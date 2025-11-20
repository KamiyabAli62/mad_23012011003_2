Android Application: Activity Lifecycle and Basic UI Demonstration

This project is an Android application developed to demonstrate the complete functionality of the Android Activity Lifecycle along with basic UI components. It can be used for Mobile Application Development (MAD) practicals, academic submissions, or reference material.

⸻

Objective

The objective of this application is to:
	•	Demonstrate all primary Activity Lifecycle methods.
	•	Display lifecycle state changes using Logcat and on-screen messages.
	•	Implement basic UI components such as TextView, Button, EditText, and Toast.
	•	Provide a clean and simple example of an interactive Android Activity.

⸻

Features
	•	Demonstrates all Activity lifecycle callback methods:
	•	onCreate()
	•	onStart()
	•	onResume()
	•	onPause()
	•	onStop()
	•	onRestart()
	•	onDestroy()
	•	Logs lifecycle transitions using Logcat.
	•	Displays lifecycle messages on screen.
	•	Simple UI containing:
	•	TextView
	•	EditText
	•	Button
	•	Toast message

  Project Structure

  app/
└── src/
    └── main/
        ├── java/com/example/lifecycle/
        │   └── MainActivity.kt
        ├── res/
        │   ├── layout/activity_main.xml
        │   └── values/strings.xml
        └── AndroidManifest.xml
README.md

Source Code

package com.example.lifecycle

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import android.widget.Toast

class MainActivity : AppCompatActivity() {

    private lateinit var statusText: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        statusText = findViewById(R.id.lifecycleText)
        val inputField = findViewById<EditText>(R.id.inputField)
        val button = findViewById<Button>(R.id.showButton)

        Log.d("LIFECYCLE", "onCreate called")
        statusText.text = "onCreate called"

        button.setOnClickListener {
            val text = inputField.text.toString()
            Toast.makeText(this, "You entered: $text", Toast.LENGTH_SHORT).show()
        }
    }

    override fun onStart() {
        super.onStart()
        Log.d("LIFECYCLE", "onStart called")
        statusText.text = "onStart called"
    }

    override fun onResume() {
        super.onResume()
        Log.d("LIFECYCLE", "onResume called")
        statusText.text = "onResume called"
    }

    override fun onPause() {
        super.onPause()
        Log.d("LIFECYCLE", "onPause called")
        statusText.text = "onPause called"
    }

    override fun onStop() {
        super.onStop()
        Log.d("LIFECYCLE", "onStop called")
        statusText.text = "onStop called"
    }

    override fun onRestart() {
        super.onRestart()
        Log.d("LIFECYCLE", "onRestart called")
        statusText.text = "onRestart called"
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("LIFECYCLE", "onDestroy called")
        // Cannot update UI here reliably
    }
}

activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <TextView
        android:id="@+id/lifecycleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Lifecycle State"
        android:textSize="22sp"
        android:padding="10dp" />

    <EditText
        android:id="@+id/inputField"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter something here" />

    <Button
        android:id="@+id/showButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Show Toast"
        android:layout_marginTop="16dp" />

</LinearLayout>

How It Works
	1.	Each Activity lifecycle method logs a message using Log.d().
	2.	The current lifecycle method name is displayed in the TextView.
	3.	The UI allows user input through an EditText.
	4.	Pressing the button displays the entered text via Toast.

This helps visualize lifecycle transitions when the app is minimized, rotated, reopened, or closed.

⸻

How to Run the Project
	1.	Install Android Studio.
	2.	Clone or download the project.
	3.	Open the project in Android Studio.
	4.	Connect an Android device or start an emulator.
	5.	Click the Run button.

⸻

Requirements
	•	Android Studio Flamingo or later
	•	Minimum SDK: 21
	•	Kotlin enabled in the project

⸻

Purpose

This application is created for educational use, practical submissions, assignment work, and to help understand the Activity Lifecycle with a clear visual demonstration.
