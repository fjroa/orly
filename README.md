orly
====
Este proyecto consiste en una aplicación que genere de manera automática composiciones gráficas de tipo orla de graduación que pueda ser facilmente personalizable y configurable, utilizando tecnologías web para su tratamiento y posicionamiento. La particularidad del sistema es la automatización del proceso de captura fotográfica.

Análisis
========
El proyecto se encuentra en su fase de análisis inicial en la que se está definiendo el proceso que seguirá la aplicación. Para iniciar se considererá un proyecto tipo estándar de orla usando como referencia una orla de la Universidad de Jaén (https://lh3.googleusercontent.com/u-dMIlHe2knVMChGkXDbRVx_3rjuI05KJcADtAz3M1w).

Podemos ver que una orla se compone de:
  - Marco que engloba la composición. Dispone de una identificación de la universidad y abajo consta de la promoción
  - Cuerpo de fotografía, que esta dividido a su vez en:
    - Parte Superior: Consta de los logotipos de la universidad y de la facultad correspondiente a cada lado, y en el centro se encuadran las fotografías de los profesores que impartieron la titulación. Encima se muestra el título de la facultad.
    - Nombre de la titulación cursada, en la zona central diviendo ambas partes
    - Parte Inferior: Consta de las fotografías de los alumnos que se graduaron ese año.

A su vez, las fotografías tienen una forma que se repite:

  - Imagen : retrato de la persona, que viene adornado con un recorte oval. La imagen muestra la cabeza completa y el cuerpo en proporción 2:3
  - Pie de fotografía: Tiene 3 líneas centradas compuestas por el nombre, apellidos y ciudad (provicia).

Tareas
======

Se realizará una apilcación web basada en AngularJS para el tratamiento de las imágenes basado en la librería ng-grid-panel https://github.com/Hacklone/ng-grid-panel como componente principal para el posicionamiento de las imagenes. Para el recorte se utilizara css.

Lo ideal sería utilizar la librería OpenBR para localizar el punto medio que divide los ojos de la persona fotografiada. La idea es utilizar una herramienta similar a https://github.com/jonom/jquery-focuspoint para realizar el recorte de las imagenes basado en los puntos focales devueltos por OpenBR. De este modo nos aseguramos que las fotografías se amolden correctamente de forma responsiva, además de permitir realizar una orla a partir de una fotografía grupal. 

Para capturar los datos se implentará un formulario html y habrá distintas formas de ordenación de las fotografías dependiendo de los datos, permitiendo el posicionamiento dinámico de las fotos mediante el click del ratón.

Se necesitan los recursos del marco de tipo vectorial o de tipo css si fuera posible. Los logotipos serían imagenes estáticas.

Las fotografía en cada parte indicada anteriormente serán obligatoriamente del mismo tamaño y con el mismo tipo de letra y tamaño. El tamaño vendrá determinado por el número de elementos que haya para que se respeten unas proporciones (basadas en una fórmula) que también será configurable. Esto abre la puerta a diversos templates y formas diferentes de orla. La fórmula para este caso en concreto está en proceso de análisis.

Finalmente habrá un servicio web que nos entregue la orla en formato imprimible del tamaño que nosotros le indiquemos.

En el futuro se pretende que una aplicación móvil que recoja las imágenes obtenidas directamente desde la cámara del dispositivo y automatice todo el proceso en la nube.
