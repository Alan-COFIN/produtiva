# Produtiva

Plataforma de produtividade modular, construída para organizar o trabalho da
Coordenação de Execução Financeira (COFIN/IFAC). O módulo inicial é o **PGD**
(Programa de Gestão e Desempenho); a arquitetura foi pensada para receber, no
futuro, módulos de Financeiro, Contratos, Tributos, REINF, Processos e Agenda
sem retrabalho.

## Stack

- React 19 + TypeScript
- Vite
- Tailwind CSS v4
- React Router
- Zustand (estado global)
- React Hook Form + Zod (formulários e validação)
- Recharts (gráficos)
- Heroicons

## Arquitetura

```
src/
  app/          # bootstrap da aplicação e rotas
  assets/       # imagens, ícones estáticos
  components/   # componentes de UI reutilizáveis (Button, Card, Modal...)
  layouts/      # Sidebar, Navbar, MainLayout
  pages/        # uma pasta por módulo/tela (Dashboard, Activities, Reports, Settings...)
  hooks/        # hooks customizados
  services/     # regras de acesso a dados (hoje: LocalStorage)
  storage/      # driver de persistência (isolado para trocar por API no futuro)
  store/        # stores Zustand (estado global)
  types/        # tipos e contratos TypeScript
  utils/        # funções auxiliares puras
  styles/       # estilos globais e tokens de tema
```

A camada `services` nunca é acessada diretamente pelas telas — apenas pelas
`stores`. Isso mantém a UI desacoplada da forma como os dados são persistidos:
trocar LocalStorage por uma API no futuro exigirá mudanças apenas em
`services/` e `storage/`.

## Como rodar

```bash
npm install
npm run dev       # ambiente de desenvolvimento
npm run build     # build de produção
npm run preview   # servir o build localmente
npm run lint      # checagem de lint
npm run format    # formatação com Prettier
```

## Deploy (GitHub Pages)

O deploy é automático via GitHub Actions (`.github/workflows/deploy.yml`):
a cada push na branch `main`, o projeto é buildado e publicado em
GitHub Pages. Também é possível publicar manualmente com:

```bash
npm run deploy
```

## Status

Módulo **PGD** com Dashboard e CRUD completo de Atividades implementados.
Veja o [ROADMAP.md](./ROADMAP.md) para os próximos módulos e o
[CHANGELOG.md](./CHANGELOG.md) para o histórico de versões.
