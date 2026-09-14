# Atividade-2-SORTEIO

# EXERCICIO 1

Ao clicar no botão "Saudar", a função saudarUsuario(view: View) é acionada pelo parâmetro android:onClick. Dentro dela, o println envia uma mensagem para o console de depuração (Logcat) e o findViewById busca a referência da view do tipo TextView para atualizar seu texto com setText (ou atribuição .text).

# KOTLIN
package com.exemplo.aula2

import android.os.Bundle
import android.view.View
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main_ex1)
    }

    fun saudarUsuario(view: View) {
        // 1. Mensagem fixa no Logcat
        println("O botão Saudar foi clicado!")

        // 2. Atualização do TextView
        val txtSaudacao = findViewById<TextView>(R.id.txtSaudacao)
        txtSaudacao.text = "Olá, seja bem-vindo(a)!"
    }
}

# XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/txtSaudacao"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Aguardando saudação..."
        android:textSize="18sp" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:onClick="saudarUsuario"
        android:text="Saudar" />

</LinearLayout>

[


# EXERCICIO 2

A variável contador deve ficar declarada fora da função contarClique, no nível da classe MainActivity. Se ficasse dentro da função, toda vez que o botão fosse pressionado a variável seria reiniciada em 0. A cada clique, incrementamos contador++, exibimos a contagem no Logcat e atualizamos a tela.


# kotlin

import android.os.Bundle
import android.view.View
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    // Declaração fora da função para manter o valor entre cliques
    private var contador = 0

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main_ex2)
    }

    fun contarClique(view: View) {
        contador++

        // Imprime no Logcat
        println("botão clicado $contador vezes")

        // Atualiza a tela
        val txtContador = findViewById<TextView>(R.id.txtContador)
        txtContador.text = "Cliques: $contador"
    }
}

# XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/txtContador"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Cliques: 0"
        android:textSize="18sp" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:onClick="contarClique"
        android:text="Contar" />

</LinearLayout>

