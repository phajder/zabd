# Data modeling in MongoDB

1. **[2 pkt]** Czym jest indeks? Jakie typy indeksów istnieją w MongoDB? Zalety, wady.
    1. Jak można go tworzyć i jak jest usuwany? Przedstaw przykłady dla trzech dowolnych typów, które uważasz za istotne.
    2. Jak zmodyfikować istniejący indeks?
    3. Czym jest query planner? Czym różni się index scan (IXSCAN) od collection scan (COLLSCAN)? Jaki ma to wpływ na wydajność wykonania zapytania? Wykorzystaj metodę explain na rzecz kursora.
    4. Do czego można wykorzystać metodę hint?
2. **[1 pkt]** Zaprezentuj budowanie i działanie indeksu na przykładzie wzorca Attribute pattern.
3. **[2 pkt]** Relacje między opisywanymi obiektami a wzorce. Porównaj ze sobą Subset pattern oraz Bucket pattern.
    1. Przedstaw usecasy i implementację oraz zalety i wady dla obydwu wzorców.
    2. Jak zastosowanie wskazanych wzorców może wpływać na indeksy i ich wykorzystanie?
4. **[1 pkt]** W jaki sposób można wykonać SQLową operację JOIN w MongoDB? Przedstaw dwa przykłady. Możesz wykorzystać przykład z Subset pattern.
    1. Jak łączyć dane z dwóch kolekcji? Przedstaw przykłady wykorzystując operator $lookup.
    2. Jaka jest różnica w planie wykonania zapytania między query z $lookup a query do dwóch różnych kolekcji? Wykorzystaj metodę explain na rzecz kursorów.
5. **[4 pkt]** Omów i przedstaw możliwą implementację 4 wybranych wzorców, wykorzystywanych w MongoDB, niewymienionych w tej instrukcji. Listę można znaleźć [tutaj](https://www.mongodb.com/blog/post/building-with-patterns-a-summary).

**Uwaga!** Maksymalną liczbę punktów można otrzymać za przedstawienie przykładów i implementacji innych niż w dokumentacji i blogu MongoDB.
