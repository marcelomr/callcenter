# Call Center

Se utilizo:
Java 8
Maven 4.0
Eclipse STS (Spring Tool Suite) 4. Se puede usar otro eplise
Spring Boot 1.5.6

## Solución

Para no tener que andar creando hilos de forma manualmente con Thread, Semaforos, etc. 
Se utilizo la interfaz ExecutorService y PriorityBlockingQueue para:
Manejar adecuadamente la concurrencia que ya me brinda java.
Tener una correcta priorizacion en el orden de atencion de los empleados, de acuerdo a su tipo.
Y que las llamadas queden en espera hasta que algun empleado se libere y pueda atenderla.

#### CallCenter.java

Es el main que inicia el Call Center.

### Aclaraciones
La codigo se realizo con un mix tanto en español como en ingles.

Cabe aclarar que por defecto:
La cantidad de empleados que se crean siempre es 10. 7 OPERADORES, 2 SUPERVISORES y 1 DIRECTOR.
La cantidad de recursos/telefonos que se crean es 10. Pero se puede elegir otra cantidad en particular, segun se necesite #.
La cantidad de llamadas minimas que se crean es 10. Pero se puede elegir otra cantidad en particular, segun se necesite  #.
La duracion de las llamadas es aleatoria entre 5 y 10. Pero se puede elegir otra duración en particular, segun se necesite #.
 # como se puede ver en los diferentes test.


### TESTS

test10Llamados : Representa el caso de ejemplo minimo solicitado en la consigna.

testCallsQtyResourcesQtyRamdon: Representa el mismo funcionamiento que CallCenter.java.

test20Llamados: Representa el caso en el que entran más de 10 llamadas.
Se atienden las primeras 10 llamadas, y las otras 10 quedan encoladas para ser atendidas a medida que se van liberando empleados.

testLlamadaSinAtender: Representa el caso en el cual una llamada nunca es atendida/completada satisfactoriamente, ya sea por que nunca se libero un empleado o porque la llamada quedo fuera del rango horario de atención del Call Center.

testPriorizacionDeEmpleados: lleva a cabo la validacion de la prioridad en el orden de atencion de los empleados.