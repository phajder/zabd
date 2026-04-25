# Aggregation Framework
1. **[1 pkt]** Czym jest Aggregation Framework w MongoDB? Opisz pokrótce zalety, wady oraz jego podstawowe ograniczenia. Do czego służy parametr allowDiskUse? Co on umożliwia i jakie są konsekwencje jego użycia? W jakich przypadkach nie można go wykorzystać?
2. **[2 pkt]** Podstawowe stage w Aggregation pipeline: $match, $project, $sort, $skip, $limit.
    1. Czym są stage i jak są wykorzystywane w Aggregation Frameworku? Omów na przykładzie wymienionych stagów.
    2. W jaki sposób układ stagów względem siebie wpływa na wydajność zapytania?
    3. Zaproponuj dwa pipeliny, wykorzystujące co najmniej trzy ze wskazanych stagów oraz wskaż ich znaczenie (usecase).
3. **[2 pkt]** Praca z tablicami i agregacją. Stage $project, $unwind, $group oraz operatory tablicowe.
    1. Wyjaśnij znaczenie stagów $unwind, $group. Przedstaw ich przykładowe zastosowanie.
    2. Przedstaw pięć różnych wyrażeń tablicowych, które można wykorzystać w połączeniu ze wskazanymi w p. a stagami. Wybierz te, które uważasz za przydatne/istotne. Czy istnieją jakieś ograniczenia w ich stosowaniu w połączeniu ze wskazanymi stagami?
    3. Czym są akumulatory i jak można je wykorzystywać? Podaj po dwa przykłady dla stagów $project oraz $group. Jakie są różnice i podobieństwa?
4. **[2 pkt]** Funkcje okienkowe: stage `$setWindowFields`.
    1. Czym są funkcje okienkowe (window functions)? Jaka jest kluczowa różnica między `$setWindowFields` a `$group` — co się dzieje z dokumentami wyjściowymi w każdym z tych stagów?
    2. Korzystając z kolekcji `sample_mflix.movies`, zaimplementuj ranking filmów według oceny IMDb w obrębie gatunku. Odpowiednik SQL poniżej — przedstaw analogiczny pipeline MongoDB, wyjaśniając rolę parametrów `partitionBy`, `sortBy` oraz operatora `$rank`:
        ```sql
        SELECT title, genre, imdb_rating,
               RANK() OVER (PARTITION BY genre ORDER BY imdb_rating DESC) AS rank_in_genre
        FROM movies;
        ```
    3. Korzystając z tej samej kolekcji, zaimplementuj skumulowaną liczbę filmów wydanych do danego roku (running total). Odpowiednik SQL poniżej — zwróć uwagę na rolę parametru `window: { documents: ["unbounded", "current"] }`:
        ```sql
        SELECT year, COUNT(*) AS movies_that_year,
               SUM(COUNT(*)) OVER (ORDER BY year ROWS UNBOUNDED PRECEDING) AS cumulative_total
        FROM movies
        GROUP BY year
        ORDER BY year;
        ```
    4. Jakie inne operatory są dostępne w `$setWindowFields` (np. `$denseRank`, `$documentNumber`, `$shift`, `$expMovingAvg`)? Wskaż po jednym usecasie dla dwóch wybranych.
5. **[2 pkt]** Praca na wielu kolekcjach. Stage $lookup oraz $graphLookup. Omów wszystkie parametry tych stagów. Wskaż, które są obowiązkowe a które opcjonalne. Przedstaw po dwa przykłady do każdego, wykorzystując również inne stage, np. $project, $match, $limit.
6. **[1 pkt]** Do czego służą stage $facet, $function oraz $accumulator? Przedstaw po jednym usecasie dla każdego z nich oraz wytłumacz na tym przykładzie ich znaczenie.