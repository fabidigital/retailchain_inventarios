•	¿Cuántas filas devuelve cada consulta y por qué son distintas?
**Con Union devuelve 11 filas, elimina duplicados  id_ 103,104,105
107 y 111 igual producto con distinto Id_
Con Union All tomando stock, devuelve 14 filas 
Productos con distintos stocks en el inventario.**

.¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
**Con Union All el rendimiento es mayor y trabaja más rápido.
Con Union garantiza que el reporte no tengas filas duplicadas, dando resultados únicos.**

•	¿En qué casos de negocio usarías cada uno? Da al menos dos ejemplos reales distintos a los del ejercicio.
**Union lo usaría para tomar todos los productos para catalogo de marketing o para una campaña de publicidad en Meta.
Union All lo usaría para trabajar auditorias de stock o de sucursales.**

•	¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
**La consulta arrojaría Error. La cantidad de columnas debe ser las misma y debe ser compatibles con tipo de datos.**


