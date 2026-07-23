•	¿Cuántas filas devuelve cada consulta y por qué son distintas?
**Con Union All tomando stock, devuelve 14 filas
UNION no elimino nada porque ninguna fila es 100% idéntica entre sucursales — el stock es lo que las diferencia. 
Si quisieras ver a UNION eliminando filas de verdad, necesitarías que las 4 columnas coincidan exactamente.**

.¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
**UNION ALL simplemente concatena los resultados de ambas consultas, uno atrás del otro. No hay verificación adicional:
toma las filas de la primera tabla, les agrega las de la segunda, y devuelve todo. 
UNION, en cambio, tiene que garantizar que no haya filas duplicadas en el resultado final. Para lograr eso, el motor necesita:
Ordenar (o usar una estructura tipo hash) todas las filas combinadas de ambas consultas.
Comparar cada fila con las demás para detectar cuáles son idénticas en todas sus columnas.
Eliminar las que resulten duplicadas.
Ese paso de ordenamiento/comparación (generalmente un SORT o un HASH DISTINCT internamente) es costoso en términos de
procesamiento, especialmente cuando:
Hay muchas filas (el costo de ordenar crece más rápido que la cantidad de datos).
Las columnas son muchas o pesadas (compara más datos por fila).**

•	¿En qué casos de negocio usarías cada uno? Da al menos dos ejemplos reales distintos a los del ejercicio.
**Union lo usaría para tomar todos los productos para catalogo de marketing o para una campaña de publicidad en Meta.
Union All lo usaría para trabajar auditorias de stock o de sucursales.**

•	¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
**La consulta arrojaría Error. La cantidad de columnas debe ser las misma y debe ser compatibles con tipo de datos.**


