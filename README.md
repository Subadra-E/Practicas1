# Practicas1
Avances de Prácticas 

Consideraciones Previas:

* Considerar la matriz densidad para un sistema de n qubits de dimensión 2^n  

* v1, v2 son vectores estado que pertenecen al espacio del sistema completo

* El vector de estado generado por v1 y v2 es de la forma psi = cos(theta)*v1 + e^(i*phi)*sin(theta)*v2

Funciones Utilizadas:

*TraceSystem*
Creada por
Mark S. Tame
School of Mathematics and Physics, Queen's University, Belfast.  UK.

Esta función calcula trazas parciales sobre cualquiera de los subsistemas. 
Se utilizó para encontrar la matriz densidad reducida del subsistema A.

***************PurezadelsubsistemaAapartirdevectoresestado*************
Calcula la pureza para el estado del subsistema A

Algoritmo Utilizado:
*Tomar al vector estado que pertenece al subespacio generado por v1 y v2
*Construir la matriz densidad 
*Utilizar la función TraceSystem para calcular la matriz densidad reducida del subesistema A
*Calcular la traza del cuadrado de la matriz reducida

***************PuntosendondelaPurezaesMaxima*************
Encuentra los velores de theta y phi para los cuales la pureza del subsistema A es máxima

Algoritmo Utilizado:

*Encontrar puntos críticos:
-Función "Sol"
con la ayuda de FindRoot se encuentran los valores de theta, phi en donde la derivada es cero
tomando distintos puntos de partida

-Con la función "Sol", recorrer distintos pares de valores iniciales theta y phi para encontrar 
los puntos donde la derivada es cero (los valores encontrados se almacenan en la Tabla "data")

*Evaluar si son puntos máximos:
-Con ayuda de las funciones "secdtheta", "secdphi", "secdthetaphi" y "delta" (las cuales calculan
las segundas derivadas y el determinante de la matriz Jacobiana), se evalúan las condiciones para
saber si los valores de theta y phi encontrados devuelven un máximo (los pares seleccionados, se 
almacenan en la tabla "m")

*Eliminar Puntos valores repetidos:
-Con ayuda de "DeleteDuplicates", se eliminan los puntos que tengan una diferencia menor a 10^-13 
(se almacenan en la lista "max")

*Eliminar Puntos en donde aparezacan "Falsos" Máximos:
-Como segundo filtro, se eliminan los valores de theta y phi que devuelven un aparente valor máximo 
en la frontera
