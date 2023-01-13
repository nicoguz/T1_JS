# Tarea 1

## Notas Generales
* Todo lo que esté despues de un "//" es un comentario (se ignora cuando se corre el código)
* Recomiendo descargarse VSCode para escribir código y hacer cada ejercicio en un archivo separado. ([Tutorial](https://www.youtube.com/watch?v=2RoWZXcbPjw), ver hasta 2:32)
* Recomiendo instalar las extensiones de VSCode para JavaScript y lo necesario para correr JavaScript en tu pc. ([Tutorial](https://www.youtube.com/watch?v=5uSI2RpQ1og), ver hasta 6:19)
* Si quieres probar tu código puedes hacerlo [aquí](https://www.programiz.com/javascript/online-compiler/) o usar la extensión del punto anterior.
---
## 1. Estás en disney con tus amigos y te has subido a todos los juegos que querías excepto por uno D : !!! Frustrada por no poder subirte al carrucel del rey león decides al llegar a tu casa crear un programa que te haga ver el mundo como si todo diera vueltas en circulos. Crea una función que reciba un `string` y devuelva el mismo string pero con la última letra al inicio.  
  ¡¡OJO!! El programa no debe considerar los espacios al inicio o final de la palabra.
  
  Por ejemplo:
  ```
  input: "  hola    "
  output: "ahol"

  rotar("hola") --> ahol
  ```

  Hint: Para acceder a una letra de un string se debe hacer de la misma manera que para una lista. Los strings y listas se comportan muy parecido en cuanto a posiciones.

  Copia y pega tu función aquí para dar vueltas en el carrucel :D (ejecutalo en [este link](https://www.programiz.com/javascript/online-compiler/))
  ```
  let palabra = "Hakunna Matatta :D";
  def rotar(palabra){}
  while(1) {
    console.log(palabra);
    palabra = rotar(palabra);
  }
  ```

<details>
  <summary style="font-size: 170%">Solución</summary>
  
  * Primero definimos la función:
  ```
  def rotar(palabra) {

  }
  ```
  * Después debemos eliminar los espacios en blanco de la palabra. Esto se puede hacer fácilmente con el metodo `trim()` de los strings o haciendo un while que revise la primera letra de la palabra. Si la letra es " " (espacio) entonces cortamos la primera letra y volvemos a revisar. Lo mismo con la última letra.
  * Luego tomamos la palabra y usando el hint tomamos la última letra de la palabra. Recordar que la posición del último elemento de una lista es el largo de esta - 1. Lo mismo ocurre para los strings:  
  `let posicion_letra = palabra.length - 1`  
  `let ultima_letra = palabra[posicion_letra]`

  * Ahora que tenemos la última letra lo único que tenemos que hacer es ponerla al inicio de la palabra y eliminar la última letra (o seleccionar toda la palabra excepto por la última letra).

    Esto se puede hacer de múltiples formas (investigar "string slice" y "substring"). Por simplicidad aquí se utilizará substring. Así

    `let nueva_palabra = ultima_letra + palabra.substring(0,posicion_letra - 1)`
  
  * Por último retornamos la nueva palabra:  
  `return nueva_palabra`

  Así, la solución quedaría:  
  ```
  def rotar(palabra) {
    let palabra_limpia = palabra.trim()
    let posicion_letra = palabra_limpia.length - 1
    let ultima_letra = palabra_limpia[posicion_letra]
    let nueva_palabra = ultima_letra + palabra_limpia.substring(0,posicion_letra - 1)

    return nueva_palabra
  }
  ```
</details>  

---

## 2. Un día de aburrimiento en tu casa te preguntas ¿Cuantas veces tendré que doblar un papel hasta que mida 1 cm? Como no quieres contaminar el planeta, en vez de doblar papeles decides escribir un programa que te ayude a solucionarlo. Escribe un programa que recibe un número y va dividiendo de dos en dos hasta llegar a 1 con las siguientes restricciones:
  * Si algún numero resulta ser impar sumale 1 para que la división sea entera.
  * Si el número resultante de alguna división llegase a ser "11" el programa debe terminar inmediatamente imprimiendo "No me gusta el número 11 >:(".
  * Cuando llegues a 1 debes terminar el programa e imprimir la cantidad de veces que se dividió el número en 2

  Hint: Los loops te serán útiles aquí aunque uno es más simple para este problema que otro.  
  Hint 2: Recordar la operación resto. Puede ser útil para ver si un número es par o impar.  

  Fun fact: El resultado es el techo de log2 del número :O !!!

<details>
  <summary style="font-size: 170%">Solución</summary>
  
  * En primer lugar, escribimos el número a utilizar (esto puede ser una variable creada por nosotros)
  `let numero = 45;`

  * Luego utilizamos el loop `while` de la siguiente forma:
  ```
  // Creamos un contador para ver cuantas veces dividimos en 2 el número
  let contador = 0

  while (numero > 1) {

    // Primero debemos revisar si el número es 11
    if (numero == 11) {
      console.log("No me gusta el número 11 >:(");
      // Terminamos el loop
      break;
    }

    // Revisamos si el número es impar o par viendo el resto de la division con 2. 
    // Si el resto es 1 entonces es impar.
    if (numero%2 == 1) {
      numero += 1
    }

    // Si llegamos acá es porque el número aun sigue siendo mayor que 1 y no es 11
    numero = numero / 2;
    contador += 1;
  }

  console.log(contador)
  ```
</details>

---

## 3. Felicidades!! Has ganado un ticket con todo pagado a un crucero matemático!! Como a ti te encantan las matemáticas aceptas ir con gusto y decides llevar todos tus números favoritos en tu maleta. Crea una función que recibe una lista (tu maleta) y se asegura que todos los números del 1 al 9 estén dentro. En específico:

* La función debe revisar que se encuentren todos los números del 1 al 9 por separado.
* Si algún número no está en la maleta debes meterlo. El orden no importa.
* Si encuentras algún elemento que no sea un número debes sacarlo de la maleta (no queremos que nos cobren demás por sobrepeso en la maleta D: )
* La función debe retornar una lista con solo los números del 1 al 9 que ya estaban presentes y otra lista con los números faltantes.

Hint: Existe una función para conocer el tipo de un elemento (esto podría servir para ver si es basura o no). Puedes asumir que no habrán numeros fuera del rango 1 a 9 en la lista inicial.

Hint 3: Puedes usar cuantas listas quieras en el proceso para llegar a tu resultado, pero debes retornar solo las 2 especificadas.

Hint 3: Para poder retornar más de un elemento en una función puedes usar una lista. Es decir, retornar `[lista 1, lista 2]`

<details>
  <summary style="font-size: 170%">Solución</summary>
  
  * Definimos la función
  ```
  def revisar_maleta(maleta) {
  }
  ```
  * Primero podemos limpiar la maleta de cualquier elemento que no sea un número.

  ```
  // Aquí utilizaremos otra lista donde solo meteremos números presentes en la otra lista
  let numeros_iniciales = []

  for (let i=0; i < maleta.length; i += 1) {
    // typeof retorna un string con el nombre del tipo de variable (investigar que nombres puede retornar)
    if (typeof maleta[i] == 'number') {
      // Añadimos el número a la otra lista
      numeros_iniciales.push(maleta[i])
    }
  }
  ```
  * Ahora `numeros_iniciales` ya tiene todos los números presentes en la lista inicial. Solo queda revisar qué números faltan

  ```
  // Definimos una lista para los números faltantes
  let numeros_faltantes = [];

  for (let i=1; i <= 9; i += 1) {
    // Si el número i-ésimo no se encuentra en la lista, lo ponemos como faltante (investigar 'includes()')
    if !(numeros_iniciales.includes(i)) {
      numeros_faltantes.push(i)
    }
  }
  ```

  * Por último, retornamos ambas listas, dejando la solución de la siguiente manera:  
  ```
  def revisar_maleta(maleta) {
    // Aquí utilizaremos otra lista donde solo meteremos números presentes en la otra lista
    let numeros_iniciales = []

    for (let i=0; i < maleta.length; i += 1) {
      // typeof retorna un string con el nombre del tipo de variable (investigar que nombres puede retornar)
      if (typeof maleta[i] == 'number') {
        // Añadimos el número a la otra lista
        numeros_iniciales.push(maleta[i])
      }
    }

    // Definimos una lista para los números faltantes
    let numeros_faltantes = [];

    for (let i=1; i <= 9; i += 1) {
      // Si el número i-ésimo no se encuentra en la lista, lo ponemos como faltante
      // (investigar 'includes()')
      if !(numeros_iniciales.includes(i)) {
        numeros_faltantes.push(i)
      }
    }

    return [numeros_iniciales, numeros_faltantes]
  }
  ```

  
</details>