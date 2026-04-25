# Streams

Architektura zdarzeniowa (event-driven architecture) jest fundamentem nowoczesnych systemów mikroserwisowych — zamiast synchronicznych wywołań API usługi komunikują się przez wymianę zdarzeń, co zwiększa ich odporność na awarie, ułatwia skalowanie i odsprzęga cykl życia producenta od konsumenta. Valkey oferuje dwa mechanizmy wymiany wiadomości: pub-sub oraz Streams, które mają różne gwarancje dostarczania i odpowiadają różnym potrzebom architektonicznym. Wybór między nimi, a także między Valkey a dedykowanymi brokerami jak Apache Kafka czy RabbitMQ, jest jedną z kluczowych decyzji projektowych w architekturze rozproszonej.

1. **[1 pkt]** Przedstaw budowę i działanie wzorca pub-sub. W jaki sposób można go wykorzystać? Czym jest Quality of Service (QoS) w pub-sub i jakie wyróżniamy jego poziomy? Wymień i omów pokrótce trzy protokoły implementujące ten wzorzec.
2. **[2 pkt]** Pub-sub w Valkey i jego granice.
   1. Wyjaśnij, czym są subskrypcje proste (simple syndication) oraz oparte o patterny (pattern syndication). Jakie typy danych można przesyłać przy pomocy pub-sub w Valkey? Podaj przykłady. Czym jest glob-style pattern?
   2. Jakie jest najważniejsze ograniczenie pub-sub w Valkey w kontekście niezawodności systemu? Co się dzieje z wiadomościami wysłanymi do kanału, gdy w danej chwili nie ma żadnego subskrybenta? Jakie ma to konsekwencje dla architektury — kiedy pub-sub jest wystarczający (np. powiadomienia live, broadcasting), a kiedy jego brak persistencji jest nieakceptowalny i należy sięgnąć po Streams?
3. **[3 pkt]** Streams w Valkey:
   1. Czym są Streams? Przedstaw oraz omów ich strukturę.
   2. Jak dodawać dane do strumienia? Jaki jest ich format? Przedstaw na przykładzie z użyciem `valkey-cli`.
   3. Zaprezentuj, w jaki sposób nasłuchiwać strumień. Uwzględnij tryby blokującego oraz nieblokującego nasłuchiwania. W jaki sposób można wykorzystać każdy z nich?
4. **[2 pkt]** Consumer groups:
   1. Czym są Consumer groupy? Jaki jest cel ich tworzenia? Co umożliwiają?
   2. Omów działanie Consumer groupy na przykładzie, wykorzystując dostępne procedury w `valkey-cli`. Uwzględnij mechanizm potwierdzeń (`XACK`) oraz podgląd wiadomości oczekujących (`XPENDING`) — co się dzieje z wiadomością, która nie została potwierdzona przez konsumenta? Jak można to wykorzystać do budowania konsumentów odpornych na awarie?
5. **[2 pkt]** Opisz na przykładzie, w jaki sposób Streams w Valkey mogą być wykorzystane jako broker wiadomości dla usług w modelu mikroserwisowym. Uwzględnij następujące:
   1. Zaprojektuj uproszczony schemat komunikacji między co najmniej trzema usługami z wykorzystaniem Streams i consumer groups. Uwzględnij obsługę błędów i ponowne przetwarzanie niepotwierdzonych wiadomości.
   2. W jakich przypadkach Valkey Streams jest wystarczającym wyborem jako broker wiadomości, a kiedy należy sięgnąć po dedykowane rozwiązanie? Porównaj z Apache Kafka i RabbitMQ pod kątem: retencji i replay wiadomości, partycjonowania, throughputu, gwarancji dostarczania (at-least-once vs exactly-once) oraz złożoności operacyjnej.
