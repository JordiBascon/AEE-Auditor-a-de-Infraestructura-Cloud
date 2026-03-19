# AEE Auditoría de Infraestructura Cloud
Para esta actividad la misión era realizar un informe de consultas preciso y eficiente que no afectara al rendimient odel servidor de producción.

Para ello se nos entregaron 5 misiones diferentes las cuales he solucionado y voy a explicar brevemente:

## Misión 1: Mapeo de Seguridad (Navegación Absoluta/Relativa)
Para esta misión se nos pedía extraer los puertos de los servicios que se están ejecutando en el centro de datos con ubicación París.
Para ello debí extraer el atributo ubicación de los centros de datos y mostrar los puertos:
```
/catalogo_cloud/centro_datos[@ubicacion = "Paris"]/servidor/software/servicios/servicio/@puerto /string()
```
## Misión 2: Auditoría de Mantenimiento (Filtrado por Valores)
Para esta misión se nos pedía consultar la versión del sistema operativo del servidor con un identificador en específico.
Para ello, igual que en la misión 1, consulté los atributos de ID que se encuentran en Servidor y mostré su versión del sistema operativo:
```
/catalogo_cloud/centro_datos/servidor[@id = "srv-db-01"]/software/so/@version /string()
```
## Misión 3: Inventario de Alta Capacidad (Predicados Matemáticos)
Para esta misión se nos pedía mostrar los nodos completos de los discos con capacidad mayor o igual a 8TB.
Para ello localicé los discos y en el atributo de capacidad_tb seleccioné los mayores e iguales a 8TB con sus respectivos caracteres (>=):
```
/catalogo_cloud/centro_datos/servidor/hardware/discos/disco[@capacidad_tb >= 8]
```
## Misión 4: Eficiencia Energética (Uso de Funciones o Índices)
Para esta misión se nos pedía identificar el primer servidor (mostrando su nodo completo) que aparece en estado apagado.
Para ello nuevamente utilicé el atributo estado de servidor y el "modificador" [1] que sirve para mostrar únicamente el primero:
```
/catalogo_cloud/centro_datos/servidor[@estado = "apagado"][1]
```
## Misión 5: Desafío del Auditor Senior (Navegación Inversa / Existencia)
Para esta misión se nos pedía extraer la arquitectura de la CPU que pertenece al único servidor con una GPU instalada.
Para ello unicamente localicé ese servidor y mostré el atributo:
```
/catalogo_cloud/centro_datos/servidor/hardware/gpu /string()
```

> Hay varios códigos que no utilizan el "/string()", esto es para mostrar el nodo completo y no un nombre en específico.
