# Estrutura Padronizada do Projeto ✅

Este repositório foi completamente organizado e padronizado para facilitar manutenção e escalabilidade.

## 📁 Estrutura Final

```
BUILD-INS/
├── index.html                    # Índice principal com links para todas as campanhas
├── assets/                       # Todos os ativos centralizados
│   ├── images/
│   │   ├── header/              # Imagens do header/hero
│   │   ├── ceo/                 # Foto do CEO/fundador
│   │   ├── projects/            # Projetos before/after
│   │   ├── fotos-extras/        # Imagens extras/backup
│   │   └── logo innov builders.jpg
│   ├── css/                     # CSS customizados (futuro)
│   └── js/                      # JavaScript customizados (futuro)
├── pages/                       # Landing pages principais
│   ├── index.html              # Página principal (MS Clarity)
│   ├── thank-you.html          # Página de agradecimento
│   └── test-form.html          # Teste de formulário
├── google/                      # Variação Google Ads
│   ├── index.html              # GTM + Clarity
│   └── thank-you.html
├── meta/                        # Variação Meta Ads
│   ├── index.html              # Facebook Pixel
│   └── thank-you.html
├── docs/                        # Documentação
│   ├── STRUCTURE-OVERVIEW.md   # Este arquivo
│   ├── SETUP-GUIDE.md
│   ├── CAMPAIGN-PAGES-README.md
│   ├── LAUNCH-CHECKLIST.md
│   └── ...
├── archive/                     # Arquivos arquivados
│   └── exports/                # Páginas exportadas antigas
├── marketing/                   # Criativos e anúncios
│   └── ANÚNCIOS/
└── portfolio/                   # Portfolio raw/exemplos
    └── raw/

```

## ✅ Melhorias Aplicadas

1. **Assets Centralizados**: Todos os ativos (imagens, logo, projetos) agora estão em `assets/`
2. **Deduplicação**: Removidas pastas duplicadas de `google/` e `meta/` - agora referenciam `../assets/`
3. **Páginas Organizadas**: HTMLs principais movidos para `pages/`
4. **Index de Navegação**: Novo `index.html` no root para acesso rápido a todas as variações
5. **Paths Atualizados**: Todos os caminhos nos HTMLs foram atualizados automaticamente
6. **Git Versionado**: Todas as mudanças comitadas com mensagens descritivas

## 🔗 Referências de Paths

Todas as páginas agora usam caminhos relativos padronizados:

- **Root index** → `assets/images/...`
- **pages/** → `../assets/images/...`
- **google/** → `../assets/images/...`
- **meta/** → `../assets/images/...`

## 🚀 Como Adicionar Novos Ativos

1. **Imagens de Header**: `assets/images/header/`
2. **Projetos Before/After**: `assets/images/projects/Nome-do-Projeto/`
3. **Logo**: `assets/images/`
4. **CSS**: `assets/css/`
5. **JavaScript**: `assets/js/`

## 📊 Benefícios

- ✅ Sem duplicação de arquivos
- ✅ Manutenção mais fácil (um único local para atualizar assets)
- ✅ Estrutura escalável
- ✅ Paths consistentes
- ✅ Melhor organização para trabalho em equipe
- ✅ Commits Git organizados e rastreáveis
