# Redis stream

1. **[1 pkt]** Przedstaw budowę i działanie wzorca pub-sub. W jaki sposób można go wykorzystać? Czym jest Quality of Service (QoS) w pub-sub i jakie wyróżniamy jego poziomy? Wymień i omów pokrótce trzy protokoły, implementujące ten wzorzec.
2. **[1 pkt]** Wykorzystując bazę Redis:
   1. Wyjaśnij, czym są subskrypcje proste (simple syndication) oraz oparte o patterny (pattern syndication)? Jakie typy danych można przesyłać przy pomocy redis pub-sub? Podaj przykłady.
   2. Czym jest glob-style pattern (subscription)?
3. **[3 pkt]** Redis Streams:
   1. Czym jest Redis Streams? Przedstaw oraz omów ich strukturę.
   2. Jak dodawać dane do strumienia? Jaki jest ich format? Przedstaw na przykładzie.
   3. Zaprezentuj, w jaki sposób nasłuchiwać strumień. Uwzględnij tryby blokującego oraz nieblokującego nasłuchiwania. W jaki sposób można wykorzystać każdy z nich?
4. **[2 pkt]** Consumer groups:
   1. Czym są Consumer groupy? Jaki jest cel ich tworzenia? Co umożliwiają?
   2. Omów działanie Consumer groupy na przykładzie, wykorzystując dostępne procedury w redis-cli.
5. **[3 pkt]** Opisz na przykładzie, w jaki sposób Redis streams mogą być wykorzystane jako broker wiadomości dla usług w modelu mikroserwisowym.
