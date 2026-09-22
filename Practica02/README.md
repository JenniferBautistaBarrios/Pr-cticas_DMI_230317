# 🌸 Práctica 02 — Mi Primera Aplicación Móvil con Flutter

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-Framework-02569B?style=for-the-badge&logo=flutter" alt="Flutter"/>
  <img src="https://img.shields.io/badge/Dart-Lenguaje-0175C2?style=for-the-badge&logo=dart" alt="Dart"/>
  <img src="https://img.shields.io/badge/Estado-Finalizada-4CAF50?style=for-the-badge" alt="Finalizada"/>
</p>

---

## 💗 Descripción

En esta práctica se desarrolló una aplicación móvil interactiva utilizando **Flutter** y el lenguaje de programación **Dart**.

El proyecto consiste en un contador que permite incrementar, disminuir y reiniciar su valor mediante botones. Además, incorpora cambios visuales dinámicos que permiten identificar los valores positivos, negativos y neutros mediante diferentes colores.

El objetivo de esta actividad es conocer los fundamentos del desarrollo de aplicaciones móviles con Flutter, poniendo en práctica el uso de widgets, el manejo de estados y la interacción del usuario con la interfaz.

---

## 🛠️ Tecnologías utilizadas

| Tecnología                                 | Descripción                                                            |
| ------------------------------------------ | ---------------------------------------------------------------------- |
| 💙 **Flutter**                             | Framework utilizado para desarrollar la aplicación móvil.              |
| 🎯 **Dart**                                | Lenguaje de programación empleado para implementar la lógica.          |
| 🎨 **Material Design**                     | Componentes y estilos utilizados en la interfaz.                       |
| 💻 **Visual Studio Code / Android Studio** | Herramientas para desarrollar y ejecutar el proyecto.                  |
| 🌐 **Git y GitHub**                        | Herramientas para el control de versiones y almacenamiento del código. |

---

## 📋 Actividades realizadas

Durante el desarrollo de esta práctica se llevaron a cabo las siguientes actividades:

* 📱 Creación de una aplicación móvil con Flutter.
* 📂 Exploración de la estructura básica de un proyecto Flutter.
* 🧩 Desarrollo de la pantalla principal utilizando `StatefulWidget`.
* 🔢 Declaración de una variable entera para almacenar el valor del contador.
* ➕ Implementación de las funciones para aumentar y disminuir el contador.
* 🔄 Incorporación de una opción para reiniciar el contador a cero.
* ⚙️ Uso de `setState()` para actualizar la interfaz.
* 🎨 Diseño de botones flotantes con `FloatingActionButton`.
* ♻️ Creación de un componente reutilizable llamado `CustomButton`.
* 🔹 Integración de iconos de Material Icons.
* 🌈 Aplicación de colores dinámicos según el valor del contador.
* ✍️ Implementación de texto dinámico para mostrar “Click” o “Clicks”.
* 📐 Organización de los elementos mediante `Column`, `Center`, `Scaffold` y `AppBar`.
* 📏 Uso de `SizedBox` para mejorar la distribución y el espaciado.

---

## ⚙️ Funcionamiento de la aplicación

La aplicación permite realizar tres acciones principales:

### ➕ Incrementar

Al presionar el botón con el icono `plus_one`, el valor del contador aumenta una unidad.

```dart
clickCounter++;
```

### ➖ Disminuir

El botón con el icono `exposure_minus_1_outlined` permite restar una unidad al contador.

```dart
clickCounter--;
```

### 🔄 Reiniciar

Al seleccionar el botón con el icono `refresh_rounded`, el contador vuelve a su valor inicial.

```dart
clickCounter = 0;
```

Cada operación se ejecuta dentro de `setState()`, lo que permite actualizar automáticamente el valor mostrado en pantalla.

---

## 🎨 Colores dinámicos del contador

El contador cambia de color dependiendo del valor que se encuentre mostrando.

| Estado      | Condición     | Color       |
| ----------- | ------------- | ----------- |
| 🩷 Negativo | Menor que `0` | Rosa claro  |
| 🟣 Neutro   | Igual a `0`   | Morado      |
| 🌸 Positivo | Mayor que `0` | Rosa pastel |

La lógica utilizada para determinar el color es la siguiente:

```dart
color: clickCounter < 0
    ? Color(0xFFE75480)
    : clickCounter == 0
        ? Color(0xFFB57EDC)
        : Color(0xFFE8A0BF),
```

De esta manera, el usuario puede identificar fácilmente el estado actual del contador mediante tonos rosados y morados.

---

## ✨ Texto dinámico

La aplicación adapta automáticamente el texto que aparece debajo del número del contador.

