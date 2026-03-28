# Deployment Guide — junmilan-portfolio

## Hosting

- **Platforma:** [Vercel](https://vercel.com)
- **Repo:** [github.com/junmilan/junmilan-portfolio](https://github.com/junmilan/junmilan-portfolio)
- **Auto-deploy:** Každý push do `master` se automaticky nasadí na produkci.

## Jak nasadit změny

1. Uprav soubory lokálně
2. Commitni a pushni do `master`:
   ```bash
   git add .
   git commit -m "popis změny"
   git push
   ```
3. Vercel automaticky detekuje push a nasadí novou verzi (~10s)
4. Zkontroluj stav na [vercel.com/dashboard](https://vercel.com/dashboard)

## Preview deploymenty

Každý pull request automaticky dostane vlastní preview URL (např. `junmilan-portfolio-xyz.vercel.app`). Díky tomu si můžeš změny ověřit před mergem do `master`.

## Rollback

Pokud je potřeba vrátit předchozí verzi:

1. Jdi na Vercel dashboard → projekt → **Deployments**
2. Najdi poslední funkční deployment
3. Klikni na **⋯** → **Promote to Production**

Alternativně přes CLI:
```bash
npx vercel rollback
```

## Vlastní doména

### Přidání domény na Vercelu

1. Vercel dashboard → projekt → **Settings** → **Domains**
2. Zadej doménu (např. `junmilan.cz`)
3. Vercel ti ukáže DNS záznamy, které je potřeba nastavit

### DNS nastavení u registrátora

Přidej tyto záznamy u svého registrátora (např. Wedos):

| Typ   | Název | Hodnota              |
|-------|-------|----------------------|
| A     | @     | `76.76.21.21`        |
| CNAME | www   | `cname.vercel-dns.com` |

> DNS propagace může trvat až 48 hodin, obvykle do 1 hodiny.

### SSL

Vercel automaticky vystaví a obnoví SSL certifikát (Let's Encrypt) po ověření DNS.

## Konfigurace

- `vercel.json` — security headers, clean URLs, trailing slash
- `.gitignore` — vyloučené soubory z gitu

## Užitečné příkazy

```bash
npx vercel             # manuální deploy
npx vercel --prod      # deploy do produkce
npx vercel env ls      # výpis environment variables
npx vercel logs        # zobrazení logů
npx vercel rollback    # návrat na předchozí verzi
```
