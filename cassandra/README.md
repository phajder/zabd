# Laboratoria z Apache Cassandra jako przykład bazy dla zastosowań write-heavy

Apache Cassandra jest rozproszoną bazą danych zaprojektowaną do masowego zapisu bez pojedynczego punktu awarii. Jej architektura jest fundamentalnie inna niż pozostałych baz omawianych w tym kursie: każdy węzeł jest równorzędny (brak primary/secondary), dane są replikowane na wielu węzłach według konfigurowalnego replication factor, a spójność jest parametrem operacyjnym, nie właściwością systemu. Cassandra zajmuje pozycję AP w twierdzeniu CAP — dostępność i tolerancja podziału kosztem spójności ścisłej. Napędza infrastrukturę Discorda (miliardy wiadomości dziennie), Netflixa (historia oglądania), Apple (iCloud) i dziesiątek innych systemów wymagających sub-milisekundowych zapisów przy ogromnych wolumenach.

## Scenariusz na 3.0
Należy wykonać jeden ze wskazanych kursów dostępnych na platformach DataStax lub Apache Cassandra:
* [DS201: Foundations of Apache Cassandra](https://datastax.academy/course/view.php?id=6) *(DataStax Academy)*
* [DS220: Data Modeling with Apache Cassandra](https://datastax.academy/course/view.php?id=7) *(DataStax Academy)*
* [Apache Cassandra — Getting Started](https://cassandra.apache.org/doc/latest/cassandra/getting_started/) + wybrany kurs z [DataStax Academy](https://datastax.academy/)

**Uwaga!** Dopuszcza się wykonanie dwóch kursów za łączną liczbę punktów 20 (tj. full za ten moduł). Kursy DataStax Academy mogą odnosić się do starszych wersji Cassandry — warto sprawdzić aktualną dokumentację [Apache Cassandra 5.x](https://cassandra.apache.org/doc/latest/) w przypadku rozbieżności.

Jako potwierdzenie wykonania należy załączyć screen potwierdzający ukończenie kursu (np. certyfikat) oraz krótkie sprawozdanie (1-2 strony), co udało się dzięki kursowi nauczyć. Mile widziane listingi kodu.

## Scenariusz na 5.0
1. [Cassandra fundamentals](/cassandra/1-fundamentals/README.md)
2. [Data modeling in Cassandra](/cassandra/2-data-modeling/README.md)
