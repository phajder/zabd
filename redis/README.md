# Laboratoria z Valkey jako przykład pamięciowej bazy klucz-wartość

## Kontekst wyboru Valkey

Historycznym punktem odniesienia dla tego modułu jest **Redis** — przez ponad dekadę de facto standard in-memory key-value store w branży. W marcu 2024 roku Redis Ltd. zmieniło licencję z BSD na SSPL/RSALv2, które nie spełniają definicji open-source według OSI. W odpowiedzi społeczność — wspierana przez AWS, Google Cloud, Oracle i Ericsson — sforkował Redis 7.2 pod egidą Linux Foundation, tworząc **Valkey** (licencja BSD).

Valkey jest binarnie i API-kompatybilny z Redisem: każda komenda, każdy typ danych, pub-sub oraz Streams działają identycznie. Valkey jest już domyślnym backendem Amazon ElastiCache i Google Cloud Memorystore. Z perspektywy inżynierskiej przejście na Valkey jest transparentne — z perspektywy architektonicznej jest lekcją o cyklu życia projektów open-source, zrównoważonym finansowaniu i mechanizmie forkowania społeczności.

W labach na ocenę 5.0 używamy **Valkey**. Materiały z Redis University wymienione w scenariuszu 3.0 pozostają aktualne — opisują ten sam protokół i API.

## Scenariusz na 3.0
Do zaliczenia należy przedstawić ukończenie jednego wybranego learning path z Redis University:
* [Redis for Java Developers](https://university.redis.com/courses/ru102j/)
* [Redis for .NET Developers](https://university.redis.com/courses/ru102n/)
* [Redis for Python Developers](https://university.redis.com/courses/ru102py/)
* [Redis for JavaScript Developers](https://university.redis.com/courses/ru102js/)

Jako potwierdzenie wykonania należy załączyć screen potwierdzający ukończenie kursu (np. certyfikat) oraz krótkie sprawozdanie (1-2 strony), co udało się dzięki kursowi nauczyć. Mile widziane listingi kodu.

## Scenariusz na 5.0
1. [Valkey fundamentals](/redis/1-fundamentals/README.md)
2. [Cache models](/redis/2-cache-models/README.md)
3. [Streams](/redis/3-streams/README.md)
