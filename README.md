# Ex.No:8 To create a gallery control using android studio to display images or photos.


## AIM:

To create a gallery control using android studio to display images or photos.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
```
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name  and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Design the  MainActivity file which will contain the images to be displayed in our gallery.

Step 7: Create a CustomizedGalleryAdapter In the same location as MainActivity for easier reference,and it is extended from BaseAdapter and implements the overridden methods. 

Step 8: Save and run the application.
```


## PROGRAM:
```
/*
Program to print the text “GalleryControl”.
Developed by: SMRITI.B
Registeration Number : 212221040156
*/
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#fff"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!-- create a ImageView and Gallery -->
    <ImageView
        android:id="@+id/imageView"
        android:layout_width="fill_parent"
        android:layout_height="200dp"
        android:scaleType="fitXY" />

    <!-- By using android:spacing we can give spacing between images
        android:animationDuration="3000" -> for animation running -->
    <Gallery
        android:id="@+id/languagesGallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="100dp"
        android:animationDuration="2000"
        android:padding="10dp"
        android:spacing="5dp"
        android:unselectedAlpha="50" />
</LinearLayout>
```
## MainActivity.java:
```
package com.example.gallery_view;

import android.os.Bundle;
import android.widget.Gallery;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Gallery simpleGallery;

    CustomizedGalleryAdapter customGalleryAdapter;
    ImageView selectedImageView;

    int[] images = {
            R.drawable.img,
            R.drawable.img_1,
            R.drawable.img_2,
            R.drawable.img_3,
            R.drawable.img_4,
            R.drawable.img_5,
            R.drawable.img_6,
            R.drawable.img_7,
            R.drawable.img_8,
            R.drawable.img_9,
            R.drawable.img_10,
            R.drawable.img_11,
            R.drawable.img_12
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        
        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);

       
        selectedImageView = (ImageView) findViewById(R.id.imageView);

        
        customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);

        
        simpleGallery.setAdapter(customGalleryAdapter);

        
        simpleGallery.setOnItemClickListener((parent, view, position, id) -> {
            
            selectedImageView.setImageResource(images[position]);
        });
    }
}

```
## CustomizedGalleryAdapter.java:
```
package com.example.gallery_view;

import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;

public class CustomizedGalleryAdapter extends BaseAdapter {

    private final Context context;
    private final int[] images;

    public CustomizedGalleryAdapter(Context c, int[] images) {
        context = c;
        this.images = images;
    }

    public int getCount() {
        return images.length;
    }

    public Object getItem(int position) {
        return position;
    }

    public long getItemId(int position) {
        return position;
    }

   
    public View getView(int position, View convertView, ViewGroup parent) {
        
        ImageView imageView = new ImageView(context);

        imageView.setImageResource(images[position]);

        imageView.setLayoutParams(new Gallery.LayoutParams(200, 200));
        return imageView;
    }
}

```


## OUTPUT
![Output1](https://github.com/smriti1910/GalleryView/assets/133334803/233aab11-f958-4f0b-b61d-07024ade8e6b)
![Galleryview](https://github.com/smriti1910/GalleryView/assets/133334803/b5800ef9-8261-4b3f-a930-819de8e9c5c1)
![Gaallery&imageview](https://github.com/smriti1910/GalleryView/assets/133334803/7f0e3af7-790a-4fc7-853c-d6c47f0f1a78)





## RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.

