---
theme: seriph
background: https://cover.sli.dev
title: CRUD Operations - Update & Delete
info: |
  ## CRUD Operations - Update & Delete
  Cloud Computing Week 5 - Sistem Informasi
author: Cloud Computing Course
presenter: true
drawings:
  enabled: true
transition: slide-left
mdc: true
---

# CRUD Operations
## Update & Delete Operations

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Cloud Computing Week 5 <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
Selamat datang di pertemuan kelima Cloud Computing.
Hari ini kita akan melengkapi CRUD operations dengan UPDATE dan DELETE functionality.
-->

---
layout: default
---

# Learning Objectives
## *Tujuan Pembelajaran Hari Ini*

<div class="grid grid-cols-1 gap-4 pt-4">

<v-click>

### ✏️ <span v-mark.circle.red="1">**Edit Functionality**</span>
Membangun sistem editing yang intuitive dengan pre-populated forms

</v-click>

<v-click>

### 🗑️ <span v-mark.highlight.yellow="2">**Delete Operations**</span>
Implementasi deletion yang aman dengan confirmation dan soft deletes

</v-click>

<v-click>

### ✅ <span v-mark.underline.blue="3">**Data Validation**</span>
Advanced validation untuk update operations dan data integrity

</v-click>

<v-click>

### ⚠️ <span v-mark.strikethrough.green="4">**Error Handling**</span>
Robust error handling dengan user-friendly feedback dan recovery

</v-click>

</div>

<v-click>

<div class="absolute bottom-4 right-4">
  <div class="flex items-center gap-2 bg-orange-50 px-4 py-2 rounded-lg">
    <carbon:task class="text-orange-600" />
    <span class="text-sm text-orange-800">Complete CRUD</span>
  </div>
</div>

</v-click>

<!--
Hari ini kita akan melengkapi CRUD operations dengan UPDATE dan DELETE.
Focus pada safety, validation, dan user experience yang excellent.
-->

---
layout: center
class: text-center
---

# CRUD Operations Recap
## *Complete Data Management*

<v-click>

<div class="grid grid-cols-4 gap-6 pt-8">
  
  <div class="text-center">
    <div class="text-4xl mb-4 text-blue-600">📝</div>
    <h3 class="text-lg font-bold mb-2 opacity-50">CREATE</h3>
    <p class="text-sm text-gray-500">✅ Completed</p>
  </div>
  
  <div class="text-center">
    <div class="text-4xl mb-4 text-green-600">👁️</div>
    <h3 class="text-lg font-bold mb-2 opacity-50">READ</h3>
    <p class="text-sm text-gray-500">✅ Completed</p>
  </div>
  
  <div class="text-center">
    <div class="text-4xl mb-4 text-orange-600">✏️</div>
    <h3 class="text-lg font-bold mb-2"><span v-mark.highlight.orange="2">UPDATE</span></h3>
    <p class="text-sm text-orange-600">🎯 Today's Focus</p>
  </div>
  
  <div class="text-center">
    <div class="text-4xl mb-4 text-red-600">🗑️</div>
    <h3 class="text-lg font-bold mb-2"><span v-mark.highlight.red="3">DELETE</span></h3>
    <p class="text-sm text-red-600">🎯 Today's Focus</p>
  </div>
  
</div>

</v-click>

<v-click>

<div class="mt-8 text-xl text-gray-700">
  Completing the <span v-mark.circle.purple="4">**CRUD Circle**</span> 🔄
</div>

</v-click>

<!--
Kita sudah menguasai CREATE dan READ minggu lalu.
Hari ini focus pada UPDATE dan DELETE untuk melengkapi CRUD operations.
-->

---
layout: center
---

# Update Operations
## *Editing Existing Data*

<v-click>

<div class="grid grid-cols-3 gap-8 pt-8">
  
  <div class="text-center">
    <div class="text-5xl mb-4">📋</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.blue="1">Pre-populate Forms</span></h3>
    <p class="text-gray-600">Display current data for editing</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">✅</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.green="2">Validation</span></h3>
    <p class="text-gray-600">Ensure data integrity during updates</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">💾</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.orange="3">Update Storage</span></h3>
    <p class="text-gray-600">Safely persist changes to database</p>
  </div>
  
</div>

</v-click>

<!--
Update operations melibatkan tiga komponen utama untuk editing experience yang smooth.
-->

---
layout: default
---

# Update Controller Implementation
## *Backend Update Logic*

