# Test para Anaconda3
Este es un ejercicio para probar el funcionamiento de Anaconda3 desde VSC, creando una nueva libreta en Jupyter.
***
## Configuración del entorno
### 1.- Instalación de Python
La mayoría de las distros de Linux ya traen instalada alguna versión de Python, usualmente es la version 2. Para verificar la versión utiliza este comando en la terminal de Linux:
~~~
python --version
~~~
 En caso contrario se debe de ejecutar el siguiente comando:
~~~
sudo apt-get install python3 
~~~
### 2.- Instalación de Anaconda3
Para configurar Visual Studio Code desde la terminal, se necesita instalar Anaconda o Miniconda que son plataformas que generan ambientes de trabajo con todas las herramientas de Python incluyendo el uso de bibliotecas como Pandas o numpy. Dirígete al siguiente enlace:

https://www.anaconda.com/products/individual

Y selecciona el instalador de Linux, aparecerá lo siguiente:
<p> 
<img src="https://edu.codigoiot.com/pluginfile.php/12775/mod_lesson/page_contents/2490/Entorno_03.png" width="500px" align="right">
</p>
No es necesario crear una cuenta en Anconda, solo descarga el archivo. Para instalar, ejecuta el siguiente comando en terminal: 

~~~
bash ~/Downloads/Anaconda3-2022.05-Linux-x86_64.sh 
~~~
Deberás tomar en cuenta que el comando anterior puede ser modificado dependiendo el lugar en donde fue descargado y la versión.
### 3.- Instalar Jupyter
El siguiente paso es instalar Jupyter Notebook que es una interfaz que nos permite trabajar con todo tipo de archivos, como audio o vídeo, y no solo con archivos de datos. Ejecuta el siguiente comando desde la terminal:

~~~
sudo apt-get install jupyter 
~~~
### 4.- Agregar extensiones a VSC
Deberás descargar los siguientes pluggins desde la pestaña de extensiones en VSC:
<img src="https://edu.codigoiot.com/pluginfile.php/12775/mod_lesson/page_contents/2490/Entorno_04.png" width="500px" align="right">

### 5.- Configuración de ambiente
Ahora es necesario enlazar todos los elementos que instalamos y seleccionar el intérprete en VSC, para esto ve a view-> command palette-> Python: Select interpreter.
<img src="https://edu.codigoiot.com/pluginfile.php/12775/mod_lesson/page_contents/2491/Entorno_08.png" width="500px" align="right">
En este caso si no te marca alguna opcion en la que diga anaconda3, deberás buscar la ubicación manualmente en la opción "enter interpreter path".

Finalmente se crea un ambiente en Jupyter, para esto dirígete a view-> command palette-> Jupyter: Create new blank Jupyter Notebook.

<img src="https://edu.codigoiot.com/pluginfile.php/12775/mod_lesson/page_contents/2491/Entorno_09.png" width="500px" align="right">
Ahora verifica que el ambiente esté configurado correctamente con el siguiente programa:

~~~
import numpy as np 
arr = np.array([100, 2.7, 8.3333, 4, 0.5]) print(arr) 
print(type(arr)) 
~~~
 Has terminado la configuración del entorno y está listo para trabajar desde VSC en Ubuntu 20.04. 