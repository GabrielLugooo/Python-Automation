<img align="center" src="https://media.licdn.com/dms/image/v2/D4D16AQGUNxQ7NSC05A/profile-displaybackgroundimage-shrink_350_1400/profile-displaybackgroundimage-shrink_350_1400/0/1738695150340?e=1744243200&v=beta&t=oXX-ixT9bR3dJcYCLv4KBs5wjKFoeP0524kFGHQMYmQ" alt="gabriellugo" />

# ALGORITMO PYTHON PARA ACTUALIZAR ARCHIVO

<a href="https://github.com/GabrielLugooo/Python-Algorithm-Update-File/blob/main/README%20Spanish.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Algoritmo%20Python%20Español-000000" alt="Algoritmo Python Español" /></a>
<a href="https://github.com/GabrielLugooo/Python-Algorithm-Update-File" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Algoritmo%20Python%20Inglés-green" alt="Algoritmo Python Inglés" /></a>

### Objetivo

Archivo de actualización de algoritmo de Python Es un algoritmo que elimina las direcciones IP identificadas en una variable "remove_list" del archivo "allow_list.txt" de direcciones IP aprobadas.

Este algoritmo implica abrir el archivo, convertirlo en una cadena para leer y luego convertir esta cadena en una lista almacenada en la variable "ip_addresses".

A continuación, itera las direcciones IP en "remove_list". Con cada iteración, evalúa si el elemento formaba parte de la lista "ip_addresses". Si lo es, le aplica el método ".remove()" para eliminar el elemento de "ip_addresses".

Después de esto, utiliza el método ".join()" para convertir "ip_addresses" nuevamente en una cadena para poder sobrescribir el contenido del archivo "allow_list.txt" con la lista revisada de direcciones IP.

### Habilidades Aprendidas

- Tecnologías Python.
- Proteger redes, información y datos mediante un algoritmo que identifica técnicas de direcciones IP permitidas y no permitidas.
- Capacidad para generar y reconocer firmas y patrones de ataque.
- Mejor conocimiento de protocolos de red y vulnerabilidades de seguridad.
- Desarrollo de pensamiento crítico y habilidades de resolución de problemas en ciberseguridad.

### Technologías Usadas