````md magic-move {at:1}
```php
<?php
// Basic Update Methods
class PostController extends Controller
{
    public function edit($id)
    {
        $post = Post::findOrFail($id);
        return view('posts.edit', compact('post'));
    }
    
    public function update(Request $request, $id)
    {
        $post = Post::findOrFail($id);
        $post->update($request->all());
        
        return redirect('/posts');
    }
}
```

```php
<?php
// Update with Validation
class PostController extends Controller
{
    public function edit($id)
    {
        $post = Post::findOrFail($id);
        $categories = Category::all();
        
        return view('posts.edit', compact('post', 'categories'));
    }
    
    public function update(Request $request, $id)
    {
        $post = Post::findOrFail($id);
        
        $validated = $request->validate([
            'title' => 'required|min:5|max:255',
            'content' => 'required|min:10',
            'category_id' => 'required|exists:categories,id'
        ]);
        
        $post->update($validated);
        
        return redirect('/posts')->with('success', 'Post updated!');
    }
}
```

```php
<?php
// Advanced with File & Authorization
class PostController extends Controller
{
    public function edit($id)
    {
        $post = Post::findOrFail($id);
        $this->authorize('update', $post);
        
        return view('posts.edit', [
            'post' => $post,
            'categories' => Category::all()
        ]);
    }
    
    public function update(Request $request, $id)
    {
        $post = Post::findOrFail($id);
        $this->authorize('update', $post);
        
        $validated = $request->validate([
            'title' => 'required|min:5|max:255|unique:posts,title,' . $id,
            'content' => 'required|min:10',
            'category_id' => 'required|exists:categories,id',
            'featured_image' => 'nullable|image|max:2048'
        ]);
        
        if ($request->hasFile('featured_image')) {
            if ($post->featured_image) {
                Storage::delete($post->featured_image);
            }
            $validated['featured_image'] = $request->file('featured_image')
                ->store('posts', 'public');
        }
        
        $post->update($validated);
        
        return redirect('/posts')->with('success', 'Post updated!');
    }
}
```
````

<v-click>

<div class="absolute bottom-4 left-4">
  <div class="bg-orange-100 text-orange-800 px-3 py-2 rounded text-sm">
    <carbon:warning class="inline mr-1" /> 
    Always authorize before updating!
  </div>
</div>

</v-click>

<!--
Update controller development dengan progressive complexity.
Authorization dan file handling adalah concerns penting dalam updates.
-->

---
layout: default
---

# Edit Form Implementation
## *Pre-populated Forms*

````md magic-move {at:1}
```html
<!-- Basic Edit Form -->
<form method="POST" action="/posts/{{ $post->id }}">
    @method('PUT')
    @csrf
    
    <input type="text" name="title" value="{{ $post->title }}" required>
    <textarea name="content" required>{{ $post->content }}</textarea>
    
    <button type="submit">Update Post</button>
</form>
```

```html
<!-- Enhanced with Validation -->
<form method="POST" action="/posts/{{ $post->id }}">
    @method('PUT')
    @csrf
    
    <input type="text" name="title" 
           value="{{ old('title', $post->title) }}"
           class="@error('title') is-invalid @enderror" required>
    @error('title')
        <div class="invalid-feedback">{{ $message }}</div>
    @enderror
    
    <select name="category_id" required>
        @foreach($categories as $category)
            <option value="{{ $category->id }}" 
                    {{ old('category_id', $post->category_id) == $category->id ? 'selected' : '' }}>
                {{ $category->name }}
            </option>
        @endforeach
    </select>
    
    <textarea name="content" required>{{ old('content', $post->content) }}</textarea>
    
    <button type="submit">Update Post</button>
    <a href="/posts">Cancel</a>
</form>
```

```html
<!-- Complete with Image Update -->
<form method="POST" action="/posts/{{ $post->id }}" enctype="multipart/form-data">
    @method('PUT')
    @csrf
    
    <input type="text" name="title" 
           value="{{ old('title', $post->title) }}" required>
    
    <!-- Current Image Display -->
    @if($post->featured_image)
        <div class="current-image">
            <img src="{{ Storage::url($post->featured_image) }}" 
                 alt="Current image" style="max-width: 200px;">
            <p>Current image</p>
        </div>
    @endif
    
    <!-- New Image Upload -->
    <input type="file" name="featured_image" accept="image/*">
    <small>Leave empty to keep current image</small>
    
    <textarea name="content" required>{{ old('content', $post->content) }}</textarea>
    
    <button type="submit">Update Post</button>
    <a href="/posts/{{ $post->id }}">Cancel</a>
</form>
```
````

