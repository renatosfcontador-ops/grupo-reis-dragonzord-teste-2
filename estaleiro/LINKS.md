# Links oficiais — DragonZord Teste 2

## Showroom público (estático)

- **URL:** https://renatosfcontador-ops.github.io/grupo-reis-dragonzord-teste-2/
- **Tipo:** GitHub Pages (build estático)
- **Status:** online (HTTP 200, verificado em 15/11/2026)
- **Repositório:** https://github.com/renatosfcontador-ops/grupo-reis-dragonzord-teste-2
- **Deploy:** `.github/workflows/deploy-pages.yml` (push em `main`)

## Backend / túnel

- **Não exposto.** Nenhum túnel público (Cloudflare/ngrok) foi criado para o backend local.
- Motivo: expor o back-end/Motor de IA publicamente com senha fraca (`Admin@123`) é risco crítico.
- Para expor com segurança: usar Cloudflare Tunnel + Cloudflare Access (ou segredo forte) e confirmar o escopo.

## Validação local

- `server.js` OK
- `assets/app.js` OK
- `projects.json` OK (JSON válido)