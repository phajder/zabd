# MongoDB fundamentals

1. Na klastrze MongoDB Atlas dostępne są zbiory testowe. Załaduj je do bazy, zgodnie z dokumentacją: https://docs.atlas.mongodb.com/sample-data. Zestaw ten można znaleźć również na cloudzie (zabd2022-samples.zip).
2. **[1 pkt]** Przedstaw i przeanalizuj struktury danych w MongoDB:
    - Bazodanowe, np. Database, Collection, Document i inne.
    - Typy podstawowe (prymitywne), np. Number, String i inne.
    - Typ tablicowy (Array).
    - Typ zagnieżdżony (embedded document, subdocument).
3. **[4 pkt]** Stwórz CRUDy do wybranych kolekcji i przedstaw je w formie listingów, wraz ze stosownym opisem. Uwzględnij co następuje, mając w szczególności na uwadze typy wymienione w zad. 2:
    1. _(CREATE)_ Jaką strukturę mogą, a jaką muszą mieć dodawane dokumenty? Jakie dane są obowiązkowe a jakie fakultatywne? Opisz operacje wsadowe (`insertMany`, `bulkWrite`) i omów ich znaczenie dla wydajności.
    2. _(READ)_ Wyszukiwanie dokumentów w pojedynczej kolekcji. Do czego służą i jak są wykorzystywane $-operators? Opisz rolę kursora jako obiektu wynikowego metody `find()` — jego cykl życia, metody `limit()`, `skip()`, `sort()` oraz wpływ kolejności tych operatorów na wydajność zapytania.
    3. _(UPDATE)_ Aktualizacja dokumentów. W jaki sposób można je wykonywać? Jakie są możliwe aktualizacje typów tablicowych i zagnieżdżonych?
    4. _(DELETE)_ Jakie są możliwe sposoby usuwania dokumentów lub jego składowych (np. za pomocą UPDATE)?
4. **[2 pkt]** Transakcje w MongoDB.
    1. Czym jest atomowość pojedynczego dokumentu? W jakich przypadkach jest wystarczająca, a kiedy wymaga uzupełnienia transakcją multi-dokumentową? Podaj przykłady obu scenariuszy.
    2. Opisz mechanizm transakcji multi-dokumentowych w MongoDB. Czym jest sesja (`ClientSession`) i jak się ją tworzy? Przedstaw szkielet kodu realizującego transakcję z obsługą commit i abort.
    3. Jakie są konsekwencje wydajnościowe stosowania transakcji w środowisku rozproszonym (replica set, sharded cluster)? Dlaczego dobrze zaprojektowany model danych powinien minimalizować ich stosowanie?
    4. Porównaj poziomy izolacji transakcji w MongoDB z ich odpowiednikami w SQL (`READ COMMITTED`, `SNAPSHOT ISOLATION`). Jakie gwarancje spójności oferuje MongoDB domyślnie i jak można je konfigurować za pomocą `readConcern` oraz `writeConcern`?
5. **[2 pkt]** Przedstaw na przykładach, w jaki sposób w MongoDB modeluje się relacje o licznościach 1:1, 1:n oraz n:m. Omów krótko różnice w operacjach CRUDowych w zależności od sposobu reprezentacji relacji.
6. **[1 pkt]** Na podstawie wcześniejszych zadań przedstaw główne różnice pomiędzy bazami relacyjnymi a MongoDB. Uwzględnij gwarancje spójności (atomowość, transakcje, izolacja), elastyczność schematu oraz operacje niewykonywalne w jednej z klas baz.
