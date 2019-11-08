# uploadImageSnippetLaravel

```php
if ($request->hasFile('photo_fr')) {
    $image_name = 'event_'.$event->id.'_photo_fr_'.time().'.jpg';
    $photo_fr = Image::make($request->file('photo_fr'));
    $photo_fr->resize(2000, 2000, function ($constraint) {
        $constraint->aspectRatio();
        $constraint->upsize();
    });
    $photo_fr->save(storage_path('app/images/'.$image_name));
    $event->image_src_fr = $image_name;
  }

```
