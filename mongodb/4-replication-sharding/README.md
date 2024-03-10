# MongoDB replication and sharding (10 pkt)
0. Do pracy można wykorzystać dołączoną konfigurację [mongod.conf](./mongod.conf) oraz skrypt [docker-compose.yaml](./docker-compose.yaml) w celu stworzenia trzech instancji mongod. W przypadku shardingu wystarczy wprowadzić drobne modyfikacje.
1. **[2 pkt]** Replica Set:
    - Czym jest replica set i w jakim celu jest wykorzystywany?
    - Przedstaw, jak stworzyć Replica Set, składający się z trzech procesów mongod.
    - Jakie typy węzłów wyróżniane są w replice? Przedstaw ich możliwe przypadki użycia oraz pozwalające na to fragmenty kodu/konfiguracji.
    - Dlaczego liczba węzłów w replice powinna być nieparzysta? Omów na przykładzie.
    - Jakie parametry konfiguracji węzłów repliki są do dyspozycji administratora? Do czego można je wykorzystać?
2.	**[3 pkt]** Sharded cluster:
    - Czym jest sharding i sharded cluster w MongoDB? Przedstaw budowę takiego klastra, wskazując niezbędne do jego prawidłowego funkcjonowania usługi (węzły).
    - Jak można wykorzystać replikację w shardingu? Wskaż, które z węzłów mogą być replikowane i w jaki sposób jest to realizowane.
    - Stwórz shardowany klaster, wykorzystując zasoby lokalnej maszyny lub chmurowe (AWS).
3.	**[3 pkt]** Sharding kolekcji:
    - Omów aspekt wykorzystania indeksów w shardingu kolekcji. Czym jest shard key? Jakie są ograniczenia dotyczące stosowania indeksów w shardingu?
    - Czym są chunki? Jak są wykorzystywane w shardingu?
    - Jakie występują strategie shardowania w MongoDB? Omów, wykorzystując przykładowe dane z Atlasa.
    - Dokonaj shardingu dowolnej kolekcji ze zbioru sample-dataset (mongodb atlas).
4.	**[2 pkt]** Zapytania na kolekcjach poddanych shardingowi:
    - W jaki sposób realizowane jest zapytanie w shardowanym klastrze? Przedstaw dowolny przykład, posługując się dostępnymi w architekturze typami węzłów.
    - Czym są i jaka jest różnica między zjawiskami scatter gather a targeted queries? Wyjaśnij na przykładzie zapytań, wykorzystujących te zjawiska.
