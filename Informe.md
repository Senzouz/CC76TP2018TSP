# Travelling Salesman Problem
## Índice
1. Introducción

Se trata del **Problema del vendedor viajero** o tambien conocido con las siglas TSP (Travelling Salesman Problem). Dicho problema consiste en el recorrido de un conjunto de ciudades alrededor del mapa, el cual tiene como punto de inicio cualquier ciudad. La manera en la cual debe recorrer dicho viajero tiene algunos requerimientos: debe pasar por todas las ciudades, solo una sola vez por ciudad y tener el minimo costo de recorrido (tiempo, costo de viaje, distancia, etc). Luego de dicho recorrido debe regresar al punto inicial. 

A travez del tiempo, se ha producido algunas soluciones: Karl Menger (Shortest Hamiltonian Path, 1930), J.B. Robinson (Hamiltonian game, 1949), G. Dantzig, R. Fulkerson, y S. Johnson (Instancia de 49 ciudades y una introducción de cortes y branching, 1954), M. Held and R.M. Karp (Introducción de heuristicas, 1962) o el mas reciente Cook, Espinoza and Goycoolea (Instancia de 33 000 ciudades, 2005)(1)

El presente trabajo realiza una invesigacion, dentro del marco del Trabajo Parcial para el curso de Complejidad Algoritmica, sobre dicho problema planteado. En primer lugar, se analizara los motivos y las implementaciones en la vida real de dicho problema. En segundo lugar, se analizara el problema, los requistos y el manejo de la data base. En tercer lugar, los objetivos a cumplir. En cuarto lugar se dara un repaso sobre los temas a utilizar. En quinto lugar,se mostrara la posible solucion para luego, en el sexto punto, mostrar los algoritmos implementados para dicha solucion. Por ultimo se analizara la complejidad de la solucion (Big O). Y por ultimo, de dara las conclusiones segun nuestros objetivos

2. Motivación
3. Problema

Dada una colección de ciudades y el costo de viaje entre cada par de ellas, el **TSP** se trata de encontrar el camino más barato en el que se visiten todas estas ciudades y regresar al punto inicial. En su versión estandar, el costro del viaje es simétrico en el sentido que viajar de la ciudad A hacia la ciudad B cuesta lo mismo que viajar de B hacia A.
La simplicidad del enunciado de este problema es engañosa, dado que el TSP es uno de los problemas en matemática computacional más intensamente estudiado y aún no se conoce una solución efectiva para todos los casos.
Aunque la compejidad del TSP aún es desconocida, por más de 50 años su estudio ha guiado el camino para métodos de solución mejorados en muchas áreas de optimización matemática.(2)

4. Objetivos
5. Marco Teórico
6. Solución
7. Algoritmos implementados
8. Complejidad
9. Conclusiones

(1) ESPINOZA, Daniel. El Problema del Vendedor Viajero (TSP) y Programación Entera (IP).Chile. Universidad de Chile. [http://www.dii.uchile.cl/~daespino/PApers/TSP_and_IP_chile_050820.pdf](http://www.dii.uchile.cl/~daespino/PApers/TSP_and_IP_chile_050820.pdf) (Consultado el dia 13 de setiembre de 2018)
(2) COOK, William. The Travelling Salesman Problem. Canada. University of Waterloo. [http://www.math.uwaterloo.ca/tsp/problem/index.html]
