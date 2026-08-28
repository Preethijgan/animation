# Ex.No: 6 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

1. Open Android Studio and create a new Android application.

2. Design the activity layout with an ImageView/View and buttons for different animation operations.

3. Initialize the ImageView/View and all animation buttons in MainActivity.java.

4. Add Move animation to move the image horizontally.

5. Add Zoom animation to increase and decrease the image size.

6. Add Fade animation to gradually change the image transparency.

7. Add Blink animation to repeatedly make the image disappear and appear.

8. Add Rotate animation to continuously rotate the triangle around its center.

9. Add Slide animation to move the triangle from one position to another on the screen.

10. Run the application and click each button to perform the corresponding animation.

11. Verify that all animation operations are performed successfully.

## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Preethi J
Registeration Number : 212223220080
*/
```

### MainActivity.java

```java
package com.example.animation;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;

public class MainActivity extends Activity {

    View animationShape;

    Button blinkButton;
    Button fadeButton;
    Button rotateButton;
    Button zoomButton;
    Button slideButton;
    Button moveButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        animationShape = findViewById(R.id.animationShape);

        blinkButton = findViewById(R.id.blinkButton);
        fadeButton = findViewById(R.id.fadeButton);
        rotateButton = findViewById(R.id.rotateButton);
        zoomButton = findViewById(R.id.zoomButton);
        slideButton = findViewById(R.id.slideButton);
        moveButton = findViewById(R.id.moveButton);

        // Blink Animation
        blinkButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.blink);
                animationShape.startAnimation(animation);
            }
        });

        // Fade Animation
        fadeButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.fade);
                animationShape.startAnimation(animation);
            }
        });

        // Rotate Animation
        rotateButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.rotate);
                animationShape.startAnimation(animation);
            }
        });

        // Zoom Animation
        zoomButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.zoom);
                animationShape.startAnimation(animation);
            }
        });

        // Slide Animation
        slideButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.slide);
                animationShape.startAnimation(animation);
            }
        });

        // Move Animation
        moveButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Animation animation =
                        AnimationUtils.loadAnimation(MainActivity.this, R.anim.move);
                animationShape.startAnimation(animation);
            }
        });
    }
}
```

### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center"
        android:padding="20dp">

        <com.example.animation.TriangleView
            android:id="@+id/animationShape"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:layout_gravity="center" />

        <Button
            android:id="@+id/blinkButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Blink Animation" />

        <Button
            android:id="@+id/fadeButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Fade Animation" />

        <Button
            android:id="@+id/rotateButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Rotate Animation" />

        <Button
            android:id="@+id/zoomButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Zoom Animation" />

        <Button
            android:id="@+id/slideButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Slide Animation" />

        <Button
            android:id="@+id/moveButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Move Animation" />

    </LinearLayout>

</ScrollView>

```
### anim folder structure

```anim
app
 └── src
      └── main
           └── res
                └── anim
                     ├── blink.xml
                     ├── fade.xml
                     ├── rotate.xml
                     ├── zoom.xml
                     ├── slide.xml
                     └── move.xml
```

### blink.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="1.0"
    android:toAlpha="0.0"
    android:duration="500"
    android:repeatCount="5"
    android:repeatMode="reverse" />
```
### fade.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromAlpha="0.0"
    android:toAlpha="1.0"
    android:duration="1500" />

```
### rotate.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:toDegrees="360"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />
```
### zoom.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXScale="1.0"
    android:toXScale="2.0"
    android:fromYScale="1.0"
    android:toYScale="2.0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:duration="1000" />


```
### slide.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="-500"
    android:toXDelta="0"
    android:duration="1000" />
```
### move.xml
```xml
<?xml version="1.0" encoding="utf-8"?>

<translate xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromXDelta="0"
    android:toXDelta="400"
    android:duration="1000"
    android:repeatCount="1"
    android:repeatMode="reverse" />

```


## OUTPUT



https://github.com/user-attachments/assets/c8c70b21-7925-4846-ab5a-a0363b26b8bc






## RESULT

Thus, the Android application was successfully developed to perform Move, Blink, Fade, Zoom, Rotate and Slide animation operations on the image/view using Android Studio.