<!--
Edit form development dengan progressive enhancement.
old() helper dan current value handling untuk user experience yang smooth.
-->

---
layout: two-cols
---

# Update Validation Strategies
## *Data Integrity in Updates*

<v-click>

### <span v-mark.circle.red="1">**Unique Field Updates**</span>
```php
// Exclude current record from unique check
'email' => 'required|email|unique:users,email,' . $id

// More specific exclusion
'slug' => Rule::unique('posts')->ignore($post->id)
```

</v-click>

<v-click>

### <span v-mark.highlight.blue="2">**Conditional Validation**</span>
```php
'password' => 'nullable|min:8|confirmed',
'new_password' => 'required_with:current_password|min:8'
```

</v-click>

<v-click>

### <span v-mark.underline.green="3">**File Update Logic**</span>
```php
'image' => 'nullable|image|max:2048',
// Only update if new file provided
if ($request->hasFile('image')) {
    // Handle file replacement
}
```

</v-click>

::right::

<v-click>

<v-motion
  :initial="{ x: 50, opacity: 0 }"
  :enter="{ x: 0, opacity: 1 }"
  :duration="700">

```php
<?php
// Custom Update Request
class UpdatePostRequest extends FormRequest
{
    public function rules()
    {
        $postId = $this->route('post');
        
        return [
            'title' => [
                'required',
                'string',
                'min:5',
                'max:255',
                Rule::unique('posts')->ignore($postId)
            ],
            'content' => 'required|string|min:10',
            'category_id' => 'required|exists:categories,id',
            'featured_image' => 'nullable|image|max:2048',
            'status' => 'required|in:draft,published'
        ];
    }
    
    public function messages()
    {
        return [
            'title.unique' => 'A post with this title already exists.',
            'featured_image.max' => 'Image must be less than 2MB.'
        ];
    }
}

// Controller Usage
public function update(UpdatePostRequest $request, $id)
{
    $post = Post::findOrFail($id);
    $validated = $request->validated();
    
    $post->update($validated);
    
    return redirect('/posts')->with('success', 'Updated!');
}
```

</v-motion>

</v-click>

<!--
Advanced validation techniques untuk update operations.
Unique field handling dan conditional validation untuk scenarios yang complex.
-->

---
layout: center
---

# Delete Operations
## *Safe Data Removal*

<v-click>

<div class="grid grid-cols-3 gap-8 pt-8">
  
  <div class="text-center">
    <div class="text-5xl mb-4">⚠️</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.red="1">Confirmation</span></h3>
    <p class="text-gray-600">User confirmation before deletion</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">🗑️</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.orange="2">Soft Deletes</span></h3>
    <p class="text-gray-600">Recoverable deletion strategy</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">🔗</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.blue="3">Cascade Handling</span></h3>
    <p class="text-gray-600">Related data management</p>
  </div>
  
</div>

</v-click>

<!--
Delete operations memerlukan special consideration untuk safety dan data integrity.
-->

---
layout: default
---

# Delete Controller Implementation
## *Safe Deletion Logic*

````md magic-move {at:1}
```php
<?php
// Basic Delete
class PostController extends Controller
{
    public function destroy($id)
    {
        $post = Post::findOrFail($id);
        $post->delete();
        
        return redirect('/posts')
               ->with('success', 'Post deleted!');
    }
}
```

```php
<?php
// Delete with Authorization & File Cleanup
class PostController extends Controller
{
    public function destroy($id)
    {
        $post = Post::findOrFail($id);
        $this->authorize('delete', $post);
        
        // Delete associated files
        if ($post->featured_image) {
            Storage::delete($post->featured_image);
        }
        
        $post->delete();
        
        return redirect('/posts')->with('success', 'Post deleted!');
    }
}
```

```php
<?php
// Soft Delete with Recovery Options
class PostController extends Controller
{
    public function destroy($id)
    {
        $post = Post::findOrFail($id);
        $this->authorize('delete', $post);
        
        $post->delete(); // Soft delete
        
        return redirect('/posts')
               ->with('success', 'Post moved to trash!');
    }
    
    public function forceDestroy($id)
    {
        $post = Post::withTrashed()->findOrFail($id);
        $this->authorize('forceDelete', $post);
        
        if ($post->featured_image) {
            Storage::delete($post->featured_image);
        }
        
        $post->forceDelete(); // Permanent deletion
        
        return redirect('/posts/trash')
               ->with('success', 'Post deleted permanently!');
    }
    
    public function restore($id)
    {
        $post = Post::withTrashed()->findOrFail($id);
        $this->authorize('restore', $post);
        
        $post->restore();
        
        return redirect('/posts')
               ->with('success', 'Post restored!');
    }
}
```
````

