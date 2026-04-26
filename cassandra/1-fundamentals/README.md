# Cassandra fundamentals

Cassandra została zaprojektowana z założeniem, że awarie węzłów są normą, a nie wyjątkiem. Jej architektura — pierścień równorzędnych węzłów, replikacja danych, konfigurowalny poziom spójności — bezpośrednio kształtuje model danych i semantykę operacji CQL. Zanim przejdziesz do modelowania, musisz zrozumieć, dlaczego Partition istnieje jako odrębna warstwa abstrakcji i co znaczy "spójność" w systemie bez centralnego węzła decyzyjnego.

1. **[3 pkt]** Podstawowe struktury bazy Apache Cassandra:
    1. Omów następujące struktury: Column, Row, Partition, Table, Keyspace, Cluster. Dla każdej wskaż rolę, jaką pełni w Cassandrze, i porównaj z odpowiednikiem (lub jego brakiem) w relacyjnej bazie danych.
    2. Przedstaw, jak za pomocą CQL można tworzyć te struktury. Zwróć uwagę na elementy składni, których znaczenie jest inne niż w SQL lub gdy odpowiednik nie istnieje (np. `WITH REPLICATION`, `PRIMARY KEY` z wieloma kolumnami).

2. **[2 pkt]** Architektura rozproszona i spójność.
    1. Opisz topologię pierścienia (ring) w Cassandrze. W jaki sposób dane są dystrybuowane między węzłami przy użyciu consistent hashing? Czym jest token i token range?
    2. Czym jest replication factor? Jakie są dostępne strategie replikacji (`SimpleStrategy` vs `NetworkTopologyStrategy`) i kiedy każda z nich jest właściwym wyborem?
    3. Omów poziomy spójności (`ONE`, `QUORUM`, `ALL`, `LOCAL_QUORUM`). Jak wybór poziomu spójności wpływa na dostępność i poprawność danych przy awarii węzła? Gdzie Cassandra sytuuje się w twierdzeniu CAP i jak poziomy spójności pozwalają to "dostroić"?

3. **[3 pkt]** Typy danych w Apache Cassandra:
    1. Wymień typy danych dostępne w Cassandrze. Wskaż, które mają bezpośredni odpowiednik w SQL, a które są charakterystyczne dla modeli nierelacyjnych.
    2. Jakie typy kolekcji oferuje Cassandra (`list`, `set`, `map`, `frozen`)? Czym jest `frozen` i kiedy jego użycie jest wymagane?
    3. Jak można przechowywać dane w formie dokumentów znanych z MongoDB? Omów typ `tuple` oraz User Defined Types (UDT) — kiedy warto z nich korzystać?

4. **[2 pkt]** CQL — operacje na danych.
    1. Stwórz tabelę użytkowników dowolnego systemu z wykorzystaniem typów podstawowych, co najmniej dwóch kolekcji i UDT lub `tuple`. Przedstaw listingi CRUD.
    2. Jaka jest semantyka `INSERT` w Cassandrze? Czym różni się od SQL — co się dzieje, gdy wstawiamy wiersz z istniejącym kluczem głównym? Czym są Lightweight Transactions (`IF NOT EXISTS`, `IF <warunek>`) i jaki jest ich koszt w środowisku rozproszonym?
    3. Czym jest TTL (Time To Live) w Cassandrze? Jak ustawić go na poziomie wiersza i kolumny? Jakie są konsekwencje wygaśnięcia danych (tombstones) dla wydajności odczytu?
