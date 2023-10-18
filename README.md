# Ex.No:8 To create a gallery control using android studio to display images or photos.
### AIM:

To create a gallery control using android studio to display images or photos.
### EQUIPMENTS REQUIRED:

Latest Version Android Studio
### ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as “gallery control” and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application
### PROGRAM:
~~
/*
Program to print the text “GalleryControl”.
Developed by:Mehanthyka D
Registeration Number :212221040105
*/
~~
### activity_main.xml
~~~
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="36dp"
        app:layout_constraintBottom_toTopOf="@+id/languagesGallery"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:srcCompat="@tools:sample/avatars" />

    <Gallery
        android:id="@+id/languagesGallery"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="171dp"
        android:layout_marginBottom="204dp"
        android:animationDuration="2000"
        android:padding="10dp"
        android:spacing="5dp"
        android:unselectedAlpha="50"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />

</androidx.constraintlayout.widget.ConstraintLayout>
~~~
### MainActivity.java
~~~
package com.example.gallerycontrol;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Gallery;
import android.widget.ImageView;
public class MainActivity extends AppCompatActivity {
    Gallery simpleGallery;
    CustomizedGalleryAdapter customGalleryAdapter;
    ImageView selectedImageView;
    int[] images =
            {R.drawable.c,R.drawable.css,R.drawable.java,R.drawable.python,R.drawable.html,R.drawable.js};
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleGallery = (Gallery) findViewById(R.id.languagesGallery);
        selectedImageView = (ImageView) findViewById(R.id.imageView);
        customGalleryAdapter = new CustomizedGalleryAdapter(getApplicationContext(), images);
        simpleGallery.setAdapter(customGalleryAdapter);
        simpleGallery.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
                selectedImageView.setImageResource(images[position]);
            }
        });
    }
}

CustomizedGalleryAdapter.java

package com.example.gallerycontrol;
import android.content.Context;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.Gallery;
import android.widget.ImageView;
public class CustomizedGalleryAdapter extends BaseAdapter {
    private Context context;
    private int[] images;
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
    } }
~~~
### OUTPUT
![270903693-3effe703-ddef-4c89-a0b4-2bc59dc61b43](https://github.com/mehanthyka/gallerycontrol/assets/127507580/d291ecdf-efa8-4da2-85a4-6e37c1faac43)
![270903733-73030b0d-62db-4009-9953-e4a0620c6faf](https://github.com/mehanthyka/gallerycontrol/assets/127507580/78d71165-97b3-433d-a1a6-3bc166890c1f)
![270903803-4f6b299f-3fa2-45e9-a72b-73706500798a](https://github.com/mehanthyka/gallerycontrol/assets/127507580/37a774e6-f17d-46c3-9345-64d395899e37)
![270903873-19851a56-cdb0-4fa0-9dda-475c94f22cb3](https://github.com/mehanthyka/gallerycontrol/assets/127507580/87726764-ffc8-452b-8c19-c0c2b5a4830b)
![270903904-c17862c1-bcb1-4f8a-a93e-5a28aa96c56b](https://github.com/mehanthyka/gallerycontrol/assets/127507580/39d324ba-dc8b-4d0f-9e05-71f2ca5c1ee3)

### RESULT
Thus a Simple Android Application to create a gallery control using android studio to display images or photos is developed and executed successfully.
