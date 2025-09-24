# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
1.Start Android Studio and create a new project.

2.In the main layout file, add:

   A TextField (EditText) to enter a URL.
   A Button labeled "Navigate".

3.In the main activity:
    Get the text entered in the EditText.
    Check if the entered text equals "www.gmail.com".

If true, create an Implicit Intent with action Intent.ACTION_VIEW.

4.Pass the Google URL (https://www.google.com) to the intent using Uri.parse().

5.Start the activity with startActivity(intent) to open the browser.




## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:DHINESH R
Registeration Number :212223220019
*/
```

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <!-- Text Field -->
    <EditText
        android:id="@+id/urlEditText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter URL"
        android:text="https://www.gmail.com"
        android:inputType="textUri"
        android:layout_marginBottom="20dp"/>

    <!-- First Button -->
    <Button
        android:id="@+id/implicitButton1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Implicit Intent 1"
        android:layout_marginBottom="20dp"/>

    <!-- Second Button -->
    <Button
        android:id="@+id/implicitButton2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Implicit Intent 2" />

</LinearLayout>
```
MainActivity.java
```
package com.example.implicitintentdemo;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText urlEditText;
    Button implicitButton1, implicitButton2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize views
        urlEditText = findViewById(R.id.urlEditText);
        implicitButton1 = findViewById(R.id.implicitButton1);
        implicitButton2 = findViewById(R.id.implicitButton2);

        // Button 1 → Open Gmail page
        implicitButton1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String gmailUrl = "https://www.gmail.com";
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(gmailUrl));
                startActivity(intent);
            }
        });

        // Button 2 → Open URL from Text Field
        implicitButton2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String url = urlEditText.getText().toString();
                if (!url.startsWith("http://") && !url.startsWith("https://")) {
                    url = "https://" + url; // Add https if missing
                }
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }
        });
    }
}
```

## OUTPUT
<img width="358" height="439" alt="image" src="https://github.com/user-attachments/assets/0e3a3f45-7746-4163-b7e8-47c719282f64" />
<img width="346" height="764" alt="image" src="https://github.com/user-attachments/assets/6f255da6-070c-46df-8500-c6d4ad34d95d" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


