# Cassandra data modeling

1. **[3 pkt]** Czym jest klucz główny? Jak go konstruować? Z czego się składa? Jakie są główne różnice między jego odpowiednikiem w bazie relacyjnej?
    1. Jak sortuje się dane w Cassandrze? Czym jest Clustering Column? Jaka jest jego rola w sortowaniu danych?
    2. Czym jest Partition Key? Jaką pełni rolę? Jak jest wykorzystywany w zapytaniach?
2. **[5 pkt]** Czym jest denormalizacja? W jakim celu się ją wykonuje? Jaki jest jej cel w Cassandrze?
    1. W jaki sposób zamodelować ten system w Cassandrze? Od czego należy zacząć?
    2. Stwórz schemat prostej wypożyczalni filmów, składający się z następujących tabel: wideo, gatunek oraz tabelę wypożyczeń (user, video).Dodatkowo wykorzystaj tabelę użytkowników z lab9.
    3. W jaki sposób skonstruować temat w bazie relacyjnej? Przedstaw diagram ERD.
    4. Napisz zapytania:
        1. Wypożyczone przez użytkownika filmy. 
        2. Filmy z wskazanego jako argument gatunku. 
        3. Wypożyczone przez użytkownika filmy względem gatunku. 
3. **[2 pkt]** Przedstaw podobieństwa i różnice w modelowaniu struktury danych między bazą relacyjną a Cassandrą.
