Nodos Ros (Publisher - Suscriber) - Comunicación Arduino
==============
*El proyecto consiste en comunicar Ros y Arduino, se utiliza el Arduino uno y se trabaja como un nodo de Ros para la comunicación Serial. El Arduino envia 3 datos (un booleano, un entero y un flotante) por tres topics diferentes, los nodos de Ros creados se encargan de recibir y procesar la información utilizando una funcion de pertenecia para obtener el porcentaje que cada dato tiene a una clase (bajo, medio, alto), si cada dato tiene una pertenencia mayor al 50% a una de las clases se dice que pertenece a esa clase y dependiendo de a que clase pertenezaca cada uno de los tres datos que envia el arduino, se envía un valor en grados diferente al arduino para controlar un servomotor.*

![alt text](https://github.com/eliandv1911/Nodos_Ros-Arduino/blob/8d2bce3f6bba70efaebd5a2c07391af1d3629d52/images/funcion_pertenencia.png)


**NODO "talker_3d.cpp":**
*Este nodo se encarga de recibir los tres datos que son enviados de arduino (bool, int, float) por tres diferentes topics y volverlos a enviar por un topic diferente para que otro nodo los reciba*

**NODO "listener_talker_bool.cpp":**
*Este nodo se encarga de recibir el dato booleano que publica el nodo "talker_3d.cpp", si el dato es "true" va a publicar en un topic que tiene un porcentaje de pertenencia de 100% para alto, por el contrario si es "false" va a publicar en el topic que tiene un porcentaje de pertenencia de 100% para bajo*

**NODO "listener_talker_int.cpp":**
*Este nodo se encarga de recibir el dato entero que publica el nodo "talker_3d.cpp", evalua este dato en las funciones de pertenencia y publica el resultado de la evaluacion en un topic diferente*

**NODO "listener_talker_float.cpp":**
*Este nodo se encarga de recibir el dato flotante que publica el nodo "talker_3d.cpp", evalua este dato en las funciones de pertenencia y publica el resultado de la evaluacion en un topic diferente*

*-------------------------------------------------------------------------------------------------------------------------------------------------------*

***Nota:** para los tres nodos anteriores los topics de cada nodo que publican, estan publicando cadenas con el porcentaje de pertenencia para cada clase (bajo, medio, alto), por ejemplo: "A100%/M0%/B0%"*

*-------------------------------------------------------------------------------------------------------------------------------------------------------*

**NODO "listener_talker_char1.cpp":**
*Este nodo se encarga de recibir la cadena que viene del nodo "listener_talker_bool.cpp", separa la cadena y dependiendo del porcentaje de pertenencia (si para una clase es mayor a 50%) asigna una letra que representa a la clase a la cual pertenece (B-A -> bajo-alto), esta letra se publica como un caracter en un topic*

**NODO "listener_talker_char2.cpp":**
*Este nodo se encarga de recibir la cadena que viene del nodo "listener_talker_int.cpp", separa la cadena y dependiendo del porcentaje de pertenencia (si para una clase es mayor a 50%) asigna una letra que representa a la clase a la cual pertenece (B-M-A -> bajo-medio-alto), esta letra se publica como un caracter en un topic*

**NODO "listener_talker_char3.cpp":**
*Este nodo se encarga de recibir la cadena que viene del nodo "listener_talker_float.cpp", separa la cadena y dependiendo del porcentaje de pertenencia (si para una clase es mayor a 50%) asigna una letra que representa a la clase a la cual pertenece (B-M-A -> bajo-medio-alto), esta letra se publica como un caracter en un topic*

*This will be Italic*

**This will be Bold**

- This will be a list item
- This will be a list item

1. This will be a numerated list 
2. This will be a numerated list 

```
this will be a code segment
```
> this will be a definition
<http://url> this will be a web link
<!--this will a comment-->
This will a title
--------------
