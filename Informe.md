# Travelling Salesman Problem
## Índice
1. Introducción

Se trata del **Problema del vendedor viajero** o tambien conocido con las siglas TSP (Travelling Salesman Problem). Dicho problema 
consiste en el recorrido de un conjunto de ciudades alrededor del mapa, el cual tiene como punto de inicio cualquier ciudad. La manera 
en la cual debe recorrer dicho viajero tiene algunos requerimientos: debe pasar por todas las ciudades, solo una sola vez por ciudad y 
tener el minimo costo de recorrido (tiempo, costo de viaje, distancia, etc). Luego de dicho recorrido debe regresar al punto inicial. 

A travez del tiempo, se ha producido algunas soluciones: Karl Menger (Shortest Hamiltonian Path, 1930), J.B. Robinson (Hamiltonian game, 
1949), G. Dantzig, R. Fulkerson, y S. Johnson (Instancia de 49 ciudades y una introducción de cortes y branching, 1954), M. Held and 
R.M. Karp (Introducción de heuristicas, 1962) o el mas reciente Cook, Espinoza and Goycoolea (Instancia de 33 000 ciudades, 2005)

El presente trabajo realiza una invesigacion, dentro del marco del Trabajo Parcial para el curso de Complejidad Algoritmica, sobre dicho 
problema planteado. En primer lugar, se analizara los motivos y las implementaciones en la vida real de dicho problema. En segundo 
lugar, se analizara el problema, los requistos y el manejo de la data base. En tercer lugar, los objetivos a cumplir. En cuarto lugar se 
dara un repaso sobre los temas a utilizar. En quinto lugar,se mostrara la posible solucion para luego, en el sexto punto, mostrar los 
algoritmos implementados para dicha solucion. Por ultimo se analizara la complejidad de la solucion (Big O). Y por ultimo, de dara las 
conclusiones segun nuestros objetivos

2. Motivación

Una de las principales motivaciones por las cuales se hace el presente trabajo son algunas de las aplicaciones que se le pueden dar a 
nuestro problema, como son: Enrutamientos de vehiculos, estudio de la secuencia de genes, observacion astrologica, diseño de chips y 
otros problemas algoritmicos.

3. Problema

Dada una colección de ciudades y el costo de viaje entre cada par de ellas, el **TSP** se trata de encontrar el camino más barato en el 
que se visiten todas estas ciudades y regresar al punto inicial. En su versión estandar, el costro del viaje es simétrico en el sentido 
que viajar de la ciudad A hacia la ciudad B cuesta lo mismo que viajar de B hacia A.
La simplicidad del enunciado de este problema es engañosa, dado que el TSP es uno de los problemas en matemática computacional más 
intensamente estudiado y aún no se conoce una solución efectiva para todos los casos.
Aunque la compejidad del TSP aún es desconocida, por más de 50 años su estudio ha guiado el camino para métodos de solución mejorados en 
muchas áreas de optimización matemática.

4. Objetivos

  - Objetivo General
        - Mostrar el costo minimo del grafo para y regresar al punto inicial
  - Objetivos Secundarios
        - Implementar el ingreso de la ciudad a la que se quiere llegar

5. Marco Teórico 

- Algoritmo de busqueda por Fuerza Bruta
O tambien llamada búsqueda exhaustiva o como generar y probar, es una técnica muy general de resolución de  problemas y paradigmas
algorítmicos que consiste en enumerar sistemáticamente todos los posibles candidatos para la solución y verificar
si cada candidato satisface la afirmación del problema. Es simple de implementar, y siempre encontrará una solución, si existe. Sin 
embargo su costo es proporcional al número de soluciones candidatas, que en muchos problemas prácticos tiende a crecer muy rápidamente
a medida que aumenta el tamaño del problema. Por lo tanto este algoritmmo se usa cuando el tamaño del problema es limitado o de un
tamaño manejable. El método también se usa cuando la simplicidad de la implementación es más importante que la velocidad.


6. Solución

**Python**
El algoritmo recibe una arreglo de puntos de coordenadas. Calcula el orden minimo de puntos de coordenadas segun su distancia entre 
ellas utilizando fuerza bruta (min). Añade el punto a la lista "camino" y lo retira de "must_visit". Al finalizar, se calcula toda la 
distancia total del camino segun su orden (enumerate).


**C++**

El algoritmo recibe una matriz de adyacencia, y calcula la menor distancia para ir desde una ciudad inicio hacia todas las demás y 
regresar al punto inicial. Al finalizar, retorna la distancia total (minima).

7. Algoritmos implementados

  a. **Algoritmo Heurístico TSP en python** 
```python
def Read(filename):
    G = []
    i = 0
    file = open(filename)
    for line in file:
        G.append([float(x) for x in line.split('\t')])
        
    return G

def distancia(point1, point2):
    return ((point1[0] - point2[0])**2 + (point1[1] - point2[1])**2) ** 0.5


def total_distancia(points):
    return sum([distancia(point, points[index + 1]) for index, point in enumerate(points[:-1])])


def tsp(points, start=None):
    if start is None:
        start = points[0]
    must_visit = points
    camino = [start]
    must_visit.remove(start)
    while must_visit:
        nearest = min(must_visit, key=lambda x: distancia(camino[-1], x))
        camino.append(nearest)
        must_visit.remove(nearest)
    return camino
    
print(total_distancia(tsp(G))) 
 ```
 b. **Algoritmo inocente TSP en C++**
 ```c++
 int TSP(int grafo[][V], int inicio)
{
    vector<int> vertices;
    for (int i = 0; i < V; i++)
        if (i != inicio)
            vertices.push_back(i);
    int camino_minimo = INT_MAX;
    do {
        int peso_actual = 0;
        int k = inicio;
        for (int i = 0; i < vertices.size(); i++) {
            peso_actual += grafo[k][vertices[i]];
            k = vertices[i];
        }
        peso_actual += grafo[k][inicio];
        camino_minimo = min(camino_minimo, peso_actual);        
    } while (next_permutation(vertices.begin(), vertices.end())); 
    return camino_minimo;
}
 ```

8. Complejidad

La complejidad del algoritmo de busqueda por fuerza bruta es de tiempo es O (N!). Por lo que nunca debe usarse en listas largas.
En el caso del algoritmo heurístico la complejidad es de tiempo O(N^2)


9. Conclusiones

Luego de hacer las debidas pruebas, hemos comprobado que se puede impelementar una solucion para TSP en nodos de tamaño corto, debido a que el tiempo en el peor caso posible es factorial de n  


10. Bibliografia

(1) ESPINOZA, Daniel. El Problema del Vendedor Viajero (TSP) y Programación Entera (IP).Chile. Universidad de Chile. [http://www.dii.uchile.cl/~daespino/PApers/TSP_and_IP_chile_050820.pdf](http://www.dii.uchile.cl/~daespino/PApers/TSP_and_IP_chile_050820.pdf) (Consultado el dia 13 de setiembre de 2018)

(2) COOK, William. The Travelling Salesman Problem. Canada. University of Waterloo. [http://www.math.uwaterloo.ca/tsp/problem/index.html]

(3) Traveling Salesman Problem (TSP) Implementation
[https://www.geeksforgeeks.org/traveling-salesman-problem-tsp-implementation/]

(4)Travelling salesman using brute-force and heuristics
[https://codereview.stackexchange.com/questions/81865/travelling-salesman-using-brute-force-and-heuristics]
