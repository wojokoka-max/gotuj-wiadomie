# Gotuj świadomie

**Inteligentny przewodnik kulinarny — nie uczymy przepisów, uczymy rozumieć kuchnię.**

Aplikacja webowa (pojedynczy plik HTML, zero zależności, zero builda) tłumacząca procesy zachodzące podczas gotowania, pieczenia, fermentacji i konserwowania żywności. Zamiast kolejnej listy przepisów — odpowiedzi na pytania *dlaczego*, *kiedy*, *po co* i *co się stanie, jeśli*, oparte na sprawdzonej chemii i fizyce kuchni.

## Zawartość

- **78 kart wiedzy** w **21 kategoriach**: pieczywo, zakwas, fermentacja, mąki, mięso, ryby, warzywa, owoce, nabiał, jaja, tłuszcze, przyprawy, sosy, desery, techniki, najczęstsze błędy, ratowanie potraw, zamienniki, bezpieczeństwo żywności, przechowywanie, konserwowanie.
- Każda karta: opis, mechanizm „dlaczego", kiedy stosować / kiedy nie, najczęstsze błędy, praktyczne wskazówki, zamienniki, powiązane zagadnienia.
- **Wyszukiwarka** po tytułach, skrótach i opisach kart.
- **Przewodnik decyzji** — wielogałęziowy kreator (zamienniki, smażenie, ciasta i desery, sosy, mąka, ratunek dla potrawy) kończący się konkretną rekomendacją z uzasadnieniem.
- **Diagnostyka problemów** — trzy zestawy objawów (pieczywo drożdżowe, ciasta i desery, mięso i smażenie) z rankingiem prawdopodobnych przyczyn.
- **Moduł eksperymentów** — interaktywne suwaki dla trzech modeli (chleb pszenny, stek wołowy, biszkopt) pokazujące na żywo skutki zmiany parametrów.
- **Ulubione i historia** — zapisywane lokalnie w przeglądarce.
- **Tryb jasny / ciemny**, pełna responsywność (mobile / desktop).

## Technologia

Czysty HTML + CSS + JavaScript (bez frameworków, bez npm, bez procesu budowania). Cała treść kart jest renderowana jako statyczny DOM przy starcie — nie wstrzykiwana dynamicznie — dla pełnej indeksowalności przez wyszukiwarki.

### SEO

- Meta: `description`, `canonical`, Open Graph, Twitter Card, `theme-color` per motyw, `robots`.
- Dwa bloki JSON-LD: `WebSite` oraz `FAQPage` (15 pytań i odpowiedzi) — kandydat do rich results w Google.
- Semantyczny HTML: jeden `H1`, hierarchia nagłówków, `<article>`, `<nav>`, skip-link, atrybuty `aria` na wyszukiwarce i przełącznikach.
- Stopka zawiera pełną mapę linków do wszystkich kart wiedzy.

## Uruchomienie lokalne

Wystarczy otworzyć `index.html` w przeglądarce — brak serwera, brak instalacji.

## Wdrożenie na Vercel

1. Rozpakuj / przygotuj folder z plikiem **`index.html`** w środku (nazwa musi być dokładnie taka — Vercel serwuje ją automatycznie jako stronę główną).
2. Na [vercel.com/new](https://vercel.com/new) przeciągnij **cały folder** (nie pojedynczy plik) w pole drag & drop, albo użyj `vercel` z CLI w katalogu projektu.
3. Deployment gotowy w kilkanaście sekund pod adresem `*.vercel.app`.

Zero zmiennych środowiskowych, zero konfiguracji builda.

## Przed publikacją produkcyjną

- Podmień `https://gotujswiadomie.pl/` w `<head>` (canonical, Open Graph) na docelową domenę.
- Rozważ dodanie `sitemap.xml` i obrazka `og:image` (1200×630) — pojedynczy plik HTML ich nie dostarczy sam.

## Ograniczenia świadomie przyjęte

- Karty dotyczące konserwowania niskokwasowego (mięso, warzywa bez kwasu) celowo nie podają konkretnych czasów/temperatur pasteryzacji ciśnieniowej — to teren wymagający oficjalnych wytycznych sanitarnych, nie encyklopedii kulinarnej.
- Brak backendu i kont użytkownika — ulubione i historia żyją wyłącznie w `localStorage` danej przeglądarki.
