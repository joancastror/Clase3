1.	Diseñar un programa que solicite al usuario dos números y, si el primer número es más grande, calcule y muestre su suma y resta. De lo contrario, calculará y mostrará su producto y cociente.
Código 
namespace CalcularNotas
{
    class program
    {
        public class Calificacion
        {
            public void CalcularNumeros()
            {
                int num1 = 0;
                int num2 = 0;
                int suma = 0;
                int resta = 0;
                int producto = 0;
                double division = 0;
                string linea;

                try
                {
                    // Pedir el valor de num1
                    Console.WriteLine("Ingrese el valor de num1:");
                    linea = Console.ReadLine();
                    if (string.IsNullOrEmpty(linea))
                    {
                        Console.WriteLine("Num 1 es requerido");
                        return;
                    }
                    if (!int.TryParse(linea, out num1))
                    {
                        Console.WriteLine("Num 1 es invalido");
                        return;
                    }

                    // Pedir el valor de num2
                    Console.WriteLine("Ingrese el valor de num2:");
                    linea = Console.ReadLine();
                    if (string.IsNullOrEmpty(linea))
                    {
                        Console.WriteLine("Num 2 es requerido");
                        return;
                    }
                    if (!int.TryParse(linea, out num2))
                    {
                        Console.WriteLine("Num 2 es invalido");
                        return;
                    }

                    // Realizar operaciones
                    if (num1 > num2)
                    {
                        suma = num1 + num2;
                        resta = num1 - num2;
                        Console.WriteLine($"La suma es {suma} y la resta es {resta}");
                    }
                    else
                    {
                        producto = num1 * num2;
                        // Verificar si num2 no es 0 antes de dividir
                        if (num2 != 0)
                        {
                            division = (double)num1 / num2;
                            Console.WriteLine($"El producto es {producto} y la division es {division}");
                        }
                        else
                        {
                            Console.WriteLine("La división por cero no es posible");
                        }
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Ocurrió el siguiente error: {ex.Message}");
                }
            }
        }
    }
}


2.	Leer tres calificaciones y calcular el promedio. Si el promedio es igual o superior a siete, imprimir un mensaje indicando que el alumno ha aprobado.
Código 
namespace CalcularNotas
{
    class Program
    {
        public class Calificacion
        {
            public void CalcularNumeros()
            {
                double nota1 = 0;
                double nota2 = 0;
                double nota3 = 0;
                double promedio = 0;
                string linea = string.Empty;

                try
                {
                    // Pedir el valor de la primera calificación
                    Console.WriteLine("Ingrese la primera calificación:");
                    linea = Console.ReadLine();
                    if (string.IsNullOrEmpty(linea))
                    {
                        Console.WriteLine("La primera calificación es requerida");
                        return;
                    }
                    if (!double.TryParse(linea, out nota1))
                    {
                        Console.WriteLine("La primera calificación es inválida");
                        return;
                    }

                    // Pedir el valor de la segunda calificación
                    Console.WriteLine("Ingrese la segunda calificación:");
                    linea = Console.ReadLine();
                    if (string.IsNullOrEmpty(linea))
                    {
                        Console.WriteLine("La segunda calificación es requerida");
                        return;
                    }
                    if (!double.TryParse(linea, out nota2))
                    {
                        Console.WriteLine("La segunda calificación es inválida");
                        return;
                    }

                    // Pedir el valor de la tercera calificación
                    Console.WriteLine("Ingrese la tercera calificación:");
                    linea = Console.ReadLine();
                    if (string.IsNullOrEmpty(linea))
                    {
                        Console.WriteLine("La tercera calificación es requerida");
                        return;
                    }
                    if (!double.TryParse(linea, out nota3))
                    {
                        Console.WriteLine("La tercera calificación es inválida");
                        return;
                    }

                    // Calcular el promedio
                    promedio = (nota1 + nota2 + nota3) / 3;

                    // Mostrar el promedio y determinar si el alumno ha aprobado
                    Console.WriteLine($"El promedio es: {promedio}");
                    if (promedio >= 7)
                    {
                        Console.WriteLine("El alumno ha aprobado.");
                    }
                    else
                    {
                        Console.WriteLine("El alumno no ha aprobado.");
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Ocurrió el siguiente error: {ex.Message}");
                }
            }
        }
    }
}


3.	Desarrollar un programa que calcule el nivel de un postulante a partir de los resultados de un test. El programa recibirá como entrada el número total de preguntas y las respuestas correctas, y devolverá un nivel según el porcentaje de aciertos.
•	Nivel máximo: Porcentaje>=90%.
•	Nivel medio: Porcentaje>=75% y <90%.
•	Nivel regular: Porcentaje>=50% y <75%.
•	Fuera de nivel: Porcentaje<50%.
Codigo
namespace calcularcondicional
{
        class Program
        {
            static void Main(string[] args)
            {
                try
                {
                    // Solicitar el número total de preguntas
                    Console.WriteLine("Ingrese el número total de preguntas del test:");
                    int totalPreguntas = Convert.ToInt32(Console.ReadLine());

                    // Validar que el número total de preguntas sea mayor a 0
                    if (totalPreguntas <= 0)
                    {
                        Console.WriteLine("El número total de preguntas debe ser mayor a 0.");
                        return;
                    }

                    // Solicitar el número de respuestas correctas
                    Console.WriteLine("Ingrese el número de respuestas correctas:");
                    int respuestasCorrectas = Convert.ToInt32(Console.ReadLine());

                    // Validar que el número de respuestas correctas no sea mayor que el total de preguntas
                    if (respuestasCorrectas < 0 || respuestasCorrectas > totalPreguntas)
                    {
                        Console.WriteLine("El número de respuestas correctas no puede ser menor a 0 ni mayor que el número total de preguntas.");
                        return;
                    }

                    // Calcular el porcentaje de respuestas correctas
                    double porcentaje = ((double)respuestasCorrectas / totalPreguntas) * 100;

                    // Determinar el nivel del postulante
                    string nivel;
                    if (porcentaje >= 90)
                    {
                        nivel = "Nivel máximo";
                    }
                    else if (porcentaje >= 75)
                    {
                        nivel = "Nivel medio";
                    }
                    else if (porcentaje >= 50)
                    {
                        nivel = "Nivel regular";
                    }
                    else
                    {
                        nivel = "Fuera de nivel";
                    }

                    // Mostrar el nivel del postulante
                    Console.WriteLine($"El postulante tiene un porcentaje de aciertos de {porcentaje:F2}% y su nivel es: {nivel}");
                }
                catch (FormatException)
                {
                    Console.WriteLine("Por favor, ingrese un número válido.");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Ocurrió un error: {ex.Message}");
                }
            }
        }
}

