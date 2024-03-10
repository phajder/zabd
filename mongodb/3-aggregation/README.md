# Aggregation Framework
1. **[1 pkt]** Czym jest Aggregation Framework w MongoDB? Opisz pokrótce zalety, wady oraz jego podstawowe ograniczenia. Do czego służy parametr allowDiskUse? Co on umożliwia i jakie są konsekwencje jego użycia? W jakich przypadkach nie można go wykorzystać?
3. **[2 pkt]** Podstawowe stage w Aggregation pipeline: $match, $project, $sort, $skip, $limit.
    1. Czym są stage i jak są wykorzystywane w Aggregation Frameworku? Omów na przykładzie wymienionych stagów.
    2. W jaki sposób układ stagów względem siebie wpływa na wydajność zapytania?
    3. Zaproponuj dwa pipeliny, wykorzystujące co najmniej trzy ze wskazanych stagów oraz wskaż ich znaczenie (usecase).
4. **[2 pkt]** Praca z tablicami i agregacją. Stage $project, $unwind, $group oraz operatory tablicowe.
    1. Wyjaśnij znaczenie stagów $unwind, $group. Przedstaw ich przykładowe zastosowanie.
    2. Przedstaw pięć różnych wyrażeń tablicowych, które można wykorzystać w połączeniu ze wskazanymi w p. a stagami. Wybierz te, które uważasz za przydatne/istotne. Czy istnieją jakieś ograniczenia w ich stosowaniu w połączeniu ze wskazanymi stagami?
    3. Czym są akumulatory i jak można je wykorzystywać? Podaj po dwa przykłady dla stagów $project oraz $group. Jakie są różnice i podobieństwa?
5. **[1 pkt]** Dane geograficzne a Aggregation Framework. Opisz pokrótce stage $geoNear i przedstaw dwa usecasy.
6. **[2 pkt]** Praca na wielu kolekcjach. Stage $lookup oraz $graphLookup. Omów wszystkie parametry tych stagów. Wskaż, które są obowiązkowe a które opcjonalne. Przedstaw po dwa przykłady do każdego, wykorzystując również inne stage, np. $project, $match, $limit.
7. **[2 pkt]** Do czego służą stage $facet, $function oraz $accumulator? Przedstaw po jednym usecasie dla każdego z nich oraz wytłumacz na tym przykładzie ich znaczenie.