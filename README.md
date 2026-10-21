[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=DrPaulValle/MSFBP0)

# Práctica 2: Modelado y control del sistema cardiovascular mediante el modelo Windkessel

## Información de la estudiante
Nombre completo: Marcos Ancelmo Naranjo Rivera [L23212218@tijuana.tecnm.mx]

Modelado de Sistemas Fisiológicos

Ingeniería Biomédica

## Docente
Dr. Paul Antonio Valle Trujillo; paul.valle@tectijuana.edu.mx

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México/IT Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

## Descripción de la asignatura

El modelizado de sistemas fisiológicos es una herramienta importante en Ingeniería Biomédica, permite comprender el funcionamiento del cuerpo humano, así como diseñar y evaluar terapias y dispositivos médicos; se define como el proceso de formular modelos matemáticos o computacionales que representan el comportamiento y la interacción de los sistemas biológicos y fisiológicos. Esta asignatura pretende aportar al perfil del Ingeniero Biomédico la capacidad de realizar investigación científica en el área de Biología de Sistemas con la finalidad de dirigir y participar en equipos de trabajo interdisciplinarios en contextos nacionales e internacionales, así como de proporcionar soluciones informáticas para resolver problemas en el campo de la Ingeniería Biomédica con ética profesional; lo anterior al proporcionar al estudiante bases sólidas para modelizar sistemas y diseñar controladores para la solución de problemas en las áreas de atención médica y del sector industrial médico. La construcción de analogías entre circuitos eléctricos y sistemas fisiológicos para la formulación de modelos matemáticos y el diseño de controladores mediante la experimentación in silico brindan herramientas de gran aplicación en el quehacer profesional del Ingeniero Biomédico.

La asignatura de Modelado de Sistemas Fisiológicos forma parte del plan de estudios de la carrera en Ingeniería Biomédica con la siguiente competencia general del curso: Utiliza las propiedades de los circuitos RLC para describir la dinámica de sistemas fisiológicos, obtener modelos matemáticos y aplicar el control clásico, esto con el objetivo de integrar los principios de la Ingeniería de Control, la Electrónica Analógica y las Ciencias de la Computación con la Anatomía y Fisiología del cuerpo humano para proporcionar descripciones cuantitativas y cualitativas de sistemas fisiológicos complejos con el objetivo de modelizar, analizar, controlar, ilustrar y predecir su dinámica tanto en el corto como en el largo plazo.

## Objetivos

1. Identificar las variables y los parámetros del modelo Windkessel de cuatro elementos y relacionarlos con las propiedades hemodinámicas que representan.
2. Obtener las funciones de transferencia de los modelos normotenso, hipertenso e hipotenso.
3. Analizar la estabilidad en lazo abierto de cada caso mediante la localización de sus polos y determinar el error en estado estacionario.
4. Determinar el modelo de ecuaciones integro diferenciales del circuito.
5. Implementar los modelos en MATLAB/Simulink, representar las funciones de transferencia, el modelo de ecuaciones integro diferenciales, el circuito eléctrico normotenso mediante Simscape y el modelo de EDOs en el cuaderno computacional de MATLAB.
6. Simular la respuesta del modelo normotenso a una señal aleatoria y utilizar su salida como entrada de los modelos hipertenso e hipotenso sin controlador para comparar las respuestas de los tres individuos.
7. Diseñar y sintonizar dos controladores PID independientes para reducir las diferencias de los casos hipertenso e hipotenso respecto a la respuesta normotensa.
8. Comparar, para cada caso, la respuesta normotensa, la respuesta sin controlador y la respuesta con PID, considerando el seguimiento de la referencia, el error y el comportamiento transitorio.
9. Implementar las funciones de transferencia y los sistemas controlados en Python mediante Visual Studio Code y comparar sus resultados con los obtenidos en MATLAB.
10. Elaborar un diagrama en BioRender que relacione los componentes del modelo con las estructuras cardiovasculares y documentar los análisis, las simulaciones y los parámetros de los controladores en el repositorio.

