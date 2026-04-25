# Graph algorithms in Neo4j

Neo4j Graph Data Science (GDS) to biblioteka algorytmów grafowych uruchamianych bezpośrednio w silniku bazodanowym. Zamiast eksportować dane do zewnętrznych narzędzi analitycznych, GDS operuje na grafie reprezentowanym w pamięci jako **projected graph** — lekka projekcja podzbioru węzłów i relacji, zoptymalizowana pod obliczenia. Dokumentację wszystkich algorytmów GDS znajdziesz [tutaj](https://neo4j.com/docs/graph-data-science/current/algorithms/).

1. **[2 pkt]** GDS workflow.
    1. Czym jest projected graph i dlaczego GDS operuje na projekcji zamiast bezpośrednio na grafie bazodanowym? Jakie informacje podaje się przy tworzeniu projekcji (`gds.graph.project`)?
    2. GDS oferuje cztery tryby wykonania algorytmu: `stream`, `stats`, `mutate`, `write`. Czym się różnią? Kiedy każdy z nich jest właściwym wyborem — np. kiedy `mutate` zamiast `write`?
    3. Stwórz projected graph z bazy przygotowanej w Lab 1 lub przygotuj nowy graf (minimum 30 węzłów). Zaprezentuj pełny workflow dla dowolnego algorytmu: `gds.graph.project` → uruchomienie w trybie `stream` → zapis wyników do właściwości węzłów.

2. **[2 pkt]** Path finding.
    1. Opisz i zaprezentuj algorytm **Dijkstra** (shortest weighted path) oraz **A\*** (heuristic shortest path). Jaka jest między nimi różnica i kiedy warto stosować heurystykę? Jakie są wymagania co do wag krawędzi?
    2. Opisz dwa inne wybrane algorytmy z kategorii [Path Finding](https://neo4j.com/docs/graph-data-science/current/algorithms/pathfinding/) (np. Yen's k-shortest paths, BFS, DFS, Random Walk). Wskaż ich zasadę działania i usecase różny od klasycznego shortest path.

3. **[2 pkt]** Centrality.
    1. Opisz i zaprezentuj **PageRank**. Jaka jest jego intuicja (dlaczego uwzględnia "jakość" sąsiadów, nie tylko ich liczbę)? Podaj dwa usecasy poza wyszukiwarkami (np. wykrywanie wpływowych węzłów w sieci fraudowej, ranking produktów).
    2. Opisz dwa inne wybrane algorytmy z kategorii [Centrality](https://neo4j.com/docs/graph-data-science/current/algorithms/centrality/) (np. Betweenness, Closeness, Degree, Eigenvector). Czym się różni mierzona przez nie "ważność" węzła w sieci?

4. **[2 pkt]** Community detection.
    1. Opisz algorytm **Louvain** lub **Label Propagation**. Na czym polega optymalizacja modularności w Louvain? Czym różni się od Label Propagation pod kątem deterministyczności i skalowalności?
    2. Uruchom wybrany algorytm community detection na swoim grafie. Ile skupisk wykryto i jak są zbalansowane? Zinterpretuj wyniki w kontekście wybranej domeny — co łączy węzły należące do tej samej społeczności?

5. **[2 pkt]** Similarity.
    1. Opisz dwa wybrane algorytmy z kategorii [Similarity](https://neo4j.com/docs/graph-data-science/current/algorithms/similarity/) (np. Node Similarity, K-Nearest Neighbors). Na czym polega różnica w sposobie mierzenia podobieństwa przez każdy z nich?
    2. Przedstaw zastosowanie algorytmu similarity w kontekście systemu rekomendacji. Jak wyniki można przetłumaczyć na rekomendacje — jakie zapytanie Cypher pozwala odczytać K najbliższych sąsiadów jako listę rekomendacji?
