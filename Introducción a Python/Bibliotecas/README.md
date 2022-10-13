# Bibliotecas
Este ejercicio está basado en un curso de códigoIoT:
https://edu.codigoiot.com/mod/lesson/view.php?id=1964&pageid=2559

A continuación se muestra como realizar un ejercicio en el que se ejemplifica como usar las bibliotecas de Python, en este caso las del sensor MLX90614, este irá conectado a Raspberry.

## Diagrama del circuito
<div align="center"><img src="https://i.ibb.co/Jx5Vkv6/Diagrama-mlx.png"></div>

## Raspberry y VNC

El ejemplo utiliza el sensor de temperatura infrarrojo, que establece una comunicación por el protocolo I2C. Para esto necesitas encender la máquina virtual, la Rasberry Pi y establecer comunicación a través del VNC.
* Para realizar esto primero deberás haber realizado la configuración de la Raspberry y posteriormente la de VNC.
   * Abre una sesión de tu router(modem) en cualquier navegador y visualiza los dispositivos conectados por WiFi, copia la dirección a la que está conectada tu Raspberry.
   * Abre una terminal y ejecuta con la dirección correspondiente:
      ~~~
      ssh pi@192.168.x.x
      ~~~

* Después de haber iniciado VNC y abierto Rasberry deberás abrir la terminal y usar:
~~~
sudo raspi-config 
~~~
* Selecciona la opción de interfaces y después activa la opción I2C. Recuerda que en el entorno de configuración, el mouse se encuentra desactivado por lo que te debes mover con las flechas, la tecla tab y la tecla enter del teclado. 
<div align="center"><img src="https://i.ibb.co/9ZmLQt3/config-i2c.png"></div>


## Instalación de biblioteca

* El siguiente paso es instalar el módulo que permite la comunicación entre la tarjeta y el sensor, para esto ejecuta: 
~~~
pip3 install PyMLX90614 
~~~
* Después dirígete a la siguiente URL y descarga el archivo. 

https://pypi.org/project/PyMLX90614/#files 

* El archivo se puede almacenar en la carpeta de descargas o en el directorio principal. Una vez que encuentras la ubicación ejecuta el comando siguiente para extraer el archivo, recuerda que el comando debe coincidir con la versión que estás instalando: 
~~~
tar -xf PyMLX90614-0.0.4.tar.gz 
~~~
* Al extraer el archivo se crea una carpeta que debe de estar en el directorio raíz, si no se encuentra ahí, deberás moverla para realizar los siguientes pasos: 
~~~
cd PyMLX90614-0.0.4
sudo apt-get install python-setuptools 
sudo apt-get install -y i2c-tools 
sudo python setup.py install 
ls /dev/*i2c* 
i2cdetect -y 1
~~~
* Las instrucciones que se acaban de ejecutar son para la configuración del paquete de comunicación del sensor Infrarrojo y para activar el puerto de comunicación correspondiente. 

## Prueba del programa

Primero debes asegurarte de que la conección I2C está fucnionando correctamente, para esto deberás utilizar el comando en terminal:
~~~
sudo i2cdetect -y 1
~~~
Se deberá apreciar algo como esto:
<div align="center"><img src="https://i.ibb.co/HnHZynv/prueba-bus-i2c.png"></div>

Finalmente ejecuta el código en el IDE de tu elección y ahora habrás integrado módulos y paquetes en Python para su uso en IoT. No olvides guardar el archivo del código con la extensión .py 
~~~
#es código para python 3 
from smbus2 import SMBus 
from mlx90614 import MLX90614 
bus = SMBus(1) 
sensor = MLX90614(bus, address=0x5A) 
print ("Temperatura ambiente :", sensor.get_amb_temp()) 
print ("Temperatura de Persona u objeto :", sensor.get_obj_temp()) 
bus.close() 
~~~

## Resultado
***
El resultado es la temperatura del ambiente y de el objeto al que se le está apuntando:

<div align="center"><img src="https://i.ibb.co/5xjRTd7/Resultado-mlx.png"></div>

