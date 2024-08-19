Introducción

Este proyecto es un keylogger básico escrito en C que registra las entradas del teclado en un sistema Linux. El keylogger escucha eventos de teclado y registra las pulsaciones de teclas en un archivo de texto. El programa demuestra el uso de la gestión de eventos de entrada en Linux y llamadas al sistema en C.
Requisitos Previos

    Un sistema operativo basado en Linux.
    Conocimientos básicos de programación en C.
    Privilegios de root (necesarios para acceder a los dispositivos de entrada).

Compilación

Para compilar el keylogger, utiliza el siguiente comando:

bash

gcc -o keylogger keylogger.c

Uso

    Ejecutar el Keylogger:
    Para iniciar el keylogger, ejecuta el binario compilado como root:

    bash

sudo ./keylogger

Ubicación del Archivo de Registro:
El keylogger registrará todas las pulsaciones de teclas capturadas en el siguiente archivo:

bash

    /home/chased36/Desktop/Seguridad informatica/keylogger.txt

    Detener el Keylogger:
    Para detener el keylogger, simplemente termina el proceso (por ejemplo, usando Ctrl+C).

Explicación del Código

    Archivos de Cabecera:
        #include <stdio.h>: Funciones estándar de entrada/salida.
        #include <fcntl.h>: Opciones de control de archivos.
        #include <unistd.h>: Funciones estándar de Unix.
        #include <linux/input.h>: Estructuras de eventos de entrada.
        #include <linux/input-event-codes.h>: Definiciones de códigos de eventos.
        #include <sys/stat.h>: Datos devueltos por la función stat().
        #include <string.h>: Funciones de manipulación de cadenas.
        #include <stdlib.h>: Funciones de la biblioteca estándar.
        #include <errno.h>: Manejo de errores.

    getEvent():
        Esta función identifica el dispositivo de eventos correspondiente al teclado. Analiza el archivo /proc/bus/input/devices para localizar el dispositivo adecuado.

    getKeyCode(int code):
        Esta función traduce el código de tecla numérico recibido del evento de entrada en una cadena legible.

    main():
        La función principal maneja la inicialización y el monitoreo continuo de eventos de teclado. Abre el dispositivo de eventos correspondiente y escribe las pulsaciones de teclas detectadas en el archivo de registro.

Notas

    Implicaciones de Seguridad:
        Ejecutar este keylogger requiere privilegios de root, lo cual puede tener implicaciones significativas de seguridad. Sé cauteloso al desplegarlo en sistemas que no son de tu propiedad.

    Descargo de Responsabilidad Legal:
        Asegúrate de tener permiso legal para registrar la actividad del teclado. El uso no autorizado de keyloggers puede violar leyes de privacidad y directrices éticas.

Solución de Problemas

    No se Puede Abrir el Dispositivo de Evento:
        Asegúrate de ejecutar el programa como root.
        Verifica que se esté accediendo al dispositivo de evento correcto.

    El Archivo de Registro no se Actualiza:
        Revisa los permisos del archivo y asegúrate de que la ruta del archivo sea correcta.
        Asegúrate de que el keylogger siga ejecutándose y monitoreando el teclado.

Licencia

Este keylogger se proporciona con fines educativos. El autor no se hace responsable de ningún mal uso o daño causado por este programa.
