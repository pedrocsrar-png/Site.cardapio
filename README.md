# Churrascaria e Pizzaria Avenida — site com banco de dados

Sem dependências: precisa só de **Node 22.5+** (banco SQLite embutido).

## Rodar
    ADMIN_PASSWORD="sua-senha-forte" npm start
Site: http://localhost:3000 · Painel: http://localhost:3000/admin

## Variáveis
- ADMIN_PASSWORD (obrigatória para o painel) · PORT · PUBLIC_URL (ex.: https://seudominio.com.br, usado no /sitemap.xml) · REVIEW_MODE=auto|moderate · TRUST_PROXY=1 (atrás de Nginx/Render/Railway) · INSECURE_COOKIE=1 (só em teste local sem HTTPS)

## Publicar (precisa de HTTPS e disco persistente)
Render, Railway, Fly.io ou VPS: comando `npm start`, e monte um volume em `data/` (banco) e `public/uploads/` (fotos). Sem volume, os dados somem a cada deploy. Faça backup periódico da pasta `data/`.

## Dia a dia
- /admin → Cardápio: criar/editar prato, preço, disponibilidade, foto, arquivar.
- /admin → Avaliações: aprovar, ocultar, rejeitar; as denunciadas aparecem primeiro.
- /admin → Contato: WhatsApp, telefones, endereço, horário e links do Google (o botão "Avaliar no Google" só aparece se o link for preenchido).