<v-click>

<div class="absolute bottom-4 right-4">
  <div class="bg-red-100 text-red-800 px-3 py-2 rounded text-sm">
    <carbon:trash-can class="inline mr-1" /> 
    Soft deletes recommended!
  </div>
</div>

</v-click>

<!--
Delete controller development dengan safety considerations.
Soft deletes memberikan safety net untuk data recovery.
-->

---
layout: two-cols
---

# Soft Deletes Setup
## *Recoverable Deletion*

<v-click>

### <span v-mark.circle.blue="1">**Migration Setup**</span>
```php
// Add to migration
$table->softDeletes();

// Or manually
$table->timestamp('deleted_at')->nullable();
```

</v-click>

<v-click>

### <span v-mark.highlight.green="2">**Model Configuration**</span>
```php
use Illuminate\Database\Eloquent\SoftDeletes;

class Post extends Model
{
    use SoftDeletes;
    
    protected $dates = ['deleted_at'];
}
```

</v-click>

<v-click>

### <span v-mark.underline.orange="3">**Query Scopes**</span>
```php
// Include soft deleted
Post::withTrashed()->get();

// Only soft deleted
Post::onlyTrashed()->get();

// Restore
$post->restore();
```

</v-click>

::right::

<v-click>

<v-motion
  :initial="{ y: 30, opacity: 0 }"
  :enter="{ y: 0, opacity: 1 }"
  :duration="600">

```php
<?php
// Complete Soft Delete Model
class Post extends Model
{
    use SoftDeletes;
    
    protected $fillable = [
        'title', 'content', 'user_id', 'category_id'
    ];
    
    protected $dates = ['deleted_at'];
    
    // Relationships work with soft deletes
    public function user()
    {
        return $this->belongsTo(User::class);
    }
    
    // Custom scopes
    public function scopeTrash($query)
    {
        return $query->onlyTrashed();
    }
    
    // Cleanup on deletion
    protected static function boot()
    {
        parent::boot();
        
        static::deleting(function ($post) {
            // Clean up related data
            $post->comments()->delete();
        });
        
        static::forceDeleting(function ($post) {
            // Clean up files permanently
            if ($post->featured_image) {
                Storage::delete($post->featured_image);
            }
        });
    }
}
```

</v-motion>

</v-click>

<!--
Soft deletes implementation yang comprehensive.
Model events untuk cleanup automation dan data integrity.
-->

---
layout: default
---

# Delete Confirmation UI
## *User-Friendly Delete Interface*

````md magic-move {at:1}
```html
<!-- Basic Delete Button -->
<form method="POST" action="/posts/{{ $post->id }}" style="display: inline;">
    @method('DELETE')
    @csrf
    <button type="submit" class="btn btn-danger" 
            onclick="return confirm('Are you sure?')">
        Delete
    </button>
</form>
```

```html
<!-- Enhanced Delete with Modal -->
<button type="button" class="btn btn-danger" 
        data-bs-toggle="modal" data-bs-target="#deleteModal{{ $post->id }}">
    Delete
</button>

<!-- Modal -->
<div class="modal fade" id="deleteModal{{ $post->id }}">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h5>Confirm Deletion</h5>
            </div>
            <div class="modal-body">
                <p>Delete <strong>"{{ $post->title }}"</strong>?</p>
                <p class="text-muted">This can be undone from trash.</p>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" 
                        data-bs-dismiss="modal">Cancel</button>
                <form method="POST" action="/posts/{{ $post->id }}" style="display: inline;">
                    @method('DELETE')
                    @csrf
                    <button type="submit" class="btn btn-danger">Delete</button>
                </form>
            </div>
        </div>
    </div>
</div>
```

