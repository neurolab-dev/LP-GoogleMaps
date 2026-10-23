# NeuroLab — Landing Google Maps

Projeto independente da landing de posicionamento e qualificação de empresas
no Google Maps. Inclui a identidade do BrandOS, ilustrações, comparação de
perfis, roleta de etapas e contato pelo WhatsApp (38) 99181-0452.

## Rodar localmente

Use Node.js 22 ou posterior:

```powershell
npm ci
npm run dev
```

A landing é a página inicial do projeto: `/`.

## Subir no GitHub e publicar

1. Crie um repositório e envie o conteúdo desta pasta, preservando a estrutura.
2. Não envie `node_modules`, `dist`, `.astro` nem arquivos `.env` reais.
3. Importe o repositório na Vercel como projeto Astro.
4. Configure `SITE_URL` com a URL pública definitiva, sem caminho final.
5. Use `SITE_BASE=/`. Build: `npm run build`. Saída: `dist`.

`vercel.json` já contém a configuração de build. O domínio padrão em
`astro.config.mjs` é o institucional; configure `SITE_URL` antes de publicar
para que canonical, sitemap e metadados apontem para a landing independente.

## Arquivos principais

- `src/pages/index.astro`: página e interações.
- `src/data/google-maps.ts`: textos e etapas.
- `src/data/contato.ts`: telefone e contatos.
- `src/styles/google-maps.css`: visual da landing.
- `src/styles/maps-process.css`: roleta de etapas.
- `src/layouts/Base.astro`: metadados e estrutura compartilhada copiada.
- `src/tokens` e `src/assets/marca`: tokens e imagens oficiais do BrandOS.

Os arquivos compartilhados foram copiados para que o projeto seja independente.
Não há dependência de caminhos do site institucional nem scripts de sincronização
externos. Nenhuma senha, configuração `.env` real ou histórico Git foi incluído.

## Verificação

```powershell
npm run lint
npm run build
```

O sitemap é gerado no build. A medição de contatos usa o GA4 quando configurado
e autorizado pelo visitante; as respostas do formulário vão apenas na mensagem
preparada para o WhatsApp.
