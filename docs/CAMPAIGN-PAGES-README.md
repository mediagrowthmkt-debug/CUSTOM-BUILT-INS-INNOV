# Campaign Pages - Custom Built-ins Landing Pages

## � Estrutura de Pastas

```
BUILD-INS/
├── meta/                          # Campanha Meta (Facebook/Instagram)
│   ├── index.html                 # Página principal
│   ├── thank-you.html             # Página de agradecimento
│   ├── projects/                  # Imagens dos projetos
│   ├── FOTOS HEADER/              # Imagens do header
│   ├── foto iago/                 # Foto do CEO
│   ├── pagina exemplo_files/      # Arquivos CSS/JS
│   └── logo innov builders.jpg    # Logo
│
├── google/                        # Campanha Google Ads
│   ├── index.html                 # Página principal
│   ├── thank-you.html             # Página de agradecimento
│   ├── projects/                  # Imagens dos projetos
│   ├── FOTOS HEADER/              # Imagens do header
│   ├── foto iago/                 # Foto do CEO
│   ├── pagina exemplo_files/      # Arquivos CSS/JS
│   └── logo innov builders.jpg    # Logo
│
├── index.html                     # Página principal original
├── meta.html                      # Backup da página Meta
├── google.html                    # Backup da página Google
└── thank-you.html                 # Página de agradecimento original
```

---

## 📄 Campanhas

### 1. **Pasta META/** - Campanha Meta (Facebook/Instagram)
- **URL sugerida**: `seudominio.com/meta/`
- **Pixel de rastreamento**: Meta Pixel (Facebook Pixel)
- **Nome da campanha**: Built-ins Landing Page - Meta Ads
- **Fonte de tráfego**: Meta Ads

#### Arquivos com Meta Pixel:
- ✅ `meta/index.html` - Página principal com Meta Pixel
- ✅ `meta/thank-you.html` - Página de agradecimento com Meta Pixel

#### Eventos rastreados:
- **index.html**: 
  - `PageView` - Quando a página carrega
  - `Lead` - Quando o formulário é enviado
- **thank-you.html**: 
  - `PageView` - Quando a página carrega
  - `Contact` - Confirmação de conversão

#### Configuração necessária:
1. Substitua `YOUR_META_PIXEL_ID` pelo seu ID do Meta Pixel nos arquivos:
   - `meta/index.html` (2 lugares)
   - `meta/thank-you.html` (2 lugares)

---

### 2. **Pasta GOOGLE/** - Campanha Google Ads
- **URL sugerida**: `seudominio.com/google/`
- **Pixels de rastreamento**: 
  - Google Tag Manager (GTM)
  - Google Analytics (GA4)
  - Google Ads Conversion Tracking
- **Nome da campanha**: Built-ins Landing Page - Google Ads
- **Fonte de tráfego**: Google Ads

#### Arquivos com Google Tracking:
- ✅ `google/index.html` - Página principal com GTM + GA4
- ✅ `google/thank-you.html` - Página de agradecimento com GTM + GA4 + Conversion

#### Eventos rastreados:
- **index.html**: 
  - `PageView` - Quando a página carrega
  - `generate_lead` - Quando o formulário é enviado
- **thank-you.html**: 
  - `PageView` - Quando a página carrega
  - `conversion` - Confirmação de conversão do Google Ads

#### Configuração necessária:
1. Substitua `GTM-XXXXXXX` pelo seu ID do Google Tag Manager nos arquivos:
   - `google/index.html` (2 lugares)
   - `google/thank-you.html` (2 lugares)

2. Substitua `G-XXXXXXXXXX` pelo seu ID do Google Analytics 4 nos arquivos:
   - `google/index.html` (2 lugares)
   - `google/thank-you.html` (2 lugares)

3. Substitua `AW-CONVERSION_ID/CONVERSION_LABEL` pelo seu ID de conversão do Google Ads em:
   - `google/thank-you.html` (1 lugar)

---

## 🔧 Webhook de Integração

Ambas as páginas enviam os dados do formulário para:
```
https://hook.us2.make.com/ctp3mh229k0mi9ujiy1xcu1xh84fpa3x
```

### Dados enviados ao webhook:

**Campos do formulário:**
- `name` - Nome do cliente
- `phone` - Telefone
- `email` - E-mail
- `budget` - Orçamento estimado
- `project` - Descrição do projeto

**Informações adicionais:**
- `campaign_url` - URL completa da página
- `page_name` - Nome da página identificando a campanha
- `campaign_name` - Nome específico da campanha
- `traffic_source` - Fonte do tráfego (Meta Ads ou Google Ads)

