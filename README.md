# Ex.No:5 Develop a program to create a simple calculator using android studio.
## AIM:
To Develop a program to create a simple calculator using android studio.

## EQUIPMENTS REQUIRED:
Android Studio(Min. required Artic Fox)

## ALGORITHM:
1. Initialize Project: Create a new Android Studio project using the Empty Views Activity template.

2. Design Layout: Finish activity_main.xml ensuring unique IDs for your two inputs, result display, and four operator buttons.

3. Link UI Elements: In MainActivity.java, use findViewById() to connect all XML elements to corresponding Java variables.

4. Create Logic Method: Define a single Java function (e.g., calculateAndDisplay) that takes the required operator as input.

5. Attach Listeners: Set up OnClickListener for all four buttons, each calling the logic method with its specific operator character.

6. Perform Calculation: Inside the logic method, convert inputs to numbers and use a switch statement to execute the correct math (and check for divide-by-zero).

7.Display Output: Update the tvResult TextView with the final answer or show an appropriate error message using Toast.

## PROGRAM:
```
Program to print the text create your own content providers to get contacts details.
Developed by: Akshaay Vardhan S
Registeration Number : 212224220007
```
### MainActivity.java
```
package com.example.simple_calculator;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText etNum1, etNum2;
    TextView tvResult;
    Button btnAdd, btnSub, btnMul, btnDiv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etNum1 = findViewById(R.id.etNum1);
        etNum2 = findViewById(R.id.etNum2);
        tvResult = findViewById(R.id.tvResult);

        btnAdd = findViewById(R.id.btnAdd);
        btnSub = findViewById(R.id.btnSub);
        btnMul = findViewById(R.id.btnMul);
        btnDiv = findViewById(R.id.btnDiv);

        btnAdd.setOnClickListener(v -> calculate("+"));
        btnSub.setOnClickListener(v -> calculate("-"));
        btnMul.setOnClickListener(v -> calculate("*"));
        btnDiv.setOnClickListener(v -> calculate("/"));
    }

    private void calculate(String op) {
        String n1 = etNum1.getText().toString();
        String n2 = etNum2.getText().toString();

        if (n1.isEmpty() || n2.isEmpty()) {
            tvResult.setText("Please enter numbers");
            return;
        }

        double a = Double.parseDouble(n1);
        double b = Double.parseDouble(n2);
        double res = 0;

        switch (op) {
            case "+": res = a + b; break;
            case "-": res = a - b; break;
            case "*": res = a * b; break;
            case "/":
                if (b != 0) res = a / b;
                else { tvResult.setText("Cannot divide by 0"); return; }
                break;
        }
        tvResult.setText(n1 + " " + op + " " + n2 + " = " + res);
    }
}
```

### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F4E3FF"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="16dp">

    <!-- Title -->
    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="20dp"
        android:text="Calculator"
        android:textSize="24sp"
        android:textStyle="bold" />

    <!-- First Number -->
    <EditText
        android:id="@+id/etNum1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:hint="Enter first number"
        android:inputType="numberDecimal" />

    <!-- Second Number -->
    <EditText
        android:id="@+id/etNum2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:hint="Enter second number"
        android:inputType="numberDecimal" />

    <!-- Result -->
    <TextView
        android:id="@+id/tvResult"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:background="#FFFEFE"
        android:gravity="center"
        android:padding="10dp"
        android:text="Result"
        android:textSize="18sp" />

    <!-- Buttons -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:gravity="center"
        android:orientation="horizontal">

        <Button
            android:id="@+id/btnAdd"
            android:layout_width="0dp"  android:layout_height="wrap_content"
            android:layout_weight="1"   android:layout_margin="5dp"
            android:backgroundTint="#050505"
            android:text="+" />

        <Button
            android:id="@+id/btnSub"
            android:layout_width="0dp"  android:layout_height="wrap_content"
            android:layout_weight="1"   android:layout_margin="5dp"
            android:backgroundTint="#181616"
            android:text="-"
            android:textSize="20sp" />

        <Button
            android:id="@+id/btnMul"
            android:layout_width="0dp"  android:layout_height="wrap_content"
            android:layout_weight="1"   android:layout_margin="5dp"
            android:backgroundTint="#040303"
            android:text="x" />

        <Button
            android:id="@+id/btnDiv"
            android:layout_width="0dp"  android:layout_height="wrap_content"
            android:layout_weight="1"   android:layout_margin="5dp"
            android:backgroundTint="#000000"
            android:text="/" />

    </LinearLayout>
</LinearLayout>
```
## OUTPUT
### MainActivity.java
<img width="1919" height="1085" alt="image" src="https://github.com/user-attachments/assets/badc596f-9547-4c19-a98b-bf4d915204ec" />

### activity_main.xml
<img width="1916" height="1092" alt="image" src="https://github.com/user-attachments/assets/36cfd0fe-c14b-4c98-9bc9-e24f33b08ad7" />

### Execution
<img width="435" height="774" alt="image" src="https://github.com/user-attachments/assets/dca114a0-81c7-45d0-95cb-4afbfca7ab81" />

## RESULT
Thus a Simple Android Application to create your own simple calculator using Android Studio is developed and executed successfully.
