# 🚀 Guia Rápido de Configuração - Campanhas Built-ins

## 📦 O que você tem

Duas pastas completamente prontas para upload:

```
✅ meta/      → Campanha Facebook/Instagram (Meta Ads)
✅ google/    → Campanha Google Ads
```

Cada pasta contém **TUDO** que você precisa:
- Landing page principal (index.html)
- Página de agradecimento (thank-you.html)
- Todas as imagens e recursos
- Pixels configurados e prontos

---

## ⚡ Configuração em 3 Passos

### Passo 1: Configure os IDs dos Pixels

#### 📘 Para a pasta META/:
Abra estes 2 arquivos e substitua `YOUR_META_PIXEL_ID`:
- `meta/index.html` (linhas 10 e 16)
- `meta/thank-you.html` (linhas 10 e 16)

**Onde encontrar o Meta Pixel ID:**
1. Acesse https://business.facebook.com/events_manager
2. Clique no seu Pixel
3. Copie o número (ex: 123456789012345)

#### 📗 Para a pasta GOOGLE/:
Abra estes 2 arquivos e substitua:
- `GTM-XXXXXXX` → seu Google Tag Manager ID
- `G-XXXXXXXXXX` → seu Google Analytics 4 ID
- `AW-CONVERSION_ID/CONVERSION_LABEL` → seu ID de conversão do Google Ads

Arquivos:
- `google/index.html` (linhas 6, 14, 18)
- `google/thank-you.html` (linhas 9, 17, 21, 25)

**Onde encontrar:**
- GTM: https://tagmanager.google.com
- GA4: https://analytics.google.com (Admin > Data Streams)
- Conversion: https://ads.google.com (Tools > Conversions)

---

### Passo 2: Faça Upload para o Servidor

Envie as pastas completas via FTP/cPanel:

```
Seu Servidor:
├── public_html/
    ├── meta/          ← Upload desta pasta inteira
    │   ├── index.html
    │   ├── thank-you.html
    │   ├── projects/
    │   ├── FOTOS HEADER/
    │   ├── foto iago/
    │   └── ...
    │
    └── google/        ← Upload desta pasta inteira
        ├── index.html
        ├── thank-you.html
        ├── projects/
        ├── FOTOS HEADER/
        ├── foto iago/
        └── ...
```

**URLs resultantes:**
- `seudominio.com/meta/` → Campanha Meta
- `seudominio.com/google/` → Campanha Google

---

### Passo 3: Teste Tudo

#### ✅ Teste Campanha Meta:
1. Acesse `seudominio.com/meta/`
2. Instale a extensão [Meta Pixel Helper](https://chrome.google.com/webstore/detail/meta-pixel-helper/fdgfkebogiimcoedlicjlajpkdmockpc)
3. Veja se o pixel está verde ✓
4. Preencha o formulário de teste
5. Verifique se foi redirecionado para thank-you.html
6. Confira os eventos em https://business.facebook.com/events_manager

#### ✅ Teste Campanha Google:
1. Acesse `seudominio.com/google/`
2. Instale a extensão [Tag Assistant](https://chrome.google.com/webstore/detail/tag-assistant-legacy-by-g/kejbdjndbnbjgmefkgdddjlbokphdefk)
3. Veja se as tags estão carregando ✓
4. Preencha o formulário de teste
5. Verifique se foi redirecionado para thank-you.html
6. Confira os eventos no Google Analytics

---

## 🎯 Use nas Campanhas

### Meta Ads (Facebook/Instagram):
```
URL da Landing Page: https://seudominio.com/meta/
```

### Google Ads:
```
URL da Landing Page: https://seudominio.com/google/
```

---

## 📊 O que Será Rastreado

### Meta Campaign:
- ✓ PageView → Quando alguém acessa a página
- ✓ Lead → Quando alguém envia o formulário
- ✓ Contact → Quando chega na página de agradecimento

### Google Campaign:
- ✓ PageView → Quando alguém acessa a página
- ✓ generate_lead → Quando alguém envia o formulário
- ✓ conversion → Quando chega na página de agradecimento

---

## 🔔 Webhook de Dados

Todos os formulários enviam dados para:
```
https://hook.us2.make.com/ctp3mh229k0mi9ujiy1xcu1xh84fpa3x
```

Você receberá:
- Nome, E-mail, Telefone
- Orçamento estimado
- Descrição do projeto
- URL da campanha
- Nome da campanha
- Fonte de tráfego (Meta Ads ou Google Ads)

---

## 🆘 Problemas Comuns

**❌ Pixel não aparece:**
- Verifique se substituiu os IDs corretamente
- Limpe o cache do navegador
- Confira se o arquivo foi salvo

**❌ Imagens não carregam:**
- Verifique se todas as pastas foram enviadas
- Confira permissões (chmod 755 nas pastas)
- Veja se os caminhos estão corretos

**❌ Formulário não envia:**
- Abra o console do navegador (F12)
- Verifique se há erros JavaScript
- Teste sua conexão com o webhook

---

## ✨ Pronto!

Suas campanhas estão configuradas e prontas para receber tráfego! 🎉

**Lembre-se:**
- Cada pasta é independente
- Você pode editar sem afetar a outra
- Os dados vão todos para o mesmo webhook
- Mas você sabe de qual campanha vieram

---

**Dúvidas?** Verifique o arquivo `CAMPAIGN-PAGES-README.md` para detalhes técnicos.