```html
<!-- Complete with Soft Delete Options -->
<div class="post-actions">
    <!-- Move to Trash -->
    <button class="btn btn-warning btn-sm" 
            data-bs-toggle="modal" data-bs-target="#trashModal{{ $post->id }}">
        Move to Trash
    </button>
    
    <!-- For Trashed Items -->
    @if($post->trashed())
        <button class="btn btn-danger btn-sm" 
                data-bs-toggle="modal" data-bs-target="#permanentModal{{ $post->id }}">
            Delete Permanently
        </button>
        
        <form method="POST" action="/posts/{{ $post->id }}/restore" style="display: inline;">
            @csrf
            <button type="submit" class="btn btn-success btn-sm">Restore</button>
        </form>
    @endif
</div>

<!-- Trash Modal -->
<div class="modal fade" id="trashModal{{ $post->id }}">
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header bg-warning">
                <h5>Move to Trash</h5>
            </div>
            <div class="modal-body">
                <p>Move <strong>"{{ $post->title }}"</strong> to trash?</p>
                <div class="alert alert-info">You can restore this later.</div>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" data-bs-dismiss="modal">Cancel</button>
                <form method="POST" action="/posts/{{ $post->id }}" style="display: inline;">
                    @method('DELETE')
                    @csrf
                    <button type="submit" class="btn btn-warning">Move to Trash</button>
                </form>
            </div>
        </div>
    </div>
</div>
```
````

<!--
Delete UI development dengan progressive safety measures.
Modal confirmations dan clear messaging untuk user guidance.
-->

---
layout: two-cols
---

# Error Handling Strategies
## *Robust Error Management*

<v-click>

### <span v-mark.circle.red="1">**Validation Errors**</span>
```php
try {
    $post->update($validated);
} catch (ValidationException $e) {
    return back()->withErrors($e->errors())
                 ->withInput();
}
```

</v-click>

<v-click>

### <span v-mark.highlight.blue="2">**Database Errors**</span>
```php
try {
    $post->delete();
} catch (QueryException $e) {
    return back()->with('error', 
        'Cannot delete: Related data exists');
}
```

</v-click>

<v-click>

### <span v-mark.underline.green="3">**File Operation Errors**</span>
```php
try {
    Storage::delete($post->featured_image);
} catch (Exception $e) {
    Log::error('File deletion failed: ' . $e->getMessage());
}
```

</v-click>

::right::

<v-click>

<v-motion
  :initial="{ x: 50, opacity: 0 }"
  :enter="{ x: 0, opacity: 1 }"
  :duration="600">

```php
<?php
// Comprehensive Error Handling
class PostController extends Controller
{
    public function update(Request $request, $id)
    {
        try {
            $post = Post::findOrFail($id);
            $this->authorize('update', $post);
            
            $validated = $request->validate([
                'title' => 'required|min:5|max:255',
                'content' => 'required|min:10',
                'featured_image' => 'nullable|image|max:2048'
            ]);
            
            DB::beginTransaction();
            
            if ($request->hasFile('featured_image')) {
                $oldImage = $post->featured_image;
                $validated['featured_image'] = $request
                    ->file('featured_image')
                    ->store('posts', 'public');
                
                if ($oldImage) {
                    Storage::delete($oldImage);
                }
            }
            
            $post->update($validated);
            DB::commit();
            
            return redirect('/posts')
                   ->with('success', 'Post updated!');
                   
        } catch (ValidationException $e) {
            return back()->withErrors($e->errors())->withInput();
        } catch (Exception $e) {
            DB::rollBack();
            Log::error('Update failed: ' . $e->getMessage());
            
            return back()->with('error', 'Update failed. Try again.')
                ->withInput();
        }
    }
}
```

</v-motion>

</v-click>

<!--
Comprehensive error handling dengan different exception types.
Database transactions untuk data consistency dan proper rollback.
-->

---
layout: center
---

# Advanced Features
## *Enhancing CRUD Operations*

<v-click>

<div class="grid grid-cols-3 gap-8 pt-8">
  
  <div class="text-center">
    <div class="text-5xl mb-4">📋</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.blue="1">Bulk Operations</span></h3>
    <p class="text-gray-600">Multiple record handling</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">📝</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.green="2">Audit Trail</span></h3>
    <p class="text-gray-600">Track changes and history</p>
  </div>
  
  <div class="text-center">
    <div class="text-5xl mb-4">🔄</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.orange="3">Status Management</span></h3>
    <p class="text-gray-600">Workflow and state transitions</p>
  </div>
  
</div>

</v-click>

<!--
Advanced CRUD features untuk enterprise-level applications.
-->

---
layout: default
---

# Bulk Operations Implementation
## *Managing Multiple Records*

