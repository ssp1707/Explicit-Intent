# Ex.No:2b Explicit Intent

## AIM:

To create a layout,click button, display factorial number using Explicit Intents in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min. required Artic Fox)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “ex.no.2″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: open google page using Implicit Intents and display factorial number using Explicit Intents in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:

```
/*
Program to implement “Explicit Intents”.
Developed by: B.Kavya
Registeration Number : 212220230007
*/
```

#### MainActivity.java
```
package com.example.exintent;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    EditText etNumber;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etNumber=findViewById(R.id.etNumber);
    }
    public void displayFactorial(View view){
        Intent i=new Intent(MainActivity.this,MainActivity2.class);
        i.putExtra("number",etNumber.getText().toString());
        startActivity(i);
    }
}
```
#### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="enter_the_number"
        android:inputType="number"
        android:layout_marginTop="50dp"
        android:importantForAutofill="no" />

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="factorial"
        android:onClick="displayFactorial"/>

</LinearLayout>

```
#### MainActivity2.java
```
package com.example.exintent;

import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity {
    TextView tv;
    @SuppressLint("SetTextI18n")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        Bundle b=getIntent().getExtras();
        int no=Integer.parseInt(b.getString("number"));
        long f=1;
        for(int i=no;i>0;i--)
        {
            f=f*i;
        }
        tv=findViewById(R.id.tv);
        tv.setText("Factorial of "+no+" is "+f);
    }
}

```
#### activity_main2.xml
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2"
    android:padding="20dp">

    <TextView
        android:id="@+id/tv"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:text="factorial_of_number_is"
        style="@style/TextAppearance.AppCompat.Large"/>
</RelativeLayout>
```

## OUTPUT:

![EXPT 2B 110](https://user-images.githubusercontent.com/75234965/165447989-ac801bc4-e2cf-49da-89c3-fd955b85f0e6.png)
![image](https://user-images.githubusercontent.com/75235813/165362767-17c4812f-498c-4138-9abf-3347dccb669e.png)


## RESULT:

Thus a Simple Android Application to get user and display factorial of the same number using Explicit Intents using Android Studio is developed and executed successfully.
