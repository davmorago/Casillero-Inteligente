# Proyecto-Digital-I 
# Casilleros automáticos 
## Integrantes del grupo
Diego Alejandro Maldonado Marin

David Santiago Mora Godoy

Juan David Suarez Sanchez

![cAJAfINAL](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/dc7a9b87-2742-44b0-9f2c-10d035d8f0dc)

## Descripción del proyecto

El proyecto consiste en la creación y fabricación de un casillero automático que ofrece a los estudiantes la posibilidad de asegurar y acceder a sus pertenencias de manera conveniente y segura. El casillero se puede abrir mediante dos métodos de autenticación: mediante un sistema RFID (uso del carnet estudiantil) o a través de un teclado matricial (clave de 4 dígitos), según la preferencia del usuario.

## Problemática y análisis pestal del proyecto

### Problemática:  
Los estudiantes de la Universidad Nacional en especial los de ingeniería, para su proceso académico necesitan de implementos como multímetros, tarjetas programables, circuitos en protoboard, maquetas, entre otros que pueden llegar a dañarse al trasladarlos de la universidad a sus hogares, normalmente la mayoría de los estudiantes hacen uso del transporte público en el cual es complicado asegurar la integridad de los implementos, para un estudiante es difícil costear un taxi o servicio de transporte especial cada vez que necesite llevar algún implemento delicado a la universidad, el daño de estos implementos puede afectar el proceso académico de un estudiante y además el costo de algunos de estos implementos puede llegar al millón de pesos lo implica un gran gasto económico adicional para reponer el daño.

### Análisis pestal:

- Político: Últimamente se han dado demasiados problemas de seguridad en la universidad como robos o hurtos, a lo cual se ha dado casi nula respuesta de acción por parte de las directivas de la institución. La implementación de casilleros podría ayudar a mejorar la situación de seguridad de los estudiantes y su facilidad de cuidar los implementos personales o de equipos de trabajo.

- Económico: Se podría implementar una tarifa nominal por el uso de los casilleros automáticos, la universidad podría generar ingresos adicionales. Esto podría ayudar a financiar otros proyectos o programas en la universidad. Por otro lado, hay situaciones en las que los estudiantes pueden tener costos adicionales debido al transportar ciertos implementos, o por algún daño que pueda recibir en el mismo transporte de la casa-universidad y viceversa. Por lo cual la implementación de casilleros reduce la probabilidad de estas situaciones evitando gastos imprevistos en los estudiantes y profesores.

- Social: Los estudiantes pueden ahorrar tiempo y a su vez optimizarlo gracias a tener muchos de sus trabajos, pertenencias y demás en la misma universidad. Esto puede afectar indirectamente en la convivencia entre los estudiantes y a su vez dar más tranquilidad de no cometer una equivocación que afecte el rendimiento académico y mental de los estudiantes.

- Tecnológico: Esto puede ayudar a la universidad a destacar como una institución avanzada y moderna, ya que estamos en una de las universidades más prestigiosas del país. También puede ayudar a mejorar la eficiencia y la productividad de la gestión del espacio de almacenamiento, lo que a su vez puede liberar tiempo para que el personal de la universidad se centre en otras tareas importantes.

## Objetivos
### Objetivo principal:
Brindar a los estudiantes de la universidad Nacional la posibilidad de tener casilleros automatizados con la finalidad de mejorar su calidad en el campus y brindando seguridad, accesibilidad y espacios para los objetos personales de cada estudiante. 
### Objetivos secundarios:
Reducir la cantidad de pertenencias y proyectos robados o extraviados dentro del campus universitario. 

Proponer un avance tecnológico en las instalaciones que den pie a siempre estar actualizados en el desarrollo innovador y moderno de nuevos espacios en la universidad.

Conseguir nuevos ingresos para la universidad, de los cuales podrán salir beneficios para grupos de investigación, grupos deportivos y actividades de bienestar. Mejorando así la experiencia de la misma institución

## Periféricos
### RFID
Para leer tarjetas RFID se va a utilizar el lector RC522 el cual está capacitado para leer tarjetas con la tecnología MIFARE, esta tecnología es la que usan los carnets estudiantiles de la universidad nacional. La información de estas tarjetas se almacena de la siguiente manera.

