# Data modeling in MongoDB

1. **[2 pkt]** Walidacja schematu w MongoDB.
    1. Jak zdefiniować reguły walidacji za pomocą operatora `$jsonSchema`? Przedstaw przykład dla wybranej kolekcji z sample datasetu, definiując typy pól, pola wymagane oraz ograniczenia wartości.
    2. Omów poziomy walidacji (`strict`, `moderate`) oraz akcje (`error`, `warn`). Kiedy stosować każdą z kombinacji i jakie są konsekwencje dla istniejących dokumentów?
    3. Co się dzieje z dokumentem niespełniającym reguł walidacji podczas operacji UPDATE — czy zachowanie różni się od INSERT?
    4. Porównaj możliwości walidacji schematu w MongoDB z ograniczeniami w SQL (`NOT NULL`, `CHECK`, `UNIQUE`, `FOREIGN KEY`). Wskaż, których ograniczeń nie można wyrazić deklaratywnie w MongoDB i jak można je zastąpić.
2. **[2 pkt]** Czym jest indeks? Jakie typy indeksów istnieją w MongoDB? Zalety, wady.
    1. Jak można go tworzyć i jak jest usuwany? Przedstaw przykłady dla czterech typów, które uważasz za istotne — uwzględnij indeks wildcard (`{ "$**": 1 }`) i omów, w jakich scenariuszach elastycznego schematu jest szczególnie przydatny. Jako punkt wyjścia rozważ kolekcję `products`, w której pole `specs` ma różną strukturę w zależności od kategorii produktu:
        ```js
        // laptop
        { name: "Laptop XZ", category: "laptop", specs: { ram: 16, storage: 512, cpu: "i7-12700H" } }
        // telewizor
        { name: 'TV OLED 55"', category: "tv", specs: { screen_size: 55, resolution: "4K", refresh_rate: 120 } }
        // słuchawki
        { name: "Headphones Pro", category: "headphones", specs: { driver_size: 40, impedance: 32, wireless: true } }
        ```
        Ile osobnych indeksów pojedynczych zastępuje jeden `{ "specs.$**": 1 }`? Jak weryfikuje to `explain()`? Jakie są ograniczenia indeksu wildcard (np. compound index, indeksowanie `_id`)?
    2. Jak zmodyfikować istniejący indeks?
    3. Czym jest query planner? Czym różni się index scan (IXSCAN) od collection scan (COLLSCAN)? Jaki ma to wpływ na wydajność wykonania zapytania? Wykorzystaj metodę explain na rzecz kursora.
    4. Do czego można wykorzystać metodę hint?
3. **[1 pkt]** Zaprezentuj budowanie i działanie indeksu na przykładzie wzorca Attribute pattern.
4. **[2 pkt]** Relacje między opisywanymi obiektami a wzorce. Porównaj ze sobą Subset pattern oraz Bucket pattern.
    1. Przedstaw usecasy i implementację oraz zalety i wady dla obydwu wzorców.
    2. Jak zastosowanie wskazanych wzorców może wpływać na indeksy i ich wykorzystanie?
5. **[1 pkt]** W jaki sposób można wykonać SQLową operację JOIN w MongoDB? Przedstaw dwa przykłady. Możesz wykorzystać przykład z Subset pattern.
    1. Jak łączyć dane z dwóch kolekcji? Przedstaw przykłady wykorzystując operator $lookup.
    2. Jaka jest różnica w planie wykonania zapytania między query z $lookup a query do dwóch różnych kolekcji? Wykorzystaj metodę explain na rzecz kursorów.
6. **[2 pkt]** Omów i przedstaw możliwą implementację 2 wybranych wzorców, wykorzystywanych w MongoDB, niewymienionych w tej instrukcji. Listę można znaleźć [tutaj](https://www.mongodb.com/blog/post/building-with-patterns-a-summary).

**Uwaga!** Maksymalną liczbę punktów można otrzymać za przedstawienie przykładów i implementacji innych niż w dokumentacji i blogu MongoDB.
