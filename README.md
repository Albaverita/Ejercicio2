# Ejercicio2 : Semáforo 

Este programa de consola en C# simula un semáforo básico que alterna entre las luces roja, amarilla y verde. Cada luz se activa durante un tiempo específico: 3 segundos para la roja, 1 segundo para la amarilla y 3 segundos para la verde. El programa utiliza un bucle infinito para repetir este ciclo continuamente.


![image](https://github.com/user-attachments/assets/b4538d71-f405-4afb-a4fa-c4ebedcd1dc4)

## LIbrerias 
```kotlin 
using System;
using System.Threading;
```

## Codigo completo del rograma  
```kotlin 
class Semaforo
{
    static void Main(string[] args)
    {
        while (true)
        {
            // Luz roja
            Console.Clear();
            Console.WriteLine("  ROJO  ");
            MostrarSemaforo("ROJO");
            Thread.Sleep(3000); // Espera 3 segundos

            // Luz amarilla
            Console.Clear();
            Console.WriteLine("AMARILLO");
            MostrarSemaforo("AMARILLO");
            Thread.Sleep(1000); // Espera 1 segundo

            // Luz verde
            Console.Clear();
            Console.WriteLine("  VERDE  ");
            MostrarSemaforo("VERDE");
            Thread.Sleep(3000); // Espera 3 segundos
        }
    }

    static void MostrarSemaforo(string color)
    {
        string rojo = color == "ROJO" ? "O" : " ";
        string amarillo = color == "AMARILLO" ? "O" : " ";
        string verde = color == "VERDE" ? "O" : " ";

        Console.WriteLine("  [ " + rojo + " ]  ");
        Console.WriteLine("  [ " + amarillo + " ]  ");
        Console.WriteLine("  [ " + verde + " ]  ");
    }
}
```
## Luz roja 
Primero, limpia la consola con Console.Clear(), eliminando cualquier texto que estuviera previamente en la pantalla. Luego, muestra la palabra "ROJO" en el centro de la consola con Console.WriteLine(" ROJO "), indicando que la luz roja del semáforo está encendida. A continuación, el método MostrarSemaforo("ROJO") se ejecuta, lo que representa visualmente el semáforo con la luz roja activa. Finalmente, el programa se detiene durante 3 segundos usando Thread.Sleep(3000), simulando el tiempo que la luz roja permanece encendida antes de pasar a la siguiente luz. LUz verde y amarilla funcionan de la isma forma pero con diferenres datos. 

```kotlin 
 // Luz roja
            Console.Clear();
            Console.WriteLine("  ROJO  ");
            MostrarSemaforo("ROJO");
            Thread.Sleep(3000); // Espera 3 segundos
```
## Funcionamiento de MostrarSemaforo(string color):

Definición de la función:
La función MostrarSemaforo es estática (static), lo que significa que puede ser llamada sin necesidad de crear una instancia de la clase. Toma un parámetro de tipo string llamado color, que indica cuál luz del semáforo debe estar encendida.
Determinación de los colores:

Dentro de la función, se definen tres variables: rojo, amarillo, y verde. Estas variables se establecen en "O" si el color proporcionado coincide con ellas; de lo contrario, se establecen en un espacio vacío " ". Esto decide cuál de las luces del semáforo estará encendida y cuál apagada.
```kotlin 
string rojo = color == "ROJO" ? "O" : " ";
string amarillo = color == "AMARILLO" ? "O" : " ";
string verde = color == "VERDE" ? "O" : " ";
```

Mostrar el semáforo en la consola:

Después de determinar cuál luz estará encendida, la función utiliza Console.WriteLine para dibujar el semáforo en la consola, colocando las variables rojo, amarillo, y verde en posiciones específicas, una debajo de la otra.
```kotlin 
 Console.WriteLine("  [ " + rojo + " ]  ");
Console.WriteLine("  [ " + amarillo + " ]  ");
Console.WriteLine("  [ " + verde + " ]  ");
```
Cada llamada a Console.WriteLine muestra una línea en la consola, formando un semáforo vertical. Por ejemplo, si el color es "ROJO", el resultado en la consola se verá algo así:
```kotlin 
  [ O ]  
  [   ]  
  [   ] 
```
Resumen:
La función MostrarSemaforo selecciona y muestra cuál luz del semáforo está activa (roja, amarilla, o verde) según el valor de color pasado como argumento. Las demás luces se muestran apagadas, representadas por espacios vacíos.