![Static Badge](https://img.shields.io/badge/Python-000000?logo=python&logoSize=auto)

### Proyecto

En muchas organizaciones, el acceso a contenido restringido está controlado por una lista de direcciones IP permitidas. El archivo "allow_list.txt" identifica estas direcciones IP.

Una lista de permitidos independiente identifica las direcciones IP que ya no deberían tener acceso a este contenido. Creé un algoritmo para automatizar la actualización de la lista de permitidos "allow_list.txt" archiva y elimine aquellas direcciones IP que ya no deberían tener acceso.

#### Abra el archivo que contiene la lista de permitidos

Para la primera parte del algoritmo, abra el archivo "allow_list.txt" . Primero, asigne este nombre de archivo como una cadena a la variable "import_file" :

```sh
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"
```

A continuación, asigne el archivo “remove_list” a una lista de direcciones IP a las que ya no se les permite acceder a información restringida:

```sh
# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information.
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
```

Luego use una declaración "with" para abrir el archivo:

```sh
# Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file:
```

En el algoritmo, la instrucción "with" se utiliza con la función ".open()" en modo de lectura para abrir el archivo de lista de permitidos con fines de lectura. El propósito de abrir el archivo es permitir el acceso a las direcciones IP almacenadas en el archivo de lista de permitidos. La palabra clave "with" ayudará a administrar los recursos cerrando el archivo después de salir de la instrucción "with".

En el código "with open(import_file, "r") as file:", la función "open()" tiene dos parámetros. El primero identifica el archivo a importar y luego el segundo indica lo que desea hacer con el archivo. En este caso, "r" indica que desea leerlo. El código también utiliza la palabra clave "as" para asignar una variable llamada "file" ; "file" almacena la salida de la función ".open()" mientras trabaja dentro de la instrucción "with".

#### Leer el contenido del archivo

Para leer el contenido del archivo, utilice el método ".read()" para convertirlo en una cadena:

```sh
with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
  ip_addresses = file.read()
```

Al usar una función ".open()" que incluye el argumento "r" para "leer", puedes llamar a la función ".read()" en el cuerpo de la declaración "with". El método ".read()" convierte el archivo en una cadena y permite leerlo. Aplica el método ".read()" a la variable de archivo identificada en la declaración "with".

Luego, asigna la salida de cadena de este método a la variable "ip_addresses".

En resumen, este código lee el contenido del archivo "allow_list.txt" en un formato de cadena que me permite luego usar la cadena para organizar y extraer datos en el programa Python.

#### Convertir cadena en lista

Para eliminar direcciones IP individuales de la lista de permitidos, es necesario que estén en formato de lista. A continuación, utilice el método ".split()" para convertir la cadena "ip_addresses" en una lista:

```sh
# Use `.split()` to convert `ip_addresses` from a string to a list
ip_addresses = ip_addresses.split()
```

La función ".split()" se llama añadiéndole una variable de cadena. Funciona convirtiendo el contenido de una cadena en una lista. El propósito de dividir "ip_addresses" en una lista es facilitar la eliminación de direcciones IP de la lista de permitidos. De forma predeterminada, la función ".split()" divide el texto por espacios en blanco en elementos de lista.

La función ".split()" toma los datos almacenados en la variable "ip_addresses", que es una cadena de direcciones IP separadas por espacios en blanco, y convierte esta cadena en una lista de direcciones IP. Para almacenar esta lista, tienes que reasignarla a la variable "ip_addresses".

#### Iterar a través de la lista de eliminación

Una parte clave del algoritmo consiste en iterar las direcciones IP que son elementos de la "remove_list". Para ello, es necesario incorporar un bucle "for":

```sh
# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:
```

El bucle "for" en Python repite el código de una secuencia específica. El propósito general del bucle "for" en un algoritmo de Python como este es aplicar instrucciones de código específicas a todos los elementos de una secuencia.

La palabra clave for inicia el bucle "for". Le sigue la variable de bucle de elementos y la palabra clave "in". La palabra clave "in" indica que se debe iterar a través de la secuencia "ip_addresses" y asignar cada valor a la variable de bucle de elementos.

#### Eliminar direcciones IP que están en la lista de eliminación

El algoritmo requiere eliminar todas las direcciones IP de la lista de direcciones permitidas, "ip_addresses", que también estén incluidas en "remove_list". Como no había duplicados en "ip_addresses", puedes usar el siguiente código para hacerlo:

```sh
# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:

    # Build conditional statement
    # If current element is in `remove_list`,
    if element in remove_list:

        # then current element should be removed from `ip_addresses`
        ip_addresses.remove(element)
```

Primero, dentro del bucle "for", crea una condición que evalúe si la variable del bucle del elemento se encontró en la lista "ip_addresses". Lo harás porque aplicar ".remove()" a elementos que no se encontraron en "ip_addresses" podría generar un error.

Entonces, dentro de esa condición, aplica ".remove()" a "ip_addresses". Pasaste la variable del bucle element como argumento para que cada dirección IP que estuviera en la "remove_list" se eliminara de "ip_addresses".

#### Actualice el archivo con la lista revisada de direcciones IP

Como siguiente paso del algoritmo, era necesario actualizar el archivo de lista de permitidos con la lista revisada de direcciones IP. Para ello, primero había que convertir la lista nuevamente en una cadena. Para ello, se utiliza el método ".join()":

```sh
# Convert `ip_addresses` back to a string so that it can be written into the text file
ip_addresses = " ".join(ip_addresses)
```

El método ".join()" combina todos los elementos de un iterable en una cadena. El método ".join()" se aplica a una cadena que contiene caracteres que separarán los elementos del iterable una vez que se unan en una cadena.

En este algoritmo, use el método ".join()" para crear una cadena a partir de la lista "ip_addresses" para que pueda pasarse como argumento al método ".write()" al escribir en el archivo "allow_list.txt". Use la cadena (" ") (carácter vacío) como separador para indicarle a Python que coloque cada elemento en una nueva línea.

Luego use otra declaración "with" y el método ".write()" para actualizar el archivo:

```sh
# Build `with` statement to rewrite the original file
with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`
  file.write(ip_addresses)
```

Esta vez, utilizó un segundo argumento de "w" con la función "open()" en la declaración "with". Este argumento indica que desea abrir un archivo para sobrescribir su contenido. Al utilizar este argumento "w", puede llamar a la función ".write()" en el cuerpo de la declaración "with". La función ".write()" escribe datos de cadena en un archivo especificado y reemplaza cualquier contenido de archivo existente.

En este caso, deseaba escribir la lista de permitidos actualizada como una cadena en el archivo "allow_list.txt". De esta manera, el contenido restringido ya no será accesible para ninguna dirección IP que se haya eliminado de la lista de permitidos.

Para reescribir el archivo, agregó la función ".write()" al archivo de objeto de archivo que identificó en la declaración "with". Pasó la variable "ip_addresses" como argumento para especificar que el contenido del archivo especificado en la declaración "with" debe reemplazarse con los datos de esta variable.

#### Lea el archivo con la lista revisada de direcciones IP

Como paso final del algoritmo, era necesario leer el archivo de lista de permitidos actualizado con la lista revisada de direcciones IP.
Nuevamente, la declaración "with", la función "open()", el argumento "r", el código también usa la palabra clave as para asignar una variable llamada "file", con la función "with open(import_file, "r") as file:".

```sh
# Build `with` statement to read in the updated file
with open(import_file, "r") as file:

    # Read in the updated file and store the contents in `text`
    text = file.read()

# Display the contents of `text`
print(text)
```

Aplicar el método ".read()" a la variable de archivo identificada en la declaración "with". Luego, se asignó la salida de cadena de este método a la variable de texto.

Luego aplicar función "print()" y asignando la variable de texto podemos imprimir el contenido del archivo "import_file" revisado en la pantalla en formato de cadena.

### Limitaciones

## Python Algorythm Update File it's just for educational purpose under the MIT License.

<h3 align="left">Conecta Conmigo</h3>

<p align="left">
<a href="https://www.youtube.com/@gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=55200&format=png" alt="@gabriellugooo" height="40" width="40" /></a>
<a href="http://www.tiktok.com/@gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=118638&format=png" alt="@gabriellugooo" height="40" width="40" /></a>
<a href="https://instagram.com/lugooogabriel" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=32309&format=png" alt="lugooogabriel" height="40" width="40" /></a>
<a href="https://twitter.com/gabriellugo__" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=phOKFKYpe00C&format=png" alt="gabriellugo__" height="40" width="40" /></a>
<a href="https://www.linkedin.com/in/hernando-gabriel-lugo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=8808&format=png" alt="hernando-gabriel-lugo" height="40" width="40" /></a>
<a href="https://github.com/GabrielLugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=80&id=AngkmzgE6d3E&format=png" alt="gabriellugooo" height="34" width="34" /></a>
<a href="mailto:lugohernandogabriel@gmail.com"> <img align="center" src="https://img.icons8.com/?size=50&id=38036&format=png" alt="lugohernandogabriel@gmail.com" height="40" width="40" /></a>
<a href="https://linktr.ee/gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://simpleicons.org/icons/linktree.svg" alt="gabriellugooo" height="40" width="40" /></a>
</p>

<p align="left">
<a href="https://github.com/GabrielLugooo/GabrielLugooo/blob/main/Readme%20Spanish.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Versión%20Español-000000" alt="Versión Español" /></a>
<a href="https://github.com/GabrielLugooo/GabrielLugooo/blob/main/README.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Versión%20Inglés-Green" alt="Versión Inglés" /></a>

</p>

<a href="https://linktr.ee/gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Créditos-Gabriel%20Lugo-green" alt="Créditos" /></a>
<img align="center" src="https://komarev.com/ghpvc/?username=GabrielLugoo&label=Vistas%20del%20Perfil&color=green&base=2000" alt="GabrielLugooo" />
<a href="" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/License-MIT-green" alt="Last Edited" /></a>
