# Cache models using Valkey

Caching to jedna z najskuteczniejszych technik optymalizacji wydajności w systemach webowych — właściwie zastosowany Valkey jako warstwa cache potrafi zredukować latencję odpowiedzi o rzędy wielkości i odciążyć bazę danych od dziesiątek tysięcy zapytań na sekundę. Jednak cache źle zaprojektowany lub źle skonfigurowany staje się źródłem trudnych do zdiagnozowania błędów i awarii produkcyjnych. Lab ten skupia się na strategiach i modelach, które decydują o tym, czy cache jest zasobem, czy pułapką.

1. **[3 pkt]** Na czym polega cachowanie danych w aplikacjach? W jakim celu stosuje się caching? Wymień zalety i wady tego rozwiązania. Omów następujące zagrożenia operacyjne, które są rzeczywistymi przyczynami awarii produkcyjnych w systemach opartych na cache:
   1. _(Cache stampede / thundering herd)_ Co się dzieje, gdy popularny klucz wygasa i wiele żądań jednocześnie trafia bezpośrednio do bazy danych, zanim cache zostanie ponownie uzupełniony? Opisz trzy sposoby zapobiegania temu zjawisku: mutex lock, probabilistic early expiration (PER) oraz background refresh. Kiedy każde z nich jest właściwym wyborem?
   2. _(Cache penetration)_ Na czym polega wzorzec cache penetration i dlaczego może być wykorzystany jako wektor ataku? Jak cachowanie pustych odpowiedzi lub zastosowanie Bloom filtra może temu zapobiec?
   3. _(Cache avalanche)_ Czym różni się cache avalanche od cache stampede? Jak rozłożenie TTL w czasie (TTL jitter) oraz mechanizm circuit breaker mogą ograniczyć ryzyko kaskadowej awarii?
2. **[2 pkt]** Czym są strategie eksmisji danych z cache? W jaki sposób można je wykorzystać? Przedstaw przykłady 6 różnych strategii, w tym Least Recently Used (LRU) oraz Least Frequently Used (LFU). Dla każdej wskaż odpowiadającą jej wartość parametru `maxmemory-policy` w konfiguracji Valkey i omów, w jakim scenariuszu produkcyjnym daną politykę należy ustawić.
3. **[3 pkt]** Modele cache w aplikacjach. Omów modele: Cache-aside, Read-through, Write-through, Write-around oraz Write-back. Przedstaw ich zalety, wady oraz przypadki zastosowania.
4. **[2 pkt]** Modele cache — implementacja. Zaprezentuj możliwą implementację modeli omówionych w zadaniu 3, wykorzystując Valkey oraz inną dowolną bazę, np. MongoDB. Wystarczy szkielet kodu lub pseudokod z komentarzem opisującym kluczowe decyzje implementacyjne — nie jest wymagana pełna aplikacja.

Jako rozszerzenie tematu polecam zapoznać się z artykułem o [Sieve](https://junchengyang.com/publication/nsdi24-SIEVE.pdf).
