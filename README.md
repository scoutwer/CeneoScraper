# CeneoScraper

## kod produktu do testów 
84514582

## Algorytm pobierania opinii o produkcie z serwiu Ceneo
1. Wysłanie żądania dostępu do strony internetowej z opiniami o produkcie 
2. Jeżeli operacja zakończy się powodzeniem, wyądrębnienie z kodu strony opinii o produkcie 
3. Dla każdej opinii wyoądrebnienie z kodu html poszczególnych składowych i przypisanie ich do elementów złożonej struktury danych 
4. Jeśli istnieje kolejna strona z opiniami, przejście do niej i powtórzenie dla niej kroków 1-4
5. Zapisanie wyników do bazy danych 

## Struktura opini w serwisie Ceneo.pl

|składowa|zmienna|selektor|
|--------|-------|--------|
|opinia|review|div.js_product-review|
|identyfikator opinii|review_id|["data-entry-id"]|
|autora|author|span.user-post__author-name|
|rekomendację|recommendation|span.user-post__author-recomendation > em|
|liczbę gwiazdek|stars|span.user-post__score-count|
|treść opinii|content|div.user-post__text|
|listę zalet|prons|div.review-feature__item review-feature__item--positive|
|listę wad|cons|div.review-feature__item review-feature__item--negative|
|ile osób uznało opinię za przydatną|usefull|button.vote-yes > span|
|ile osób uznało opinię za nieprzydatną|useless|button.vote-no > span|
|data wystawienia opinii|post_date|span.user-post__published > time:sth-child(1)['datetime']|
|data zakupu produktu|purchase_date|span.user-post__published > time:sth-child(2)['datetime']|


