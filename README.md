
# Proyecto: Formulario Interactivo con Vue 3

### Autor: Gonzalo Román Reyes  
### Repositorio: https://github.com/GRomanD3v/M6AE3-ABP3.git

---

## Descripción del Proyecto 
Este proyecto es una aplicación web interactiva que utiliza Vue 3 y Bootstrap 5 para demostrar la implementación de formularios de datos reactivos. El objetivo principal es mostrar cómo se puede capturar y visualizar el estado de diferentes controles de entrada en tiempo real, utilizando la Composition API de Vue. La aplicación está construida de forma modular, encapsulando la lógica del formulario en un componente reutilizable.

---

## Requisitos de la Actividad y su Cumplimiento

La actividad solicitaba la implementación de dos tipos de controles de formulario para capturar datos de usuario. A continuación, se detalla cómo se cumplieron estos requisitos utilizando las prácticas modernas de Vue y Bootstrap.

### 1. Manejo de Controles de Tipo radio
Requerimiento: Crear cuatro controles de tipo radio para seleccionar el nivel de estudios del visitante (Educación Básica, Educación Media, Educación Técnica y Educación Universitaria) y mostrar la opción seleccionada.

### Cumplimiento:

- v-model y ref(): La propiedad estudios se declara como una referencia reactiva (ref) en el ```<script setup>```. La directiva v-model se encarga de enlazar todos los controles de radio a esta única referencia. Esto permite que Vue actualice automáticamente la propiedad estudios con el value del radio button seleccionado, garantizando que solo una opción esté activa a la vez.

- v-for: Para un código más limpio y escalable, los controles de radio se renderizan dinámicamente. Se utiliza la directiva v-for para iterar sobre un array de objetos llamado opcionesEstudios, creando un input de radio por cada nivel de educación.

- Visualización de Datos: El valor actual de la referencia estudios se muestra en la interfaz (```{{ estudios }}```) para demostrar que el form binding funciona correctamente.

### 2. Manejo de Control de Tipo select

Requerimiento: Mostrar los días de la semana en un control select y visualizar la opción seleccionada por el usuario.

### Cumplimiento:

- v-model y ref(): Al igual que con los radios, la propiedad diaSeleccionado se declara como una referencia reactiva (ref). El control select se vincula a esta propiedad con v-model, lo que permite que el modelo de datos se actualice en tiempo real con la selección del usuario.

- v-for: Las opciones del menú desplegable se generan de manera dinámica a partir de un array de strings (diasDeLaSemana), lo que elimina la necesidad de escribir manualmente cada ```<option>``` en el HTML.

- Opción Guía: Se incluye una primera opción deshabilitada que sirve como texto de guía para el usuario ("Por favor, selecciona un día"), mejorando la usabilidad.

- Visualización de Datos: El valor de la referencia diaSeleccionado se muestra en la interfaz para confirmar la selección del usuario, usando un v-if para que solo aparezca cuando se haya hecho una selección.
---

### Estructura del Proyecto y Renderizado 
Para seguir las mejores prácticas de Vue, la aplicación se estructura en componentes reutilizables.

- Formulario.vue: Este es un componente de un solo archivo que encapsula toda la lógica y la interfaz de usuario del formulario. Utiliza la sintaxis ```<script setup>``` de Vue 3, que simplifica la declaración de variables reactivas (ref) y su exposición a la plantilla.

- App.vue: El componente principal de la aplicación. Se encarga de importar y renderizar el componente Formulario.vue, demostrando cómo se pueden construir aplicaciones complejas a partir de componentes más pequeños.