---

## 📊 Diferenças entre as campanhas

| Característica | meta/ | google/ |
|---------------|-------|---------|
| **Pixel Principal** | Meta Pixel | Google Tag Manager + GA4 |
| **Traffic Source** | Meta Ads | Google Ads |
| **Evento Landing Page** | PageView + Lead | PageView + generate_lead |
| **Evento Thank You** | PageView + Contact | PageView + conversion |
| **Campaign Name** | Built-ins Landing Page - Meta Ads | Built-ins Landing Page - Google Ads |

---

## 🚀 Como usar

### Opção 1: Upload Direto (Recomendado)

1. **Faça upload das pastas completas** para seu servidor:
   - Upload da pasta `meta/` → `seudominio.com/meta/`
   - Upload da pasta `google/` → `seudominio.com/google/`

2. **Configure os IDs dos pixels** nos arquivos:
   - Meta: Edite os arquivos em `meta/`
   - Google: Edite os arquivos em `google/`

3. **Use as URLs nas campanhas**:
   - Campanhas do Meta: `seudominio.com/meta/`
   - Campanhas do Google: `seudominio.com/google/`

### Opção 2: Configuração via .htaccess

Se preferir usar URLs sem a extensão .html:

```apache
# No arquivo .htaccess na raiz
RewriteEngine On

# Redirecionar /meta para /meta/index.html
RewriteRule ^meta/?$ meta/index.html [L]

# Redirecionar /google para /google/index.html
RewriteRule ^google/?$ google/index.html [L]
```

---

## ✅ Checklist de Configuração

### Meta Campaign (pasta meta/)
- [ ] Substituir `YOUR_META_PIXEL_ID` em `meta/index.html` (2x)
- [ ] Substituir `YOUR_META_PIXEL_ID` em `meta/thank-you.html` (2x)
- [ ] Fazer upload da pasta `meta/` completa
- [ ] Testar o pixel com a extensão Meta Pixel Helper
- [ ] Testar o envio do formulário
- [ ] Verificar eventos no Events Manager do Meta

### Google Campaign (pasta google/)
- [ ] Substituir `GTM-XXXXXXX` em `google/index.html` (2x)
- [ ] Substituir `GTM-XXXXXXX` em `google/thank-you.html` (2x)
- [ ] Substituir `G-XXXXXXXXXX` em `google/index.html` (2x)
- [ ] Substituir `G-XXXXXXXXXX` em `google/thank-you.html` (2x)
- [ ] Substituir `AW-CONVERSION_ID/CONVERSION_LABEL` em `google/thank-you.html` (1x)
- [ ] Fazer upload da pasta `google/` completa
- [ ] Testar o GTM com Tag Assistant
- [ ] Testar o envio do formulário
- [ ] Verificar eventos no Google Analytics e Google Ads

---

## 🧪 Testes

Antes de lançar as campanhas, teste:

### Meta Campaign
1. ✓ Acesse `seudominio.com/meta/`
2. ✓ Verifique se o Meta Pixel está carregando (use Meta Pixel Helper)
3. ✓ Preencha e envie o formulário
4. ✓ Confirme o redirecionamento para `thank-you.html`
5. ✓ Verifique os eventos no Events Manager do Meta
6. ✓ Confirme o recebimento dos dados no webhook

### Google Campaign
1. ✓ Acesse `seudominio.com/google/`
2. ✓ Verifique se o GTM está carregando (use Tag Assistant)
3. ✓ Preencha e envie o formulário
4. ✓ Confirme o redirecionamento para `thank-you.html`
5. ✓ Verifique os eventos no Google Analytics
6. ✓ Verifique as conversões no Google Ads
7. ✓ Confirme o recebimento dos dados no webhook

---

## 📝 Notas Importantes

- ✅ Cada pasta é **totalmente independente** e autocontida
- ✅ Todas as imagens e recursos necessários estão em cada pasta
- ✅ Os pixels rastreiam automaticamente as conversões
- ✅ O webhook recebe todas as informações independente da origem
- ✅ Cada campanha tem identificadores únicos para facilitar análises
- ✅ As páginas de agradecimento também têm pixels configurados
- ✅ Pronto para upload direto no servidor

---

## 🆘 Suporte

Se precisar de ajuda:
1. Verifique se todos os IDs dos pixels foram substituídos corretamente
2. Use as extensões de navegador para debug (Meta Pixel Helper, Tag Assistant)
3. Verifique o console do navegador para erros JavaScript
4. Confirme que todas as pastas de imagens foram enviadas corretamente
