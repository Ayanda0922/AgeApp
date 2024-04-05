package com.yayarh.ageapp

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView

class MainActivity : AppCompatActivity() {

    //declare
    private lateinit var searchButton: Button
    private lateinit var resultTextView: TextView
    private lateinit var ageInput: EditText
    private lateinit var clearButton: Button

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        //initialise
        searchButton = findViewById(R.id.searchButton)
        clearButton = findViewById(R.id.clearButton)
        ageInput = findViewById(R.id.ageInput)
        resultTextView = findViewById(R.id.resultTextView)

        searchButton.setOnClickListener {
            //create a variable of age to get value from user
            val age = ageInput.text.toString().toIntOrNull()

            //If age is no null age is in the range between 20 and 50
            if (age != null && age in 20..100) {
                val employeeName = when (age) {
                    25 -> "Tupac." +
                            "Tupac was an American rapper considered on of the most influential and " +
                            "successful rappers of all times , he is among the best selling music" +
                            "artist. "
                    34 -> "Ricky Rick." +
                            "Ricky rick is a South African rapper,actor,writer,composer and record" +
                            "producer,his debut studio album Family values was released on April 3" +
                            "2015. His first side of music began at a recording studio with Bongani." +
                            "It's because of Bongani that made Ricky Rick be inspired to make his own music."
                    50 -> "Micheal Jackson." +
                            "Micheal Jackson was an American singer,songwriter,dancer and philanthropist" +
                            "know as the king of pop ,he is regared as one of the most significant" +
                            "cultural figures of the 20th century , he has 9 siblings and 3 children."
                    36 -> "Zahara." +
                            "Zahara was one of the best guitarist in South Africa , a songwriter" +
                            "and a singer.She sang her songs in Xhosa her native language as well" +
                            "as English. Zahara was raised by her parents and was the sixth of her seven " +
                            "siblings. She signed one of the biggest deal with the label TS records by" +
                            "TK Nciza and released an album Loliwe in 2011."
                    96 -> "Queen Elizabeth." +
                            "Elizabeth was the Queen of the united kingdom and other Commonwealth " +
                            "realms from 6 February 1952 until her death in 2022.She was Queen regnant" +
                            "of 32 sovereign states over the course of her lifetime and remained the" +
                            "monarch of 15 realms by the time of her death."
                    47 -> "Shona Ferguson." +
                            "Shona was a Motswana actor based in South Africa, executive producer and" +
                            " co-founder of Ferguson Films alongside his wife Connie Ferguson. He became " +
                            "famous because of his acting and being a producer in some films."
                    40 -> "Paul Walker." +
                            "Paul Walker began his career as a child actor in the 1980s after that he" +
                            "appeared in the television soap opera the young and the restless, he also" +
                            "started in the commercially successful road thriller Joy ride and being" +
                            "an action star.He also played on one of the most famous movies called fast " +
                            "asn the furious."
                    63 -> "Robin Williams." +
                            "Robin was an American actor and also an comedian,known for his improvisational" +
                            "skills and the wide variety of characters he created on the spur of" +
                            "the moment and portrayed on film, in dramas and comedies alike and is regarded" +
                            "as one of the best comedians."
                    95 -> "Nelson Mandela." +
                            "Nelson was the South African anti-apartheid activist,politician,and statesman" +
                            "who served as the first black president of South Africa , who fought for the" +
                            "rights and freedom of blacks in South African."
                    80 -> "Mary Twala." +
                            "Mary was a South African actress and was nominated for South Africa best" +
                            "movie Academy Award for best Actress in supporting role. She also was an" +
                            "actress in one of the biggest movies in South Africa called SARAFINA,a movie" +
                            "that was talking about the South Africa before its was a free county. "
                    else -> null

                }
                val message = if (employeeName != null) "The employee's name is $employeeName."
                else "No employee found with the entered age."
                resultTextView.text = message

            } else {
                resultTextView.text = "Invalid input. Pleasee enter valid age between 20and 100"
            }

        }
        clearButton.setOnClickListener {
            ageInput.text.clear()
            resultTextView.text = ""
        }
    }


    }


?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

     <ImageView
    android:id="@+id/imageView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    app:srcCompat="@drawable/img_20240403_133823_453" />


    <Button
        android:id="@+id/searchButton"
        android:layout_width="122dp"
        android:layout_height="70dp"
        android:text="Enter"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.086"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.975" />

    <EditText
        android:id="@+id/ageInput"
        android:layout_width="151dp"
        android:layout_height="70dp"
        android:layout_marginTop="32dp"
        android:layout_marginBottom="50dp"
        android:text=""
        android:hint="AgeInput"
        android:textColor="@color/white"
        app:layout_constraintBottom_toTopOf="@+id/ageInput"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="NotSibling" />

    <Button
        android:id="@+id/clearButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        android:text="Button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/clearButton"
        tools:ignore="NotSibling" />

    <TextView
        android:id="@+id/resultTextView"
        android:layout_width="315dp"
        android:layout_height="231dp"
        android:fontFamily="sans-serif-black"
        android:text="Details"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.833"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.264" />

    <Button
        android:id="@+id/button"
        android:layout_width="128dp"
        android:layout_height="69dp"
        android:layout_marginTop="272dp"
        android:text="clear"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.855"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/resultTextView" />


</androidx.constraintlayout.widget.ConstraintLayout>