Cuando el valor es `1` o `-1`, se utiliza la palabra en singular. Para los demás valores, se muestra en plural.

| Valor | Texto mostrado |
| ----: | -------------- |
|   `1` | 1 Click        |
|  `-1` | -1 Click       |
|   `0` | 0 Clicks       |
|   `2` | 2 Clicks       |
|  `-2` | -2 Clicks      |

La condición utilizada es:

```dart
'Click${clickCounter == 1 || clickCounter == -1 ? '' : 's'}'
```

Esto permite que el texto se actualice de acuerdo con el valor actual sin necesidad de modificarlo manualmente.

---

## 📱 Interfaz de usuario

La pantalla principal está diseñada para que las acciones del contador sean fáciles de identificar y utilizar.

Sus elementos principales son:

* **AppBar:** muestra el título de la aplicación y el botón de reinicio.
* **Contador principal:** presenta el valor actual con un tamaño de fuente destacado.
* **Texto descriptivo:** indica si se trata de uno o varios clicks.
* **Botón de incremento:** permite aumentar el valor.
* **Botón de decremento:** permite disminuir el valor.
* **Botón de reinicio:** devuelve el contador a cero.

Los botones se organizan verticalmente mediante un `Column`, manteniendo una distribución sencilla y ordenada.

---

## 🧩 Componente personalizado

Para reutilizar la estructura de los botones y evitar repetir código, se creó un widget personalizado llamado `CustomButton`.

```dart
class CustomButton extends StatelessWidget {
  final IconData icon;
  final VoidCallback? onPressed;

  const CustomButton({
    super.key,
    required this.icon,
    this.onPressed
  });
}
```

Este componente recibe los siguientes parámetros:

* `icon`: icono que se mostrará en el botón.
* `onPressed`: función que se ejecutará cuando el usuario presione el botón.

Su implementación facilita la reutilización de componentes y contribuye a mantener el código más organizado.

---

## 🖼️ Evidencias de funcionamiento

A continuación, se muestran las evidencias de los diferentes estados de la aplicación.

### 🌸 Contador positivo

Al incrementar el contador, el valor se muestra en color rosa pastel.

![Contador positivo](images/cap3.png)

### 🟣 Contador neutro

Cuando el contador regresa a cero, el número se muestra en color morado.

![Contador neutro](images/cap2.png)

### 🩷 Contador negativo

Al disminuir el contador por debajo de cero, el valor cambia a un tono rosa claro.

![Contador negativo](images/cap1.png)

---

## 📚 Conceptos aprendidos

Con la realización de esta práctica se reforzaron conocimientos relacionados con:

* Desarrollo de aplicaciones móviles con Flutter.
* Fundamentos del lenguaje Dart.
* Uso de `StatefulWidget` y `StatelessWidget`.
* Administración del estado mediante `setState()`.
* Declaración y modificación de variables.
* Operadores de incremento y decremento.
* Uso de condiciones y operadores ternarios.
* Manejo de eventos con `onPressed`.
* Creación de widgets reutilizables.
* Implementación de botones flotantes.
* Organización de interfaces mediante widgets.
* Uso de iconos de Material Design.
* Actualización dinámica de la interfaz.
* Diseño y distribución de elementos en aplicaciones móviles.

---

## 🌷 Conclusión

El desarrollo de esta práctica permitió crear una aplicación móvil funcional y comprender algunos de los principios fundamentales de Flutter y Dart.

A través de un contador interactivo, se puso en práctica el manejo de estados, la respuesta a eventos del usuario y la actualización automática de los elementos visuales.

Asimismo, se reforzó la importancia de organizar el código mediante componentes reutilizables y de mejorar la experiencia del usuario con elementos visuales dinámicos.

Esta actividad representa una introducción al desarrollo móvil y proporciona una base para la creación de aplicaciones más completas e interactivas.

---

## 🔗 Enlace del proyecto

<p align="center">
  🌸 <strong>Práctica 02 — Desarrollo Móvil Integral</strong> 🌸
  <br><br>
  <a href="https://jenniferbautistabarrios.github.io/Pr-cticas_DMI_230317/Practica02/arquitectura/index.html">
    <img src="https://img.shields.io/badge/🏗️_Ver_Arquitectura_del_Proyecto-FF69B4?style=for-the-badge" alt="Ver arquitectura del proyecto"/>
  </a>
  <br><br>
  <a href="https://jenniferbautistabarrios.github.io/Pr-cticas_DMI_230317/Practica02/arquitectura/index.html">
    Ver modelo de arquitectura del proyecto
  </a>
</p>

---

<p align="center">
  💗✨ <em>Práctica realizada como parte del aprendizaje de Desarrollo Móvil Integral.</em> ✨💗
</p>