![rfid](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/0a538f6f-52b0-46d8-90e3-34cdcc859a3e)

Dependiendo de de la capacidad de la tarjeta se tienen 16 o más sectores donde cada sector tendrá 4 bloques de 16 Bytes, el primer bloque de cada sector siempre se reserva para almacenar las claves de acceso y directivas de todo el sector.

Cada tarjeta tiene un identificador único (UID) que está reservado en los primeros 4 bytes, para acceder a este UID hay que proporcionar la clave que nos permita leer la información contenida en el bloque 0, esta clave de fábrica es “FF FF FF FF FF FF”, asi que si se cambio la clave por defecto será difícil acceder al UID.

Es con este UID que vamos a autenticar el carnet leído con el RC522.

![rfid2](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/861b6dbe-8ed8-43b6-8941-4ca4fa46dbca)

### Servomotor
El servomotor es la salida principal del proyecto, este será el mecanismo activo a la hora de abrir el casillero, es decir, para abrirse se posiciona a 90° mientras que a cerrarse esta posicionado en 180°. Esto se consigue mediante el ciclo de trabajo que se le entrega al servo por medio de un PWM.

El servo tiene un periodo de funcionamiento de 20ms, y lo que se hace es darle un ciclo de trabajo de 5% para posicionar el cierre, mientras que para abrir nuestro sistema le asigmos un2% de ciclode trabajo.
![Servo](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/c8ac5ac5-1a23-45fd-b00c-26421aa2842b)

### Tecla matricial

### Buzzer
Como de buzzer de la FPGA es un buzzer activo, solo necesita alimentación para funcionar. Por lo cual, cada vez que presionamos una tecla del teclado matricial alimentamos el buzzer.

![buzzer](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/959433ee-9347-42da-bf17-867f6e7ec700)

## Diagrama de bloques
![DiagramaBloques](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/eb802d76-0602-4ebe-b82d-f9f1b2c00b16)

## Diagrama de estados
![DiagramaEstados](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/d6711c33-e5db-42b4-ad52-3dd1a5fc92c5)

## Diagrama de Flujo
![DiagramaFlujo](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/bcd1c8c0-4f3d-4006-a29c-bf02fd29e88e)

## Simulaciones
### Servomotor
La siguiente imagen muestra la señal de salida del servo cuando este está cerrado (Estado en 1). Se observa que el ciclo útil aplicado para este caso es de 5%:

![ServoCerrado](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/9a1ceb4d-ea4c-4f5a-b636-55a1ec0f0c70)

Al cambiar el ciclo útil a 2% obtenemos el servo abierto (Estado en 0). Esto se muestra en la figura a continuación.

![ServaAbierto](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/e19799f2-a7bc-44b4-8d68-eaddc5015cd4)
### Teclado matricial

![Sim_Teclado](https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/c9354cfa-cc08-4f9b-afc2-eb960590bf41)

La anterior imagen muestra el funcionamiento de la lectura de los números ingresados en el teclado matricial. La primera señal que se puede ver es el clock, la segunda es un vector de 4 bits que indica cual columna fue presionada, la tercera señal es el desplazamiento de la alimentación de las filas, la cuarta es un vector de ocho bits que almacena la columna y la fila donde se encuentra la tecla presionada, la quinta señal es la activación del buzzer al presionar una tecla, la cual se encuentra en cero cuando debe sonar, ya que la salida en la FPGA está negada, la última señal corresponde a la conversión de lo leído a bcd.

## Video del funcionamiento del proyecto


https://github.com/davmorago/Proyecto-Digital-I/assets/135071520/b6b5a163-fecd-4879-b8bb-0fd308bd0ffe


## Referencias
- Datasheet Servomotor: https://datasheetspdf.com/pdf-file/791970/TowerPro/SG90/1
- Datasheet RFID: https://pdf1.alldatasheet.es/datasheet-pdf/view/227840/NXP/RC522.html
- Datasheet Arduino: http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-7810-Automotive-Microcontrollers-ATmega328P_Datasheet.pdf
- Librerias vhdl (RFID): https://intesc.mx/librerias-vhdl/
- VHDL Lenguaje para síntesis y modelado de circuitos por Fernando Pardo y José Boluda