````md magic-move {at:1}
```html
<!-- Bulk Selection UI -->
<form method="POST" action="/posts/bulk-delete">
    @csrf
    <div class="bulk-actions">
        <input type="checkbox" id="select-all"> Select All
        <button type="submit" class="btn btn-danger">Delete Selected</button>
    </div>
    
    @foreach($posts as $post)
        <div class="post-item">
            <input type="checkbox" name="selected[]" value="{{ $post->id }}">
            <h3>{{ $post->title }}</h3>
        </div>
    @endforeach
</form>
```

```php
<?php
// Bulk Operations Controller
class PostController extends Controller
{
    public function bulkDelete(Request $request)
    {
        $selectedIds = $request->input('selected', []);
        
        if (empty($selectedIds)) {
            return back()->with('error', 'No posts selected.');
        }
        
        $posts = Post::whereIn('id', $selectedIds)->get();
        
        // Check authorization for each post
        foreach ($posts as $post) {
            $this->authorize('delete', $post);
        }
        
        Post::whereIn('id', $selectedIds)->delete();
        
        return back()->with('success', count($selectedIds) . ' posts deleted.');
    }
    
    public function bulkUpdate(Request $request)
    {
        $selectedIds = $request->input('selected', []);
        $action = $request->input('bulk_action');
        
        switch ($action) {
            case 'publish':
                Post::whereIn('id', $selectedIds)->update(['status' => 'published']);
                break;
            case 'draft':
                Post::whereIn('id', $selectedIds)->update(['status' => 'draft']);
                break;
            case 'change_category':
                Post::whereIn('id', $selectedIds)
                    ->update(['category_id' => $request->input('new_category_id')]);
                break;
        }
        
        return back()->with('success', 'Bulk update completed.');
    }
}
```
````

<v-click>

<div class="absolute bottom-4 right-4">
  <div class="bg-purple-100 text-purple-800 px-3 py-2 rounded text-sm">
    <carbon:checkmark-outline class="inline mr-1" /> 
    Bulk operations save time!
  </div>
</div>

</v-click>

<!--
Bulk operations untuk efficiency dalam managing multiple records.
Authorization checking tetap penting bahkan untuk bulk operations.
-->

---
layout: two-cols
---

# Route Organization
## *RESTful Route Structure*

<v-click>

### <span v-mark.circle.blue="1">**Standard Routes**</span>
```php
Route::resource('posts', PostController::class);
```
*Generates all CRUD routes automatically*

</v-click>

<v-click>

### <span v-mark.highlight.green="2">**Custom Routes**</span>
```php
Route::post('posts/bulk-delete', [PostController::class, 'bulkDelete']);
Route::post('posts/{post}/restore', [PostController::class, 'restore']);
Route::delete('posts/{post}/force', [PostController::class, 'forceDestroy']);
```

</v-click>

<v-click>

### <span v-mark.underline.orange="3">**Route Model Binding**</span>
```php
// Automatic injection
public function show(Post $post) {
    return view('posts.show', compact('post'));
}
```

</v-click>

::right::

<v-click>

<v-motion
  :initial="{ x: 50, opacity: 0 }"
  :enter="{ x: 0, opacity: 1 }"
  :duration="600">

```php
<?php
// Complete Route Setup
// routes/web.php

// Public routes
Route::get('/', [HomeController::class, 'index'])->name('home');
Route::get('/posts', [PostController::class, 'index'])->name('posts.index');
Route::get('/posts/{post}', [PostController::class, 'show'])->name('posts.show');

// Protected routes
Route::middleware(['auth'])->group(function () {
    // Standard CRUD
    Route::resource('posts', PostController::class)->except(['index', 'show']);
    
    // Custom actions
    Route::prefix('posts')->name('posts.')->group(function () {
        Route::post('bulk-delete', [PostController::class, 'bulkDelete'])
             ->name('bulk-delete');
        Route::post('bulk-update', [PostController::class, 'bulkUpdate'])
             ->name('bulk-update');
        Route::post('{post}/restore', [PostController::class, 'restore'])
             ->name('restore');
        Route::delete('{post}/force', [PostController::class, 'forceDestroy'])
               ->name('force-destroy');
    });
    
    // Trash management
    Route::get('trash', [PostController::class, 'trash'])->name('posts.trash');
});

// API routes for AJAX
Route::prefix('api')->middleware(['auth:sanctum'])->group(function () {
    Route::post('posts/{post}/toggle-status', [PostController::class, 'toggleStatus']);
    Route::get('posts/search', [PostController::class, 'search']);
});
```

</v-motion>

</v-click>

