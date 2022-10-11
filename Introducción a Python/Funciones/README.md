# Funciones 

Las funciones son secciones de código que se pueden llamar una y otra vez, además de que cumplen con diferentes propósitos como: 

1.- Se puede crear una función y llamarla en varias ocasiones y ubicaciones.

2.- Permiten probar una solución propuesta de manera individual.

3.- Normalmente en las funciones se encuentra la estructura principal de la solución, por lo que permiten omitir los detalles de la solución propuesta. 

En Python las funciones se definen con la palabra reservada def. Cuando se llama la función, se ejecutan los comandos y finalmente devuelve un resultado. Un ejemplo de función es print, int, float, que se han utilizado previamente y que son definidas por el lenguaje de programación. 

## Funciones con parámetros 
***
En el siguiente código se muestra la forma de cómo crear, y llamar una función. En este caso la función se llama utilizando valores que son almacenados en variables dentro de la función. 

<div align="center"><img src="https://i.ibb.co/h826CPT/funciones.png"></div>


 Para llamar esta función se debe de utilizar la instrucción de la siguiente manera: 
~~~
dibujo(5, 5) 
~~~

## Regreso de valores 
***
Uno de los objetivos principales de una función es poder delegar procesos, en consecuencia, se espera que la mayoría de dichos procesos regresen un valor. En el siguiente ejemplo se muestra una función que regresa el valor de una variable: 

~~~
# Función de una sucesión geométrica 
def sumGeometric(a, r, n): 
   # Si el radio tiene un valor de uno 
   if r == 1: 
      return a * n 
   # Calcula la suma geométrica cuando el radio es diferente de uno 
   s = a * (1 - r ** n) / (1 - r) 
   #regresa el valor de s 
   return s
~~~

Finalmente, para importar una función realizada por alguien más se puede utilizar la palabra reservada import. Con las versiones diferentes de Python, también se puede utilizar el siguiente código para permitir que la nueva función sea importada: 
~~~
if __name__ == "__main__": 
   main() 
~~~