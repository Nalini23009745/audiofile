# Ex.No:3 Develop a simple application to play and control the audio file in android studio.


## AIM:

To develop a simple application, to play and control the audio file and to perfrom the start,pause and stop opeartion in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as audiofile and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml and create start,pause and stop button.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to play and control the audio file”.
Developed by:Nalini P
Registeration Number :212223220063
*/
```

## activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <Button
        android:id="@+id/btnPlay"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Play"/>

    <Button
        android:id="@+id/btnPause"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Pause"
        android:layout_marginTop="10dp"/>

    <Button
        android:id="@+id/btnStop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Stop"
        android:layout_marginTop="10dp"/>

</LinearLayout>

```

## Mainactivity.java

```
package com.example.pmdex3;

import androidx.appcompat.app.AppCompatActivity;

import android.media.MediaPlayer;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    Button play, pause, stop;
    MediaPlayer mediaPlayer;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        play = findViewById(R.id.btnPlay);
        pause = findViewById(R.id.btnPause);
        stop = findViewById(R.id.btnStop);

        mediaPlayer = MediaPlayer.create(this, R.raw.song);

        play.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                mediaPlayer.start();
                Toast.makeText(MainActivity.this,
                        "Audio Playing",
                        Toast.LENGTH_SHORT).show();
            }
        });

        pause.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if(mediaPlayer.isPlaying()) {
                    mediaPlayer.pause();

                    Toast.makeText(MainActivity.this,
                            "Audio Paused",
                            Toast.LENGTH_SHORT).show();
                }
            }
        });

        stop.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                if(mediaPlayer.isPlaying()) {
                    mediaPlayer.stop();

                    Toast.makeText(MainActivity.this,
                            "Audio Stopped",
                            Toast.LENGTH_SHORT).show();

                    mediaPlayer = MediaPlayer.create(
                            MainActivity.this,
                            R.raw.song);
                }
            }
        });
    }
}

```
## OUTPUT


<img width="1920" height="1200" alt="Screenshot (85)" src="https://github.com/user-attachments/assets/a9fd50ca-853b-433d-b468-55d1eba83fae" />
<img width="1920" height="1200" alt="Screenshot (86)" src="https://github.com/user-attachments/assets/8aadd048-2e87-4ff5-9bde-70bfce0544df" />
<img width="1920" height="1200" alt="Screenshot (84)" src="https://github.com/user-attachments/assets/3fbd9528-2a2c-4b46-93b7-9b18ec598057" />


## RESULT
   Thus a simple application, to play and control the audio file and to perfrom the start,pause and stop opeartion in Android Studio is developed and executed successfully.
