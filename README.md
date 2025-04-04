# Introducción a Kotlin: Problemas prácticos
Alumno: Bryan Edgard Ochoa Trillo

Código: 17200126

## 1. Impresión de mensajes
¿Puedes escribir una función main() que imprima estos mensajes en cuatro líneas separadas?
```
Use the val keyword when the value doesn't change.
Use the var keyword when the value can change.
When you define a function, you define the parameters that can be passed to it.
When you call a function, you pass arguments for the parameters.
```
**Solución**: [https://pl.kotl.in/2MD7zhxqA](https://pl.kotl.in/2MD7zhxqA)
``` kotlin
fun main() {
	println("Use the val keyword when the value doesn't change.")
	println("Use the var keyword when the value can change.")
	println("When you define a function, you define the parameters that can be passed to it.")
	println("When you call a function, you pass arguments for the parameters.")
}
```

## 2. Corrección de un error de compilación
Este programa imprime un mensaje que le notifica al usuario que recibió un mensaje de chat de un amigo.
``` kotlin
fun main() {
    println("New chat message from a friend'}
}
```
¿Puedes determinar la causa raíz de los errores de compilación de este programa y corregirlos?
¿El código usa los símbolos apropiados para indicar la apertura y el cierre de la cadena y el argumento de la función?
Pista: Puedes usar Kotlin Playground a fin de ejecutar el código y ver los errores de compilación.

Después de corregir los errores, el programa debe compilarse sin problemas y, luego, imprimir este resultado:
```
New chat message from a friend
```
**Solución**: [https://pl.kotl.in/iJD-Oa4bk](https://pl.kotl.in/iJD-Oa4bk)
```kotlin
fun main() {
    println("New chat message from a friend")
}
```

## 3. Plantillas de strings
Este programa informa a los usuarios sobre la próxima oferta promocional de un artículo en particular. Tiene una plantilla de cadenas, que se basa en la variable discountPercentage para el porcentaje de descuento y la variable item para el artículo en oferta. Sin embargo, existen errores de compilación en el código.
``` kotlin
fun main() {
    val discountPercentage: Int = 0
    val offer: String = ""
    val item = "Google Chromecast"
    discountPercentage = 20
    offer = "Sale - Up to $discountPercentage% discount on $item! Hurry up!"

    println(offer)
}
```
¿Puedes determinar la causa raíz de esos errores y corregirlos?
¿Puedes determinar el resultado de este programa antes de ejecutar el código en Kotlin Playground?
Pista: ¿Puedes reasignar un valor a una variable de solo lectura?

Después de corregir los errores, el programa debe compilarse sin problemas y, luego, imprimir este resultado:
```
Sale - Up to 20% discount on Google Chromecast! Hurry up!
```
**Solución**: [https://pl.kotl.in/rfL410hP5](https://pl.kotl.in/rfL410hP5)
``` kotlin
fun main() {
    var discountPercentage: Int = 0
    var offer: String = ""
    val item = "Google Chromecast"
    discountPercentage = 20
    offer = "Sale - Up to $discountPercentage% discount on $item! Hurry up!"

    println(offer)
}
```
## 4. Concatenación de strings
Este programa muestra una cantidad total de personas en una fiesta. Entre ellas, hay adultos y niños. La variable numberOfAdults contiene la cantidad de adultos en el grupo, y la variable numberOfKids, la cantidad de niños.
``` kotlin
fun main() {
    val numberOfAdults = "20"
    val numberOfKids = "30"
    val total = numberOfAdults + numberOfKids
    println("The total party size is: $total")
}
```
Paso 1
¿Puedes determinar el resultado de este programa antes de ejecutar el código en Kotlin Playground?

Rpta: `The total party size is: 2030`

Después de determinar el resultado, ejecuta el código en Kotlin Playground y, luego, verifica si el resultado coincide con el que se muestra.

Pista: ¿Qué sucede cuando usas el operador + en dos cadenas?

Paso 2
El código funciona y, además, imprime algunos resultados, pero los resultados no muestran la cantidad total de personas que asistirán a la fiesta.

¿Puedes encontrar el problema del código y corregirlo de modo que imprima este resultado?
```
The total party size is: 50
```
**Solución**: [https://pl.kotl.in/vN3L5vfCW](https://pl.kotl.in/vN3L5vfCW)
``` kotlin
fun main() {
    val numberOfAdults = 20
    val numberOfKids = 30
    val total = numberOfAdults + numberOfKids
    println("The total party size is: $total")
}
```

## 5. Formato de mensajes
Este programa muestra el salario total que recibe un empleado este mes. El salario total se divide en dos partes: la variable baseSalary, que es lo que el empleado recibe todos los meses, y la variable bonusAmount, que es una bonificación adicional otorgada al empleado.
``` kotlin
fun main() {
    val baseSalary = 5000
    val bonusAmount = 1000
    val totalSalary = "$baseSalary + $bonusAmount"
    println("Congratulations for your bonus! You will receive a total of $totalSalary (additional bonus).")
}
```
¿Puedes determinar el resultado de este código antes de ejecutarlo en Kotlin Playground?

Rpta: `Congratulations for your bonus! You will receive a total of 5000 + 1000 (additional bonus).`

Cuando ejecutas el código en Kotlin Playground, ¿se imprime el resultado que esperabas?

link: [https://pl.kotl.in/OfQ5s7ANc](https://pl.kotl.in/OfQ5s7ANc)

## 6. Implementación de operaciones matemáticas básicas
En este ejercicio, escribirás un programa que realice operaciones matemáticas básicas y, luego, imprima el resultado.

### Paso 1
La función main() contiene un error de compilación:
``` kotlin
fun main() {
    val firstNumber = 10
    val secondNumber = 5

    println("$firstNumber + $secondNumber = $result")
}
```
¿Puedes corregir el error de modo que el programa imprima este resultado?
```
10 + 5 = 15
```
**Solución**: [https://pl.kotl.in/vixC2Rx43](https://pl.kotl.in/vixC2Rx43)
``` kotlin
fun main() {
    val firstNumber = 10
    val secondNumber = 5
    
    println("$firstNumber + $secondNumber = ${firstNumber + secondNumber}")
}
```
### Paso 2
El código funciona, pero la lógica para sumar dos números se encuentra dentro de la variable de resultado, lo que hace que el código sea menos flexible a la hora de volver a usarlo. En su lugar, puedes extraer la operación de suma en una función add() para que el código se pueda volver a usar. Para ello, actualiza el código con el que se muestra a continuación. Observa que el código ahora presenta una nueva variable val, llamada thirdNumber, e imprime el resultado de esta variable nueva con firstNumber.
``` kotlin
fun main() {
    val firstNumber = 10
    val secondNumber = 5
    val thirdNumber = 8

    val result = add(firstNumber, secondNumber)
    val anotherResult = add(firstNumber, thirdNumber)

    println("$firstNumber + $secondNumber = $result")
    println("$firstNumber + $thirdNumber = $anotherResult")
}

// Define add() function below this line
```
¿Puedes definir la función add() de modo que el programa imprima este resultado?
```
10 + 5 = 15
10 + 8 = 18
```
**Solución**: [https://pl.kotl.in/SlKDsqjuZ](https://pl.kotl.in/SlKDsqjuZ)
``` kotlin
fun add(n1: Int, n2: Int): Int {
    return n1 + n2
}
```

### Paso 3
Ahora tienes una función reutilizable capaz de sumar dos números.

¿Puedes implementar la función subtract() de la misma manera en que implementaste la función add()? Modifica la función main() también para usar la función subtract(), de modo que puedas verificar que funcione como se espera.
Pista: Piensa en la diferencia entre la suma, la resta y otras operaciones matemáticas. Comienza a trabajar en el código de solución a partir de allí.

**Solución**: [https://pl.kotl.in/gOrLkLRIr](https://pl.kotl.in/gOrLkLRIr)
``` kotlin
fun subtract (n1: Int, n2: Int): Int {
    return n1 - n2
}
```

## 7. Parámetros predeterminados
Gmail tiene una función que envía notificaciones al usuario cada vez que se intenta acceder a una cuenta en un dispositivo nuevo.

En este ejercicio, escribirás un programa que muestra un mensaje a los usuarios con esta plantilla de mensaje:

`There's a new sign-in request on operatingSystem for your Google Account emailId.`

Deberás implementar una función que acepte un parámetro `operatingSystem` y un parámetro `emailId`, cree un mensaje en el formato dado y lo muestre.

Por ejemplo, si se llamó a la función con "`Chrome OS`" para el `operatingSystem` y "`sample@gmail.com`" para el emailId, se debería mostrar esta cadena:

`There's a new sign-in request on Chrome OS for your Google Account sample@gmail.com.`

### Paso 1
1. ¿Puedes implementar la función `displayAlertMessage()` en este programa de modo que imprima el resultado que se muestra?
``` kotlin
fun main() {
    val operatingSystem = "Chrome OS"
    val emailId = "sample@gmail.com"

    println(displayAlertMessage(operatingSystem, emailId))
}

// Define your displayAlertMessage() below this line.
```
2. ¿El programa imprime este resultado?

`There's a new sign-in request on Chrome OS for your Google Account sample@gmail.com.`

**Solución**: [https://pl.kotl.in/9FWZdwUh6](https://pl.kotl.in/9FWZdwUh6)
``` kotlin
fun displayAlertMessage(operatingSystem: String, emailId: String): String {
    return "There's a new sign-in request on $operatingSystem for your Google Account $emailId."
}
```

### Paso 2
Bien hecho. Mostraste el mensaje. Sin embargo, en algunos escenarios, notas que no puedes determinar el sistema operativo del usuario. En esos casos, deberás especificar el nombre del sistema operativo como `Unknown OS`. Puedes optimizar aún más el código para que no necesites pasar el argumento `Unknown OS` cada vez que se llame a la función.

1. ¿Puedes encontrar una manera de optimizar el código con esta información de modo que imprima este resultado?
```
There's a new sign-in request on Unknown OS for your Google Account user_one@gmail.com.

There's a new sign-in request on Windows for your Google Account user_two@gmail.com.

There's a new sign-in request on Mac OS for your Google Account user_three@gmail.com.
```
2. Para imprimir el mensaje anterior, reemplaza la implementación de la función `main()` por la siguiente:
``` kotlin
fun main() {
    val firstUserEmailId = "user_one@gmail.com"

    // The following line of code assumes that you named your parameter as emailId.
    // If you named it differently, feel free to update the name.
    println(displayAlertMessage(emailId = firstUserEmailId))
    println()

    val secondUserOperatingSystem = "Windows"
    val secondUserEmailId = "user_two@gmail.com"

    println(displayAlertMessage(secondUserOperatingSystem, secondUserEmailId))
    println()

    val thirdUserOperatingSystem = "Mac OS"
    val thirdUserEmailId = "user_three@gmail.com"

    println(displayAlertMessage(thirdUserOperatingSystem, thirdUserEmailId))
    println()
}
```
**Solución**: [https://pl.kotl.in/PrOakIkX5](https://pl.kotl.in/PrOakIkX5)
``` kotlin
fun displayAlertMessage(operatingSystem: String = "Unknown OS", emailId: String): String {
    return "There's a new sign-in request on $operatingSystem for your Google Account $emailId."
}
```

## 8. Podómetro
El podómetro es un dispositivo electrónico que cuenta la cantidad de pasos que se dan. En la actualidad, casi todos los teléfonos celulares, relojes inteligentes y equipos para hacer ejercicio cuentan con podómetros integrados. La app de Salud y fitness usa los podómetros integrados a fin de calcular la cantidad de pasos que se dan. Esta función calcula la cantidad de calorías que quema el usuario en función de los pasos que da.

¿Puedes cambiar el nombre de las funciones, de los parámetros de las funciones y de las variables utilizados en este programa según las prácticas recomendadas?
``` kotlin
fun main() {
    val Steps = 4000  
    val caloriesBurned = PEDOMETERstepsTOcalories(Steps);
    println("Walking $Steps steps burns $caloriesBurned calories")
}

fun PEDOMETERstepsTOcalories(NumberOFStepS: Int): Double {
    val CaloriesBURNEDforEachStep = 0.04
    val TotalCALORIESburned = NumberOFStepS * CaloriesBURNEDforEachStep
    return TotalCALORIESburned
}
```
**Solución**: [https://pl.kotl.in/5gHYvf2BI](https://pl.kotl.in/5gHYvf2BI)
``` kotlin
fun main() {
    val steps = 4000
    val caloriesBurned = pedometerStepsToCalories(steps);
    println("Walking $steps steps burns $caloriesBurned calories")
}

fun pedometerStepsToCalories(numberOfSteps: Int): Double {
    val caloriesBurnedForEachStep = 0.04
    val totalCaloriesBurned = numberOfSteps * caloriesBurnedForEachStep
    return totalCaloriesBurned
}
```

## 9. Comparación de dos números
Los teléfonos celulares modernos tienen una función integrada que registra el tiempo de uso (es decir, el tiempo que usas el teléfono cada día).

En este ejercicio, implementarás una función que compara la cantidad de minutos que usaste el teléfono hoy y ayer. La función acepta dos parámetros de números enteros y muestra un valor booleano.

El primer parámetro contiene la cantidad de minutos de uso de hoy, y el segundo, la cantidad de minutos de uso de ayer. La función muestra un valor true si pasaste más tiempo en el teléfono hoy que ayer. De lo contrario, muestra un valor false.

Por ejemplo, si llamaste a la función con estos argumentos con nombre:

- timeSpentToday = 300 y timeSpentYesterday = 250, la función muestra un valor true.
- timeSpentToday = 300 y timeSpentYesterday = 300, la función muestra un valor false.
- timeSpentToday = 200 y timeSpentYesterday = 220, la función muestra un valor false.
  
Pista: El operador de comparación > muestra un valor true si el valor anterior al operador es mayor que el que aparece después de este. De lo contrario, muestra un valor false.
**Solución**: [https://pl.kotl.in/VrfYWZ9d3](https://pl.kotl.in/VrfYWZ9d3)
``` kotlin
fun main() {
    val timeSpentToday = 300
    val timeSpentYesterday = 200
    
    if (timeSpentTodayGreaterThanYesterday(timeSpentToday, timeSpentYesterday)) {
        println("Usaste el teléfono más que ayer")
    }else {
        println("Usaste el teléfono menos que ayer")
    }
}

fun timeSpentTodayGreaterThanYesterday (timeSpentToday: Int, timeSpentYesterday: Int): Boolean {
    if (timeSpentToday > timeSpentYesterday) return true
    else return false
}
```
## 10. Movimiento del código duplicado a una función
En este programa, se muestra el clima de diferentes ciudades. Incluye el nombre de la ciudad, las temperaturas máxima y mínima del día, y las probabilidades de lluvia.

``` kotlin
fun main() {
    println("City: Ankara")
    println("Low temperature: 27, High temperature: 31")
    println("Chance of rain: 82%")
    println()

    println("City: Tokyo")
    println("Low temperature: 32, High temperature: 36")
    println("Chance of rain: 10%")
    println()

    println("City: Cape Town")
    println("Low temperature: 59, High temperature: 64")
    println("Chance of rain: 2%")
    println()

    println("City: Guatemala City")
    println("Low temperature: 50, High temperature: 55")
    println("Chance of rain: 7%")
    println()
}
```
Hay muchas similitudes en el código que imprime el clima de cada ciudad. Por ejemplo, hay frases que se repiten varias veces, como "City:" y "Low temperature:". Los códigos similares y repetidos crean el riesgo de que se produzcan errores en tu programa. Puede que hayas escrito mal una de las ciudades o que hayas olvidado uno de los detalles del clima.

¿Puedes crear una función que imprima los detalles del clima de una sola ciudad para reducir la repetición en la función main() y, luego, hacer lo mismo en las ciudades restantes?
¿Puedes actualizar la función main() a fin de llamar a la función que creaste para cada ciudad y pasar los detalles apropiados del clima como argumentos?

**Solución**: [https://pl.kotl.in/3ZqRK_5SX](https://pl.kotl.in/3ZqRK_5SX)
``` kotlin
fun main() {
    cityWeatherData("Ankara", 27, 31, 82)
    println()

    cityWeatherData("Tokyo", 32, 36, 10)
    println()

    cityWeatherData("Cape Town", 59, 64, 2)
    println()

    cityWeatherData("Guatemala City", 50, 55, 7)
    println()
}

fun cityWeatherData (city: String, lowTemp: Int, highTemp: Int, rainChance: Int) {
    println("City: $city")
    println("Low temperature: $lowTemp, High temperature: $highTemp")
    println("Chance of rain: $rainChance%")
}
```