<!--
Route organization yang clean dan logical.
Grouping routes untuk better organization dan middleware management.
-->

---
layout: center
---

# Testing CRUD Operations
## *Ensuring Code Quality*

<v-click>

<div class="grid grid-cols-2 gap-12 pt-8">
  
  <div class="text-center">
    <div class="text-6xl mb-4">🧪</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.blue="1">Unit Tests</span></h3>
    <p class="text-gray-600">Test individual methods and logic</p>
  </div>
  
  <div class="text-center">
    <div class="text-6xl mb-4">🌐</div>
    <h3 class="text-xl font-bold mb-2"><span v-mark.highlight.green="2">Feature Tests</span></h3>
    <p class="text-gray-600">Test complete user workflows</p>
  </div>
  
</div>

</v-click>

<!--
Testing adalah bagian penting dari development process untuk CRUD operations.
-->

---
layout: default
---

# CRUD Testing Examples
## *Automated Testing Implementation*

````md magic-move {at:1}
```php
<?php
// Basic CRUD Tests
class PostCrudTest extends TestCase
{
    use RefreshDatabase;
    
    public function test_user_can_create_post()
    {
        $user = User::factory()->create();
        
        $response = $this->actingAs($user)->post('/posts', [
            'title' => 'Test Post',
            'content' => 'This is test content',
            'category_id' => Category::factory()->create()->id
        ]);
        
        $response->assertRedirect('/posts');
        $this->assertDatabaseHas('posts', [
            'title' => 'Test Post'
        ]);
    }
}
```

```php
<?php
// Comprehensive CRUD Tests
class PostCrudTest extends TestCase
{
    use RefreshDatabase;
    
    public function test_user_can_update_own_post()
    {
        $user = User::factory()->create();
        $post = Post::factory()->create(['user_id' => $user->id]);
        
        $response = $this->actingAs($user)->put("/posts/{$post->id}", [
            'title' => 'Updated Title',
            'content' => 'Updated content here',
            'category_id' => $post->category_id
        ]);
        
        $response->assertRedirect('/posts');
        $this->assertDatabaseHas('posts', [
            'id' => $post->id,
            'title' => 'Updated Title'
        ]);
    }
    
    public function test_user_cannot_delete_others_post()
    {
        $user1 = User::factory()->create();
        $user2 = User::factory()->create();
        $post = Post::factory()->create(['user_id' => $user1->id]);
        
        $response = $this->actingAs($user2)->delete("/posts/{$post->id}");
        
        $response->assertStatus(403);
        $this->assertDatabaseHas('posts', ['id' => $post->id]);
    }
    
    public function test_post_soft_deletes_correctly()
    {
        $user = User::factory()->create();
        $post = Post::factory()->create(['user_id' => $user->id]);
        
        $response = $this->actingAs($user)->delete("/posts/{$post->id}");
        
        $response->assertRedirect('/posts');
        $this->assertSoftDeleted('posts', ['id' => $post->id]);
    }
}
```
````

<v-click>

<div class="absolute bottom-4 right-4">
  <div class="bg-green-100 text-green-800 px-3 py-2 rounded text-sm">
    <carbon:test-tool class="inline mr-1" /> 
    Tests ensure reliability!
  </div>
</div>

</v-click>

<!--
CRUD testing implementation untuk code quality assurance.
Testing authorization, validation, dan business logic.
-->

---
layout: center
---

# Best Practices Summary
## *CRUD Operations Excellence*

<div class="grid grid-cols-2 gap-8 pt-8">

<v-click>

<div class="bg-orange-50 p-6 rounded-lg">
  <div class="text-3xl mb-4">✏️</div>
  <h3 class="font-bold mb-2"><span v-mark.highlight.orange="1">UPDATE Operations</span></h3>
  <ul class="text-sm space-y-1">
    <li>• Pre-populate forms with current data</li>
    <li>• Handle unique field validation properly</li>
    <li>• Implement proper file replacement logic</li>
    <li>• Always authorize before updating</li>
  </ul>
</div>

</v-click>

<v-click>

<div class="bg-red-50 p-6 rounded-lg">
  <div class="text-3xl mb-4">🗑️</div>
  <h3 class="font-bold mb-2"><span v-mark.highlight.red="2">DELETE Operations</span></h3>
  <ul class="text-sm space-y-1">
    <li>• Use soft deletes for safety</li>
    <li>• Implement confirmation dialogs</li>
    <li>• Handle file cleanup properly</li>
    <li>• Consider cascade implications</li>
  </ul>
