# Neo4j fundamentals

Bazy grafowe modelują świat tak, jak naturalnie go postrzegamy — jako byty połączone relacjami. Tam gdzie bazy relacyjne normalizują połączenia do kluczy obcych i tabel łącznikowych, graf czyni relacje obywatelami pierwszej klasy: mają kierunek, typ i własne właściwości. Sprawia to, że bazy grafowe są naturalnym wyborem wszędzie tam, gdzie połączenia między danymi są równie ważne jak same dane: sieci społecznościowe, silniki rekomendacji, wykrywanie fraudów, grafy wiedzy, analiza zależności pakietów.

1. **[3 pkt]** Model grafowy i budowa bazy.
    1. Czym jest Property Graph Model? Omów jego elementy: węzły (nodes), relacje (relationships), etykiety (labels) oraz właściwości (properties) na węzłach i relacjach. Jaka jest fundamentalna różnica między przechowywaniem informacji jako właściwości węzła a jako osobnego węzła z relacją — kiedy stosować każde podejście?
    2. Wybierz domenę, w której relacje między bytami są kluczowe dla interesujących pytań analitycznych: sieć społecznościowa, system rekomendacji (filmy, produkty), mapa transportowa, sieć zależności (pakiety, mikrousługi), graf wiedzy. Zbuduj bazę zawierającą minimum 50 węzłów, co najmniej 3 typy węzłów oraz co najmniej 4 typy relacji z właściwościami.
    3. Opisz schemat przygotowanej bazy: typy węzłów z właściwościami, typy relacji z kierunkowością i właściwościami. Przedstaw schemat wizualnie (Arrow Tool, Neo4j Browser lub własny rysunek) i załącz do sprawozdania.

2. **[3 pkt]** Cypher — język zapytań grafu.
    1. Opisz, jak działa dopasowanie wzorców (pattern matching) w Cypher. Na czym polega klauzula `MATCH` i czym strukturalnie różni się od `SELECT ... JOIN` w SQL?
    2. Przedstaw operacje CRUD w Cypher na przykładach z własnej bazy:
        - `CREATE` vs `MERGE` — jaka jest różnica i kiedy używać każdego z nich?
        - `MATCH`/`WHERE`/`RETURN` z filtrowaniem właściwości i etykiet
        - `SET`, `REMOVE` — aktualizacja właściwości i etykiet
        - `DELETE` vs `DETACH DELETE` — dlaczego zwykły `DELETE` na węźle może się nie powieść?
    3. Ścieżki o zmiennej długości: przedstaw składnię `[:REL*min..max]` i napisz zapytanie, które odnajduje węzły osiągalne z danego węzła w co najwyżej N krokach. Dlaczego tego rodzaju zapytanie jest trudne lub niemożliwe do efektywnego wyrażenia w SQL bez rekurencji?
    4. Czym jest klauzula `WITH` w Cypher? Przedstaw przykład potokowania wyników między etapami zapytania (np. filtrowanie po agregacji).

3. **[2 pkt]** Indeksy i modelowanie.
    1. Jakie typy indeksów oferuje Neo4j (B-tree, fulltext, LOOKUP, range)? Jak je tworzyć i kiedy każdy z nich jest właściwy?
    2. Omów decyzję o reifikacji relacji (intermediate node pattern): kiedy relacja między dwoma węzłami powinna stać się osobnym węzłem? Zilustruj na przykładzie z własnej bazy (np. relacja "kupił" z datą i ceną jako węzeł "Zakup").

4. **[2 pkt]** Porównanie paradygmatów.
    1. Opisz co najmniej trzy fundamentalne różnice między modelem grafowym a relacyjnym. Weź konkretne zapytanie z własnej bazy (np. znajdź wszystkich znajomych znajomych, najbardziej połączone węzły) i przedstaw je w SQL — co sprawia, że jest ono bardziej naturalne w Cypher?
    2. Jakie podobieństwa można znaleźć między bazą grafową a dokumentową (MongoDB)? W jakich scenariuszach aplikacji webowej wybrałbyś Neo4j zamiast MongoDB i odwrotnie?
