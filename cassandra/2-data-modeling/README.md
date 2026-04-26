# Cassandra data modeling

Modelowanie danych w Cassandrze jest odwróceniem procesu projektowania relacyjnego. W SQL zaczyna się od encji i relacji (ERD), a zapytania dostosowuje do modelu. W Cassandrze zaczyna się od **zapytań** — tabel tworzy się dokładnie tyle, ile potrzeba wzorców dostępu, i każda tabela jest zoptymalizowana pod jedno konkretne zapytanie. To podejście, zwane **query-first design**, jest konsekwencją ograniczeń wynikających z architektury rozproszonej: brak JOINów, brak efektywnych indeksów drugorzędnych, brak możliwości filtrowania po dowolnym polu.

1. **[4 pkt]** Klucz główny, partycjonowanie i jakość modelu.
    1. Czym jest klucz główny w Cassandrze? Z czego się składa (Partition Key, Clustering Columns)? Jakie są główne różnice między nim a PRIMARY KEY w SQL?
    2. Czym jest Partition Key? Jaką pełni rolę w dystrybucji danych? Jak jest wykorzystywany przez koordynatora zapytania do zlokalizowania właściwego węzła?
    3. Czym jest Clustering Column? Jaka jest jego rola w sortowaniu danych wewnątrz partycji? Jak kierunek sortowania (`ASC`/`DESC`) wpływa na efektywność zapytań zakresowych?
    4. Omów zasadę **query-first design**: dlaczego w Cassandrze projektuje się tabele pod zapytania, a nie pod encje? Jakie są konsekwencje braku JOINów i ograniczonej użyteczności indeksów drugorzędnych (pełny skan klastra) dla procesu modelowania?
    5. Co to jest **hot partition**? Podaj przykład złego wyboru klucza partycji, który prowadzi do nierównomiernego rozkładu danych (np. `status`, `kraj`, `data`). Jak composite partition key może rozwiązać ten problem? Jakie są zalecane ograniczenia rozmiaru pojedynczej partycji?

2. **[4 pkt]** Denormalizacja i schemat aplikacji.
    1. Czym jest denormalizacja? W jakim celu się ją wykonuje w Cassandrze i dlaczego jest nie tylko dopuszczalna, ale często wymagana?
    2. Zaprojektuj schemat prostej wypożyczalni filmów dla poniższych wzorców dostępu. Skorzystaj z tabeli użytkowników przygotowanej w [Lab 1](/cassandra/1-fundamentals/README.md):
        - Pobierz listę filmów wypożyczonych przez danego użytkownika.
        - Pobierz filmy z wybranego gatunku.
        - Pobierz filmy wypożyczone przez użytkownika z wybranego gatunku.

        Dla każdego wzorca dostępu zaprojektuj osobną tabelę (lub uzasadnij, kiedy jedna tabela wystarczy). Przedstaw zapytania CQL tworzące tabele i realizujące każdy wzorzec.
    3. Przedstaw, jak ten sam problem wyglądałby w bazie relacyjnej — narysuj diagram ERD. Wskaż, które zapytania SQL wymagałyby JOINów niemożliwych w Cassandrze.
    4. Czym są indeksy drugorzędne w Cassandrze i dlaczego należy używać ich ostrożnie? Kiedy są akceptowalnym rozwiązaniem, a kiedy prowadzą do pełnego skanu klastra?

3. **[2 pkt]** Porównanie paradygmatów modelowania.
    1. Przedstaw najważniejsze różnice w procesie modelowania danych między bazą relacyjną a Cassandrą. Uwzględnij: punkt wyjścia (encje vs zapytania), normalizację vs denormalizację, obsługę relacji, oraz implikacje dla ewolucji schematu.
    2. W jakich scenariuszach wybrałbyś Cassandrę zamiast MongoDB lub Valkey? Czy mogą współistnieć w jednej architekturze — podaj przykład systemu, który korzystałby z więcej niż jednej z omawianych baz.