</div>

</v-click>

<v-click>

<div class="bg-blue-50 p-6 rounded-lg">
  <div class="text-3xl mb-4">✅</div>
  <h3 class="font-bold mb-2"><span v-mark.highlight.blue="3">Data Validation</span></h3>
  <ul class="text-sm space-y-1">
    <li>• Use form request classes</li>
    <li>• Implement conditional validation</li>
    <li>• Handle unique constraints correctly</li>
    <li>• Provide clear error messages</li>
  </ul>
</div>

</v-click>

<v-click>

<div class="bg-green-50 p-6 rounded-lg">
  <div class="text-3xl mb-4">⚠️</div>
  <h3 class="font-bold mb-2"><span v-mark.highlight.green="4">Error Handling</span></h3>
  <ul class="text-sm space-y-1">
    <li>• Use database transactions</li>
    <li>• Log errors for debugging</li>
    <li>• Provide user-friendly messages</li>
    <li>• Implement proper rollback logic</li>
  </ul>
</div>

</v-click>

</div>

<!--
Best practices summary untuk UPDATE dan DELETE operations yang robust dan user-friendly.
-->

---
layout: center
---

# Complete CRUD Journey
## *From Create to Delete*

<v-click>

<div class="text-center">
  <div class="text-7xl mb-6">🎯</div>
  <div class="text-2xl text-gray-700 mb-8">
    <span v-mark.highlight.blue="1">CREATE</span> → 
    <span v-mark.highlight.green="2">READ</span> → 
    <span v-mark.highlight.orange="3">UPDATE</span> → 
    <span v-mark.highlight.red="4">DELETE</span>
  </div>
  <div class="text-3xl font-bold">
    = <span v-mark.circle.purple="5">Complete Application</span> 🚀
  </div>
</div>

</v-click>

<v-click>

<div class="mt-8 grid grid-cols-4 gap-4 max-w-2xl mx-auto">
  <div class="bg-blue-100 p-3 rounded text-center">
    <div class="text-lg font-bold text-blue-800">Week 4</div>
    <div class="text-sm text-blue-600">Create & Read</div>
  </div>
  <div class="bg-orange-100 p-3 rounded text-center">
    <div class="text-lg font-bold text-orange-800">Week 5</div>
    <div class="text-sm text-orange-600">Update & Delete</div>
  </div>
  <div class="bg-purple-100 p-3 rounded text-center">
    <div class="text-lg font-bold text-purple-800">Result</div>
    <div class="text-sm text-purple-600">Full CRUD App</div>
  </div>
  <div class="bg-green-100 p-3 rounded text-center">
    <div class="text-lg font-bold text-green-800">Next</div>
    <div class="text-sm text-green-600">Advanced Features</div>
  </div>
</div>

</v-click>

<!--
Complete CRUD journey dari Week 4 sampai Week 5.
Sekarang kita memiliki foundation yang solid untuk advanced features.
-->

---
layout: center
class: text-center
---

# Questions & Discussion
## *Mari Berdiskusi!*

<div class="pt-8">
  <div class="text-6xl mb-8">❓</div>
  
  <div class="text-xl text-gray-600 mb-8">
    Ada pertanyaan tentang <span v-mark.highlight.orange="1">Edit Functionality</span>, 
    <span v-mark.highlight.red="2">Delete Operations</span>, 
    <span v-mark.highlight.blue="3">Data Validation</span>, 
    atau <span v-mark.highlight.green="4">Error Handling</span>?
  </div>
  
  <div class="grid grid-cols-2 gap-8 max-w-md mx-auto">
    <div class="bg-orange-50 p-4 rounded-lg">
      <carbon:chat class="text-orange-600 text-2xl mx-auto mb-2" />
      <div class="text-sm font-semibold text-orange-800">Discussion</div>
    </div>
    <div class="bg-red-50 p-4 rounded-lg">
      <carbon:code class="text-red-600 text-2xl mx-auto mb-2" />
      <div class="text-sm font-semibold text-red-800">Live Demo</div>
    </div>
  </div>
</div>

<div class="absolute bottom-4 right-4">
  <div class="text-sm text-gray-500">
    <carbon:time class="inline mr-1" />
    CRUD Operations Complete! 🎉
  </div>
</div>

<!--
Waktu untuk pertanyaan dan diskusi tentang UPDATE dan DELETE operations.
Silakan tanyakan apapun tentang implementation atau best practices.
-->