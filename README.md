# poweraverage
xml file-
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Power and  Average"
        android:textSize="34sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.057" />

    <TextView
        android:id="@+id/no1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="No1="
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.161"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.22" />

    <TextView
        android:id="@+id/no2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="58dp"
        android:layout_marginTop="52dp"
        android:layout_marginEnd="296dp"
        android:text="No2="
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/no1"
        app:layout_constraintVertical_bias="0.0" />

    <EditText
        android:id="@+id/n1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="56dp"
        android:layout_marginEnd="76dp"
        android:layout_marginBottom="44dp"
        android:ems="10"
        android:inputType="textPersonName"

        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/no1"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />

    <EditText
        android:id="@+id/n2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginEnd="76dp"
        android:ems="10"
        android:inputType="textPersonName"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toEndOf="@+id/no2"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.327"
        tools:ignore="MissingConstraints" />

    <Button
        android:id="@+id/power"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Power"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.219"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.464"
        tools:ignore="MissingConstraints" />

    <Button
        android:id="@+id/average"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="88dp"
        android:layout_marginEnd="80dp"
        android:text="Average"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"

        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.461"
        tools:ignore="MissingConstraints" />

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="128dp"
        android:layout_marginEnd="145dp"
        android:text="Ans="
        android:textSize="34sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.508"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.637" />

</androidx.constraintlayout.widget.ConstraintLayout>


java file-

package com.example.poweraverage;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private TextView num1,num2;

    private Button btn1,btn2;

    private TextView ans;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        num1= (TextView) findViewById(R.id.n1);
        num2= (TextView) findViewById(R.id.n2);
        btn1=(Button) findViewById(R.id.power);
        btn2=(Button) findViewById(R.id.average);
        ans=(TextView) findViewById(R.id.result);


        btn1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                double no1 = Double.parseDouble(num1.getText().toString());
                double no2 = Double.parseDouble(num2.getText().toString());
                double p;
                p = Math.pow(no1, no2);
                ans.setText("Power=" + p);
            }
        });

        btn2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                double a;
                double no1 = Double.parseDouble(num1.getText().toString());
                double no2 = Double.parseDouble(num2.getText().toString());

                a = (no1 + no2) / 2;
                ans.setText("Average=" + a);
            }

        });
    }
}


