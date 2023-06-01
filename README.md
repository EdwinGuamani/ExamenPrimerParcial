# ExamenPrimerParcial
package com.example.calculadorabasica;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
   Button btn_regresar;

    private Button btn_Suma;
    private Button btn_Resta;
    private Button btn_Multiplicacion;
    private Button btn_Division;

    private TextView text_respuesta;
    private EditText edittext_uno;
    private EditText edittext_dos;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btn_regresar=findViewById(R.id.btnRegresar);
        btn_Suma = findViewById(R.id.btnSuma);

        btn_Suma.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(MainActivity.this, MainActivity3.class);
                text_respuesta.setText(suma(Integer.parseInt(edittext_uno.getText().toString()), Integer.parseInt(edittext_dos.getText().toString())) + "");
                startActivity(intent);
            }
        });
        btn_regresar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent intent = new Intent(MainActivity.this, Caratula.class);
                startActivity(intent);
            }
        });
        btn_Resta = findViewById(R.id.btnResta);
        btn_Resta.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                text_respuesta.setText(resta(Integer.parseInt(edittext_uno.getText().toString()), Integer.parseInt(edittext_dos.getText().toString())) + "");
            }
        });
        btn_Multiplicacion = findViewById(R.id.btnMultiplicacion);
        btn_Multiplicacion.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                text_respuesta.setText(multiplicacion(Integer.parseInt(edittext_uno.getText().toString()), Integer.parseInt(edittext_dos.getText().toString())) + "");
            }
        });
        btn_Division = findViewById(R.id.btnDivision);
        btn_Division.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                text_respuesta.setText(division(Integer.parseInt(edittext_uno.getText().toString()), Integer.parseInt(edittext_dos.getText().toString())) + "");
            }
        });

        text_respuesta = findViewById(R.id.respuesta);

        edittext_uno = findViewById(R.id.numero1);
        edittext_dos = findViewById(R.id.numero2);

    }

    public double suma(int a, int b) {
        return a + b;
    }

    public double resta(int a, int b) {
        return a - b;
    }

    public double multiplicacion(int a, int b) {
        return a * b;
    }

    public double division(int a, int b) {
        int respuesta=0;
        if (b!=0){
            respuesta = a/b;
        }
        return respuesta;

    }
}
