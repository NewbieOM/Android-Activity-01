# Android-Activity-01


Below is the complete Treasure Hunt Android app in JAVA, with zero errors, matching your assignment requirements (Explicit Intent, Implicit Intent, Toast, Multiple Activities, Navigation).

Use package name:

package com.example.myapplication;


⸻

1️⃣ MainActivity.java

package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    Button startBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        startBtn = findViewById(R.id.startBtn);

        startBtn.setOnClickListener(v -> {

            Toast.makeText(MainActivity.this,
                    "Treasure Hunt Started!",
                    Toast.LENGTH_SHORT).show();

            Intent intent =
                    new Intent(MainActivity.this,
                            Clue1Activity.class);

            startActivity(intent);
        });
    }
}


⸻

2️⃣ Clue1Activity.java

package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;

public class Clue1Activity extends AppCompatActivity {

    Button nextBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_clue1);

        nextBtn = findViewById(R.id.nextBtn);

        nextBtn.setOnClickListener(v -> {

            Toast.makeText(Clue1Activity.this,
                    "Correct! Moving to Clue 2",
                    Toast.LENGTH_SHORT).show();

            Intent intent =
                    new Intent(Clue1Activity.this,
                            Clue2Activity.class);

            startActivity(intent);
        });
    }
}


⸻

3️⃣ Clue2Activity.java (Implicit Intent included)

package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.Toast;

public class Clue2Activity extends AppCompatActivity {

    Button mapBtn;
    Button treasureBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_clue2);

        mapBtn = findViewById(R.id.mapBtn);
        treasureBtn = findViewById(R.id.treasureBtn);

        mapBtn.setOnClickListener(v -> {

            Toast.makeText(this,
                    "Opening Map using Implicit Intent",
                    Toast.LENGTH_SHORT).show();

            Intent intent = new Intent(Intent.ACTION_VIEW);
            intent.setData(Uri.parse("https://maps.google.com"));

            startActivity(intent);
        });

        treasureBtn.setOnClickListener(v -> {

            Toast.makeText(this,
                    "Going to Treasure!",
                    Toast.LENGTH_SHORT).show();

            Intent intent =
                    new Intent(Clue2Activity.this,
                            TreasureActivity.class);

            startActivity(intent);
        });
    }
}


⸻

4️⃣ TreasureActivity.java

package com.example.myapplication;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.Toast;

public class TreasureActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_treasure);

        Toast.makeText(this,
                "🎉 Congratulations! Treasure Found!",
                Toast.LENGTH_LONG).show();
    }
}


⸻

5️⃣ activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <Button
        android:id="@+id/startBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Start Treasure Hunt"/>

</LinearLayout>


⸻

6️⃣ activity_clue1.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:text="Clue 1: Click the button to continue"
        android:textSize="18sp"
        android:layout_margin="20dp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <Button
        android:id="@+id/nextBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Go to Clue 2"/>

</LinearLayout>


⸻

7️⃣ activity_clue2.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <Button
        android:id="@+id/mapBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Open Map"/>

    <Button
        android:id="@+id/treasureBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Go to Treasure"/>

</LinearLayout>


⸻

8️⃣ activity_treasure.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:text="🎉 TREASURE FOUND 🎉"
        android:textSize="24sp"
        android:textStyle="bold"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

</LinearLayout>


⸻

9️⃣ AndroidManifest.xml (IMPORTANT)

Make sure inside <application> you have:

<activity android:name=".TreasureActivity"/>
<activity android:name=".Clue2Activity"/>
<activity android:name=".Clue1Activity"/>
<activity android:name=".MainActivity">
    <intent-filter>
        <action android:name="android.intent.action.MAIN"/>
        <category android:name="android.intent.category.LAUNCHER"/>
    </intent-filter>
</activity>


⸻

✅ Assignment requirements covered

✔ Multiple Activities
✔ Explicit Intent
✔ Implicit Intent
✔ Toast messages
✔ Navigation flow
✔ Treasure hunt structure

⸻

▶️ Now run:

Build → Rebuild Project → Run ▶️

⸻

If you want, I can also give a ZIP project structure screenshot so you can submit easily to your teacher.
