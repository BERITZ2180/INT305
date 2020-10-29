# INT305
INT305 Week 5 App
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
