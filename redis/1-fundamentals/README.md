# Redis fundamentals

1. **[2 pkt]** Czym są klucze w Redisie? Jaka jest ich rola w bazie? Jaki jest ich czas życia i od czego on zależy? Jakie są dobre praktyki przy tworzeniu nazw kluczy? Omów na przykładach w trakcie realizacji kolejnych zadań.
2. **[4 pkt]** Przedstaw [typy danych](https://redis.com/glossary/redis-data-structures/) dostępnych w Redisie. Omów, w jaki sposób są zaimplementowane, jak można je wykorzystać oraz przedstaw typowe usecasy. Uwzględnij następujące:
   1. Przedstaw, w jaki sposób reprezentowane są wartości numeryczne w Redisie.
   2. Zaprezentuj działanie i wykorzystanie funkcji dostępnych poprzez redis-cli do obsługi omówionych w poprzednim punkcie typów danych.
   3. Opisz funkcje, pozwalające na pracę ze zmiennymi liczbowymi.
   4. Jak zrealizować w Redisie implementację kolejki oraz stosu?
3. **[2 pkt]** Stwórz CRUDy, wykorzystujące każdy z wymienionych w zadaniu 2. W tym celu możesz wykorzystać kolekcje z sample datasetu, używanych na lab1-4 z zakresu MongoDB.
4. **[1 pkt]** Przedstaw, w jaki sposób Redis może przechowywać dane w sposób trwały.
5. **[1 pkt]** Przedstaw podobieństwa i różnice między modelami danych dokumentowym (MongoDB) oraz klucz-wartość (Redis).
