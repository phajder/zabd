# Valkey fundamentals

Valkey (fork Redisa 7.2, Linux Foundation, 2024) jest jedną z najszerzej stosowanych baz in-memory w nowoczesnym software engineeringu — znajdziemy go jako warstwę cache, magazyn sesji użytkownika, kolejkę zadań, broker wiadomości i silnik rate-limitingu niemal w każdym projekcie webowym działającym w skali. Jego model klucz-wartość z rozbudowanymi typami danych i gwarancją atomowości pojedynczych operacji sprawia, że jest pierwszym wyborem tam, gdzie liczy się niska latencja i wysoka przepustowość. Kontekst licencyjny przejścia Redis → Valkey opisano w [README modułu](/redis/README.md).

1. **[2 pkt]** Czym są klucze w Valkey? Jaka jest ich rola w bazie? Jaki jest ich czas życia i od czego on zależy? Jakie są dobre praktyki przy tworzeniu nazw kluczy? Omów na przykładach w trakcie realizacji kolejnych zadań.
2. **[3 pkt]** Przedstaw [typy danych](https://valkey.io/topics/data-types/) dostępnych w Valkey. Omów, w jaki sposób są zaimplementowane, jak można je wykorzystać oraz przedstaw typowe usecasy. Uwzględnij następujące:
   1. Przedstaw, w jaki sposób reprezentowane są wartości numeryczne w Valkey.
   2. Zaprezentuj działanie i wykorzystanie funkcji dostępnych poprzez `valkey-cli` do obsługi omówionych w poprzednim punkcie typów danych.
   3. Opisz funkcje pozwalające na pracę ze zmiennymi liczbowymi.
   4. Jak zrealizować w Valkey implementację kolejki oraz stosu?
   5. Czym jest HyperLogLog? Jak działa i jakie gwarancje dokładności oferuje? Przedstaw usecase w kontekście webowym (np. zliczanie unikalnych użytkowników lub adresów IP bez przechowywania pełnych zbiorów). Jaka jest jego kluczowa przewaga pamięciowa nad strukturą Set przy dużej kardynalności?
3. **[1 pkt]** Stwórz CRUDy, wykorzystujące każdy z wymienionych w zadaniu 2. W tym celu możesz wykorzystać kolekcje z sample datasetu, używanych na lab1-4 z zakresu MongoDB.
4. **[2 pkt]** Webowe wzorce użycia Valkey. Valkey jest obecny w niemal każdej produkcyjnej aplikacji webowej jako infrastruktura wspierająca kluczowe mechanizmy. Przedstaw i zaimplementuj poniższe wzorce, omawiając dla każdego z nich, dlaczego Valkey jest lepszym wyborem niż relacyjna baza danych:
   1. _(Session store)_ W jaki sposób Valkey jest wykorzystywany do przechowywania sesji użytkownika w aplikacjach webowych? Omów serializację danych sesji, strategię TTL z odświeżaniem (sliding expiration) oraz co się dzieje z aktywnymi sesjami przy restarcie Valkey bez włączonej persistencji.
   2. _(Rate limiting)_ Jak zaimplementować rate limiter (np. max 100 żądań na minutę per IP) z wykorzystaniem atomowej operacji `INCR` oraz `EXPIRE`? Jakie są ograniczenia tego podejścia (fixed window) i jak wariant oparty na Sorted Set (`ZADD`/`ZRANGEBYSCORE`) realizuje sliding window rate limiter?
   3. _(Atomowość: MULTI/EXEC vs Lua)_ Czym są transakcje w Valkey (`MULTI`/`EXEC`)? Dlaczego nie mają mechanizmu rollbacku i czym różni się to zasadniczo od transakcji w SQL? Kiedy skrypt Lua wykonywany po stronie serwera jest lepszym wyborem dla operacji wymagających atomowości złożonej logiki?
5. **[1 pkt]** Przedstaw, w jaki sposób Valkey może przechowywać dane w sposób trwały.
6. **[1 pkt]** Przedstaw podobieństwa i różnice między modelami danych dokumentowym (MongoDB) oraz klucz-wartość (Valkey). W jakich scenariuszach typowej aplikacji webowej sięgnąłbyś po każdą z tych baz — czy mogą współistnieć w jednej architekturze?
