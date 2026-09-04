# eReport.tv

Statická stránka pre Cloudflare Pages.

## Nasadenie

1. Vytvor repozitár na GitHube (napr. `ereport-tv`) a nahraj tieto súbory do koreňa.
2. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git → vyber repozitár.
3. Nastavenia buildu: Framework preset **None**, Build command prázdny, Build output directory `/`.
4. Po nasadení: Custom domains → Set up a custom domain → `ereport.tv` (a `www.ereport.tv`). DNS sa doplní automaticky, lebo doména je na Cloudflare.

Každý push do hlavnej vetvy sa nasadí automaticky.

## Najnovšie videá z YouTube

Stránka vie zobraziť posledných 6 videí z playlistu Bez cenzúry ako karty s náhľadmi. Potrebuje na to YouTube API kľúč (zadarmo):

1. Otvor https://console.cloud.google.com, vytvor projekt.
2. APIs & Services → Library → zapni **YouTube Data API v3**.
3. APIs & Services → Credentials → Create credentials → **API key**.
4. Pri kľúči nastav *Application restrictions* → Websites → pridaj `https://ereport.tv/*` a `https://www.ereport.tv/*`, a *API restrictions* → iba YouTube Data API v3.
5. Kľúč vlož do `index.html` do riadku `const YT_API_KEY = '';`.

Kým kľúč nie je vložený, zobrazí sa vložený YouTube playlist (funguje bez kľúča).

## Google AdSense

Overovací meta tag aj skript sú v `<head>` v `index.html`. Reklamné jednotky pridaj tam, kde ich chceš mať (napr. pod sekciu Videá) podľa kódu z AdSense.
