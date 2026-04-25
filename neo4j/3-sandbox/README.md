# Applied graph analytics

Lab ma charakter problemowy — Twoim zadaniem jest przeprowadzenie analizy grafowej rzeczywistego zbioru danych i wyciągnięcie z niego niebanalnych wniosków przy użyciu algorytmów GDS. Ocenie podlega przede wszystkim **analityczne myślenie, uzasadnienie doboru metod i jakość interpretacji wyników** — nie sama techniczna poprawność kodu. W sprawozdaniu każde zapytanie Cypher musi być opatrzone wynikiem (graf lub metryki) i komentarzem.

Uwagi do zaliczenia:
- Sprawozdanie musi dokładnie opisywać podjęte decyzje i uzasadniać wybór algorytmów względem charakterystyki danych.
- Wnioski muszą odnosić się do domeny, a nie tylko do metryk (np. nie *"węzeł A ma PageRank 0.85"*, ale *"użytkownik A jest kluczowym hubem dystrybucji informacji w sieci, ponieważ..."*).
- Przy ewentualnej odpowiedzi ustnej należy omówić realizowany scenariusz, uzasadnić dobór algorytmów i zinterpretować uzyskane wyniki.

## Zadania

1. **[2 pkt]** Wybór i opis datasetu.
    1. Wybierz [sandbox Neo4j](https://sandbox.neo4j.com/) z włączonym GDS (np. Fraud Detection, Twitch, Stack Overflow, Game of Thrones, European Roads) lub zaproponuj własny zbiór danych z publicznych źródeł (np. [SNAP datasets](https://snap.stanford.edu/data/)). Uzasadnij wybór — jakie pytania analityczne chcesz postawić temu zbiorowi?
    2. Opisz schemat bazy: typy węzłów, relacji i ich właściwości. Podaj skalę grafu (liczba węzłów i relacji). Jakie informacje można z niego pozyskać i jakich — nie?

2. **[2 pkt]** Eksploracja struktury grafu.
    1. Zbadaj podstawowe właściwości strukturalne: rozkład stopni węzłów (degree distribution), gęstość grafu, czy jest skierowany. Czy rozkład stopni przypomina prawo potęgowe (power law)? Co to oznacza dla charakteru sieci?
    2. Zidentyfikuj węzły o najwyższej centralności, używając co najmniej dwóch różnych miar. Co oznaczają węzły centralne w kontekście wybranej domeny?

3. **[3 pkt]** Community detection i interpretacja.
    1. Uruchom wybrany algorytm community detection (Louvain, Label Propagation lub Weakly Connected Components). Ile skupisk wykryto i jak są zbalansowane rozmiarem?
    2. Zinterpretuj wykryte skupiska w kontekście domeny. Co łączy węzły należące do tej samej społeczności? Czy wyniki są intuicyjnie sensowne — jeśli nie, jakie mogą być przyczyny?
    3. Zwizualizuj podgraf jednej wybranej społeczności i opisz, co ona reprezentuje.

4. **[3 pkt]** Analiza pogłębiona i wnioski.
    1. Zastosuj co najmniej dwa algorytmy z innych kategorii GDS (path finding, centrality, similarity) w celu pogłębienia analizy lub odpowiedzi na konkretne pytanie badawcze. Uzasadnij dobór algorytmów.
    2. Sformułuj co najmniej trzy niebanalne wnioski z przeprowadzonej analizy w języku domeny.
    3. Oceń, czy baza grafowa była właściwym wyborem dla tego problemu. Jakie pytania analityczne były trudne lub niemożliwe do zadania w relacyjnej bazie?
