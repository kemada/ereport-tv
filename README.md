# eReport.tv

Statická stránka pre Cloudflare Pages.

## Nasadenie

1. Vytvor repozitár na GitHube (napr. `ereport-tv`) a nahraj tieto súbory do koreňa.
2. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git → vyber repozitár.
3. Nastavenia buildu: Framework preset **None**, Build command prázdny, Build output directory `/`.
4. Po nasadení: Custom domains → Set up a custom domain → `ereport.tv` (a `www.ereport.tv`). DNS sa doplní automaticky, lebo doména je na Cloudflare.

Každý push do hlavnej vetvy sa nasadí automaticky.
