# CalculatorApp
## Project Overview
This Simple Calculator App is developed as part of my M.Tech assignment. The goal was to create a functional and user-friendly Android application that performs basic arithmetic operations. The project helped me gain hands-on experience with Android development using Java.

## Technologies Used
- **Java** for application logic  
- **Android Studio** as the development environment  
- **XML** for UI design  

## Learning Outcomes
- Building a responsive UI in Android Studio  
- Managing user inputs and ensuring proper validation  
- Handling basic arithmetic operations and error cases  

## Future Improvements
- Add support for advanced operations (e.g., square root, percentage)  
- Improve the UI with custom themes  
- Save calculation history

## Known Issues
- Division result may show a long decimal value  
- No support for landscape mode  

## Features
- **Basic Operations**: Add, Subtract, Multiply, Divide  
- **User Input Validation**: Ensures both numbers are entered before calculation  
- **Prevents Division by Zero**: Displays an error if attempted  
- **User-Friendly UI**: Simple and easy-to-use interface  

## Code Implementation

### **1️⃣ `activity_main.xml` (UI Layout)**
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center"
    android:background="#FAFAFA">

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter number"
        android:inputType="numberDecimal"
        android:textSize="18sp"
        android:padding="10dp"/>

    <EditText
        android:id="@+id/editText2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter number"
        android:inputType="numberDecimal"
        android:textSize="18sp"
        android:padding="10dp"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:paddingTop="20dp">

        <Button
            android:id="@+id/btnAdd"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+"
            android:textSize="20sp"
            android:padding="10dp"/>

        <Button
            android:id="@+id/btnSubtract"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="-"
            android:textSize="20sp"
            android:padding="10dp"/>

        <Button
            android:id="@+id/btnMultiply"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="×"
            android:textSize="20sp"
            android:padding="10dp"/>

        <Button
            android:id="@+id/btnDivide"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="÷"
            android:textSize="20sp"
            android:padding="10dp"/>
    </LinearLayout>

    <TextView
        android:id="@+id/resultText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Result: "
        android:textSize="22sp"
        android:textStyle="bold"
        android:paddingTop="20dp"
        android:gravity="center"/>
</LinearLayout>


### **2️⃣ `MainActivity.java` (Logic for Operations)**
```java
package com.example.calculatorapp;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    EditText editText1, editText2;
    TextView resultText;
    Button btnAdd, btnSubtract, btnMultiply, btnDivide;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText1 = findViewById(R.id.editText);
        editText2 = findViewById(R.id.editText2);
        resultText = findViewById(R.id.resultText);

        btnAdd = findViewById(R.id.btnAdd);
        btnSubtract = findViewById(R.id.btnSubtract);
        btnMultiply = findViewById(R.id.btnMultiply);
        btnDivide = findViewById(R.id.btnDivide);

        btnAdd.setOnClickListener(v -> calculate('+'));
        btnSubtract.setOnClickListener(v -> calculate('-'));
        btnMultiply.setOnClickListener(v -> calculate('*'));
        btnDivide.setOnClickListener(v -> calculate('/'));
    }

    private void calculate(char operator) {
        String num1Str = editText1.getText().toString();
        String num2Str = editText2.getText().toString();

        if (num1Str.isEmpty() || num2Str.isEmpty()) {
            resultText.setText("Please enter both numbers");
            return;
        }

        double num1 = Double.parseDouble(num1Str);
        double num2 = Double.parseDouble(num2Str);
        double result = 0;

        switch (operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 == 0) {
                    resultText.setText("Cannot divide by zero");
                    return;
                }
                result = num1 / num2;
                break;
        }
        resultText.setText("Result: " + result);
    }
}


## **How to Use**

1. **Enter two numbers** in the input fields.  
2. Click on the **+**, **-**, **×**, or **÷** button to perform the operation.  
3. The **result** will be displayed below.  

## App Preview
https://github.com/Kk1805/Calculator/blob/main/APPPREVIEW01.jpg?raw=true


## License
This project is licensed under the **MIT License**.  

## Author

👨‍💻 **Kiruthika Kanagaraj** - https://github.com/Kk1805  
📩 **Contact:** kiruthikanagaraj1805@gmail.com  
⭐ **Give a Star!** If you liked this project, please give it a **⭐ star** on GitHub!  