## Descripción detallada del sistema

En esta práctica se estudia el modelo Windkessel de cuatro elementos para representar la dinámica arterial mediante un circuito eléctrico, donde el voltaje equivale a la presión y la corriente al flujo sanguíneo. Z representa la impedancia característica arterial, L la inertancia de la sangre, C la distensibilidad arterial y R la resistencia periférica. Z y L están conectados en paralelo entre la entrada y la salida, mientras que C y R se conectan en paralelo entre la salida y la referencia. El sistema es de segundo orden porque L y C almacenan energía de manera independiente.

Se analizan los casos normotenso, hipertenso e hipotenso manteniendo constantes Z, L y R y modificando C a 1.5, 1.0 y 3.5 ml/mmHg, respectivamente. Estos valores representan diferentes capacidades de distensión y almacenamiento de volumen arterial. El análisis matemático comprende la función de transferencia del circuito, la estabilidad en lazo abierto de cada caso, el error en estado estacionario y, posteriormente, el modelo de ecuaciones integrodiferenciales.

En Simulink se implementa el circuito normotenso mediante la función de transferencia, modelo d ecuaciones integro diferenciales y circuito eléctrico y se aplica una señal aleatoria entre −0.2 y 1, con semilla 106, muestreo de 0.1 s y duración de 15 s. La salida normotensa se utiliza como entrada de los modelos hipertenso e hipotenso sin controlador y como referencia de dos lazos de control independientes. En cada lazo, un PID compara la referencia con la salida del caso correspondiente y genera la entrada del modelo a partir del error. Las ganancias se sintonizan por separado para mejorar el seguimiento de la respuesta normotensa.

El cuaderno computacional de MATLAB incluye las funciones de transferencia y el modelo de EDOs, trabajado únicamente en MATLAB; en Python se implementan las funciones de transferencia y los sistemas controlados. Las gráficas de Individuos comparan las respuestas normotensa, hipertensa e hipotensa sin controlador, mientras que las de Hipertenso e Hipotenso muestran la referencia normotensa, el caso sin controlador y su respuesta con PID. MATLAB incluye además la gráfica Individuos EDOs, dando un total de cuatro gráficas en MATLAB y tres en Python. Estas permiten comparar las implementaciones y evaluar el comportamiento transitorio y el efecto del control. Finalmente, el diagrama de BioRender relaciona los componentes del circuito con las estructuras y propiedades cardiovasculares que representan.

Palabras clave: Modelo Windkessel; Sistema cardiovascular; Controlador PID; Modelo matemático; Simulaciones numéricas.

## Lista de archivos incluidos en el repositorio
1. Diagrama biológico elaborado en BioRender.
2. Cuaderno computacional de MATLAB [.mlx y .pdf].
3. Imágenes con los parámetros de los controladores hipertenso e hipotenso.
4. Análisis matemático: función de transferencia del circuito, estabilidad en lazo abierto de cada caso, error en estado estacionario y modelo de ecuaciones integro diferenciales.
5. Archivo de la señal de entrada [signa.xlsx].
6. Código de Python [.py].
7. Imágenes de las simulaciones en Python (3): Individuos, Hipertenso e Hipotenso.
8. Imágenes de las simulaciones en MATLAB (4): Individuos, Individuos EDOs, Hipertenso e Hipotenso.
## Referencias
\[1] P. A. Valle, Syllabus para Modelado de Sistemas Fisiológicos, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: https://biomath.xyz/course/

\[2] M. C. Khoo, Physiological Control Systems Analysis Simulation, and Estimation, 2nd ed. Piscataway, New Jersey, USA: IEEE Press, 2018, Section 4, Page 93.

\[3] N. S. Nise, Control Systems Engineering, 8th ed. Hoboken, New Jersey, USA: John Wiley & Sons, 2020.
