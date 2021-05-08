# CeneoScraper
## Etap 1 - Pobranie składowych pojedyńczej opinii o konkretnym produkcie z serwisu [Ceneo.pl](https://www.ceneo.pl)
1. Pobranie kodu pojedyńczej strony z opiniami o produkcie
2. Analiza struktury kodu pojedynczej opinii

|Składowa|Selektor CSS|Nazwa zmiennej|Typ danych|
|:-------||:----------|:-------------|:---------|
|Opinia|div.js_product-review|opinion|obiekt bs4.e[lement.Tag|
|Identyfikator opinii|["data-entry-id"]|opinion_id|str|]
|Autor opinii|span.user-post__author-name|author|str|
|Rekomendacja|span.user-post__author-recomendation > em|recommendation|bool|
|Liczba gwiazdek|span.user-post__score-count|stars|float|
|Treść opinii|div.user-post__text|content|str|
|Lista zalet|div.review-feature__col:has(> div[class*="positives"]) > div.review-feature__item|pros|list|
|Lista wad|div.review-feature__col:has(> div[class*="negatives"]) > div.review-feature__item|cons|list|
|Dla ilu osób przydatna|span[id^="votes-yes"]|useful|int|
|Dla ilu osób nieprzydatna|span[id^="votes-no"]|useless|int|
|Czy potwierdzona zakupem|div.review-pz|purchased|bool|
|Data wystawienia opinii|span.user-post__published > time:nth-child(1)["datetime"]|submit_date|str|
|Data zakupu produktu|span.user-post__published > time:nth-child(2)["datetime"]|purchase_date|str|