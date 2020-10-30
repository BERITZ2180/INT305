# INT305
//INT305 Week 5 App
//MainActivity.java
package com.int305.discgolfgod;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.ImageButton;
import android.widget.ImageView;
import android.widget.Spinner;

public class MainActivity extends AppCompatActivity{
    private int currentDiscNumber = 1;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        setupNextImageButton();
            }

    private void setupNextImageButton() {
        Button btn = (Button) findViewById(R.id.btnNextImage);
        btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                currentDiscNumber ++;
                if (currentDiscNumber > 4){
                    currentDiscNumber = 1;
                }
                String filename = "disc_" + currentDiscNumber;
                int id = getResources().getIdentifier(filename,"drawable",MainActivity.this.getPackageName());
                ImageView imageView = (ImageView) findViewById(R.id.discs);
                imageView.setImageResource(R.drawable.id);
            }
        });
    }


}

//activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView2"
        android:layout_width="407dp"
        android:layout_height="735dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0"
        app:srcCompat="@drawable/_1646078_green_field_with_tree_and_cloudy_sky_" />

    <Button
        android:id="@+id/btnNextImage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="36dp"
        android:text="My Bag"
        android:textAppearance="@style/TextAppearance.AppCompat.Display3"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="@+id/imageView2" />

    <ImageView
        android:id="@+id/discs"
        android:layout_width="183dp"
        android:layout_height="183dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:srcCompat="@drawable/bag" />

</androidx.constraintlayout.widget.ConstraintLayout>
