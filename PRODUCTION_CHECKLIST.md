# Production Checklist — junmilan-portfolio

## Před nasazením

### Kód a obsah
- [x] HTML validní (W3C validator)
- [x] Responzivní design (mobil, tablet, desktop)
- [x] Kontaktní email aktuální (`jun.milan@outlook.com`)
- [x] Všechny odkazy funkční
- [x] Texty bez překlepů

### Výkon
- [x] Fonty načítány přes `display=swap`
- [x] Obrázky optimalizované (formát, velikost)
- [x] Žádný nepoužitý CSS/JS
- [ ] Lighthouse skóre > 90 (Performance, Accessibility, Best Practices, SEO)

### Bezpečnost
- [x] Security headers v `vercel.json` (CSP, HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
- [x] HTTPS vynuceno (Vercel default + HSTS)
- [x] `frame-ancestors 'none'` — ochrana proti clickjacking
- [x] `form-action 'none'` — žádné formuláře k ochraně

### SEO
- [x] `<title>` tag s popisným názvem
- [x] `<meta name="viewport">` pro mobilní zařízení
- [x] `<html lang="cs">` pro správný jazyk
- [ ] `<meta name="description">` tag
- [ ] `robots.txt`
- [ ] `sitemap.xml`
- [ ] Open Graph tagy (`og:title`, `og:description`, `og:image`)

### Deployment
- [x] Git repo na GitHubu
- [x] Vercel napojený na repo
- [x] Auto-deploy z `master` větve
- [ ] Vlastní doména nastavená
- [ ] SSL certifikát aktivní (automaticky po doméně)

### Monitoring
- [ ] Vercel Analytics zapnutý
- [ ] Vercel Speed Insights zapnutý
