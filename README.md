# Numari — Agentes de búsqueda (DFS, BFS y A*)

Implementación del puzzle **Numari** jugable por consola, junto a tres agentes de
búsqueda que lo resuelven automáticamente. Proyecto de *Introducción a la
Inteligencia Artificial* (ITLA).

## El juego

En Numari empiezas en una celda con número y debes caminar exactamente esa cantidad
de celdas vacías hasta llegar al siguiente número, repitiendo el proceso hasta visitar
**todas** las celdas del tablero. Incluye 16 niveles (de 3x3 fácil a 10x10 muy difícil)
y soporta niveles personalizados desde archivos `.txt`.

## Los agentes

| Agente | Estructura | Detalle |
|---|---|---|
| **DFS** | Pila explícita | Expansión UDLR inversa al push |
| **BFS** | Cola (deque) | Garantiza el camino más corto |
| **A\*** | Cola de prioridad | `f(n) = g(n) + h(n)` con 5 heurísticas normalizadas |

Las heurísticas de A\* (celdas restantes, pasos pendientes, números restantes,
aislamiento y distancia Manhattan) se combinan con **8 configuraciones de pesos**
para comparar su efecto en la búsqueda.

Cada ejecución reporta métricas estándar: camino a la meta, costo, nodos expandidos,
profundidad de búsqueda, tiempo y uso máximo de RAM.

## Archivos

- [`Numari_Agentes_Final.ipynb`](Numari_Agentes_Final.ipynb) — versión completa con los tres agentes y el menú
- [`Numari_final.ipynb`](Numari_final.ipynb) — versión del juego jugable
- [`Numari_Benchmark.xlsx`](Numari_Benchmark.xlsx) — resultados comparativos de los agentes

## Cómo ejecutarlo

Diseñado para **Google Colab** (usa `google.colab.output` para limpiar la pantalla
del menú). Abrir el notebook, ejecutar las celdas en orden y la última celda inicia
el menú interactivo: elegir nivel, jugar manualmente o dejar que un agente lo resuelva.
