# MongoDB fundamentals

1. Na klastrze MongoDB Atlas dostępne są zbiory testowe. Załaduj je do bazy, zgodnie z dokumentacją: https://docs.atlas.mongodb.com/sample-data. Zestaw ten można znaleźć również na cloudzie (zabd2022-samples.zip).
2. **[1 pkt]** Przedstaw i przeanalizuj struktury danych w MongoDB:
    - Bazodanowe, np. Database, Collection, Document i inne.
    - Typy podstawowe (prymitywne), np. Number, String i inne.
    - Typ tablicowy (Array).
    - Typ zagnieżdżony (embedded document, subdocument).
3. **[4 pkt]** Stwórz CRUDy do wybranych kolekcji i przedstaw je w formie listingów, wraz ze stosownym opisem. Uwzględnij co następuje, mając w szczególności na uwadze typy wymienione w zad2:
    1. _(CREATE)_ Jaką strukturę mogą, a jaką muszą mieć dodawane dokumenty? Jakie dane są obowiązkowe a jakie fakultatywne?
    2. _(READ)_ Wyszukiwanie dokumentów w pojedynczej kolekcji. Do czego służą i jak są wykorzystywane $-operators?
    3. _(UPDATE)_ Aktualizacja dokumentów. W jaki sposób można je wykonywać? Jakie są możliwe aktualizacje typów tablicowych i zagnieżdżonych?
    4. _(DELETE)_ Jakie są możliwe sposoby usuwania dokumentów lub jego składowych (np. za pomocą UPDATE)?
4. **[1 pkt]** Opisz znaczenie i działanie kursorów w MongoDB (cursor, limit, skip, sort). Jak się go tworzy? Do czego się je wykorzystuje? Jaki jest ich cykl życia? Uwzględnij wpływ tych operatorów na wydajność zapytań.
5. **[2 pkt]** Przedstaw na przykładach, w jaki sposób w MongoDB modeluje się relacje o licznościach 1:1, 1:n oraz n:m. Omów krótko różnice w operacjach CRUDowych w zależności od sposobu reprezentacji relacji.
6. **[2 pkt]** Na podstawie wcześniejszych zadań przedstaw główne różnice pomiędzy bazami relacyjnymi a MongoDB. Uwzględnij również operacje, które nie są wykonywalne w jednej bądź drugiej klasie baz.
