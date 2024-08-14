# NOTAS INTELIGENCIA ARTIFICIAL 2430

- [NOTAS INTELIGENCIA ARTIFICIAL 2430](#notas-inteligencia-artificial-2430)
  - [18/07/24](#180724)
  - [30/07/24](#300724)
  - [1/08/24](#10824)
  - [6/08/24](#60824)
  - [8/08/24](#80824)
  - [13/08/24](#130824)

## 18/07/24

- machine learning
  - antes del 2012, se sacaban caracteristicas de la imagen.
  - el campo de estudio que le da a los computadores la abilidad de aprender sin ser programados.
  - el gran problema de los algoritmos de ML es un problema de interpretabilidad.
  - para construir un modelo, se necesitan datos, se presentan datos hasta que el modelo mejore, es un ataque a fuerza bruta.
  - ML se encarga de encontrar representaciones adecuadas de los datos de entrada, para facilitar la realizacion de una tarea.
  - se llegó a un punto en donde hay muchos datos, se esta cambiando el paradigma a la necesidad dde datos de calidad
  - metodo para alcanzar la inteligencia artificial
  - deep learning es para tareas complejas, saca conclusiones de los datos, que sus creadores no se esperaban.
  - la IA nace con las derivadas, el calculo y la maximizacion y minimizacion de funciones.

## 30/07/24

- regresion lineal
  - encontrar unba funcion que mapee unos datos de entrada con datos de salida
  - REVISAR EL NOTEBOOK QUE NOS VAN A PASAR
  - aprendizaje supervisado: a mis datos de entrada yo les mapeo un valor de salida
  - es muy immportante primero entender el problema que se va a tratar
  - la variable objetivo en la regresion es continua
  - estructura entre la relacion de las variables: tendencia
  - evaluar si los resultados tienen sentiodo o no
  - siempre en las graficas hay que poner titulo y ejes
    - el modelo mas sencillo está dado por una ecuacion, está en el notebook, theta son los parametros del modelo
    - h es la hipotesis
    - theta es el vector de parametros
    - x: entrada del modelo
  - LAS LETRAS EN NEGRITA Y MINUSCULA SON VECTORES
  - m numero de observaciones, para este caso numero de casas
  - debe haber una metrica de rendimiento, que tan bien mi modelo hace las cosas
  - costo, en su mayoria esta relacionado con error. se plantea con el cuadrado de todos los errores. responde al costo que incurre el modelo por seleccionar un conjunto de parametros thea
  - se usa la distancia euclidea, la raiz de la suma de los elementos al cuadrado
  - la distancia de manhattan usa los cuadros de la grilla
  - s. t. subject to.
  - encontrar theta0 y theta1 es lo que conocemos como aprendizaje automatico de maquinas
  - el conocimiento de mi modelo (lo que mi modelo sabe), esta en los pesos de los parametros
  - pensar siempre en vectores columna
- PROXIMA CLASE INTERPRETAR SOLUCION ALGEBRAICA, REPASAR ESPACIO DE COLUMNAS DE MATRIZ!

## 1/08/24

- no usar el ambiente base de python para trabajar, crear uno propio
- la concentracion de datos es como la gravedad, jala los datos
- espacio vectorial
  - conjunto de vectores que satisfacen 3 condiciones
    - si x pertenece al espacio a.x tambien pertenece al espacio
    - si x e y pertenecen al espacio, x+y tambien deben pertenecer al espacio
    - el elemento nulo pertenece al espacio
- hay subespacios es una sola linea de R2, por ejemplo
- una base debe ser un conjunto de vectores independientes
- el espacio es el vector normal al plano que yo arme
- y no está en el espacio de columna de a, no hay forma de que encuentre h tal que el error sea 0, el menor punto que puedo obtener es la recta entre el punto y el plano
- el problema de regresion es proyectar el vector objetivo, el target, y sobre el espacio de columnas de la matriz de diseño.
- La matriz A, puede cambiar el espacio de columnas, define la estructura del modelo, define donde va a estar la solución.
- vamos a ver una interpretacion geometrica en clase
- LEER PDF DE CALCULO MATRICIAL - ESTÁ EN TRABAJO DE CLASE
- GRADIENTE DESCENDIENTE: la manera de entrenar la mayoria de modelos de ML hoy en día
  - responde la pregunta ¿como bajar mas rapido la montaña? hasta llegar al punto mas bajo posible
  - el gradiente siempre apunta al maximo y la direccion de mayor variación
  - para saber cuantos pasos avanzo uso otra funcion
  - tengo que preguntar constantemente si ya estoy en el punto mas bajo posible, si estoy rodeado de montañas
  - alpha es la tasa de aprendizaje, me dice el paso que debo dar
  - theta1 y 0 se inicializan aleatoriamente

## 6/08/24

- Gradiente Descendiente 2: la venganza
  - la tasa de aprendizaje siempre es +, nunca -
  - el paso se vuelve mas pequeño, poruqe la derivada va cambiando, se vuelve mas pequeña
  - al entrener modelos no se conoce la superficie de costo, para saber si se converge al minimo es menester tener claridad sobre la geometría
  - si el cambio es pequeño, la convergencia al minimo se demora mucho mas
  - la tasa apropiada (just right) tiene pocos saltos
- solo puedo graficar dos parametros, una epoca es mostrar todos los datos que yo tengo al modelo
- si el costo en el modelo que estamos entrenando es muy alto, toca bajar la tasa de aprendizaje
- cuando se estanca la curva, esta oscilando, la tasa de aprendizaje hizo que los polos del sistema queden sobre el circulo unitario.
- gradiente sube o baja la funcion para que haya iguales errores arriba y abajo de la curva
- el grad. desc, se usa en todo lado porque es sencillo
- como usar grad. desc:
  - proponer el modelo lineal (la matriz A refleja la estruc del modelo)
  - definir un theta inicial aleatoriamente
  - estimar salida del modelo para ese theta h=A*theta
  - encontrar el error
  - actualizar el theta = theta - (alpha/m)xA^t*e
  - goto 3 until convergence
    - crieterios de parada:
      - ubmral de error
      - no hay cambio en theta
  - util: no actualizar h! solo se vuelve a calcular cuando se actualizan los parametros
- REGRESION MULTIVARIABLE:
  - *Que el modelo sea lineal en ML, no significa que la relacion entre entrada y salida es lineal, sino que la relacion entre los parametros del modelo y la salida del modelo es lineal.*
  - YAYYY LA LINEA 100 YAAAYY
  - se aplica gradiente descendiente de forma normal
    - theta = theta - (alpha/m)xA^t*e
  - el hiper plano que me de va a estar en la mitad de los datos
  - la pendiente va a ser perpend. al error que veo desde Xd,o sea soy perpendicular al espacio columna de la matriz A (la matriz que define mi modelo).
  - pensar en expansion por serie de taylor, la funcion debe ser derivable (suave, su derivada es continua)
  - dependiendo del modelo utilizado, asi mismo van a ser las caracteristicas de las funciones que encuentre.
    - usar grad descendiente o svm
  - las redes neuroanles pueden aproximar funciones discontinuas
TAREA PARA EL 19/08 11:59 pm-> IMPLEMENTAR GRAD. DESC indivin
  IMPLEMENTAR EN NOTEBOOK DE JUPYTER EN PYTON
  DEBE SER INTERACTIVA (MIRAR IPYWIDGETS, BARRAS DESLIZANTES, Y ETC.)
  GRAFICAR LA FUNC. DE COSTO.
  USAR DATOS DEL EXCEL EN TRABAJO DE CLASE
  revisar programacion funcional, hacer muchas funciones super sencillas pequeñas

## 8/08/24

- clasificación lineal, el objetivo si tengo una grfaica cuyo eje x es tamaño del tumos y el eje y sea clasificación (si la persona tiene o no cancer), debo encontrar un modelo que tomando como entrada el tamaño del tumor me indique si la persona tiene o no cancer
- vamos a usar un comparador, todo lo que este debajo de 0.5 no tiene cancer, todo lo que esté arriba tiene cancer
- hay 2 problemas de usar regresion para un clasificador
  - la salida deseada es acotada y el modelo de regresion que uso no es acotado
  - tengo outliers (datos atipicos)
    - cuando cambio en umbral, cambia la sensibilidad en detección
- siempre que haya un problema de clasificación, no es bueno usar regresion porque no se ajusta bien
  - pero, siempre hay excepcion a la regla, hay una regresion que si se usa
    - LDA (linear Discriminant Analysis)
      - la proyeccion es un producto . ortogonal
      - la idea detrás de LDA es proyectar los datos sobre una direccion, de tal forma que se cumplan 2 cosas
        - la distancia entre las medias de las distribuciones proyectada, sea lo mas grande posible
        - la varianza entre los elementos que pertenecen a la misma clase sea lo mas pequeña posible
      - LDA encuentra la direccion en la cual suceden las dos condiciones anteriores
      - es muy dificil hacer clasificadores perfectos (>97% accuracy)
      - como plantear LDA
        - quiero max la distancia entre las medias de las proyecciones
          - proyectar y calcular la media es lo mismo que calcular y proyectar
          - uso la matriz de covarianza
        - quiero minimizar la varianza intraclase, quiero que se lo mas pequeña posible
        - sumamos el tetha0, porque corre los elementos a la izq o a la der, porque quiero poner 0 en la mitad de los 2

## 13/08/24

- para solucionar el problema de usar regresion en un clasificador, se usa regresion logística
- la funcion logistica
  - tiene salida continua
  - es un método de clasificación, a pesar de que se conoce como regresión
  - el span (región de la pendiente, transicion entre 0 y 1 de la func) depende de los valores de theta1, theta0 controla el movimiento horizontal de la logistica
    - cuando veamos redes neuronales, el span va a ser importante para la inicialización
  - ML en general: la ciencia que mapea datos de entrada a datos de salida
    - la diferencia está en la variable de salida
  - hablamos de una regresion logistica, porque la salida del modelo es continua, es de clasificacion porque lo entreno con datos cuya salida es discreta.
  - puedo interpretar la salida como una probabilidad, a medida que avanzo en la funcion, la P(xeC1).
  - Uso una funcion de transformación para hacer el dual (repasar video de clase si tengo dudas)
  - la desventaja es que debo saber que funcion me separa las dos clases
  - para regresion se usa alguna medida de error, para clasificacion usar cross entropia como func. de costo
