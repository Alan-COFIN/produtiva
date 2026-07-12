# Changelog

Todas as mudanças relevantes deste projeto são documentadas aqui.
Formato baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/).

## [0.1.0] - Sprint 0 e Sprint 1

### Adicionado
- Setup do projeto com React, Vite, TypeScript, Tailwind CSS v4, ESLint e Prettier.
- Arquitetura modular de pastas (`app`, `components`, `layouts`, `pages`, `hooks`,
  `services`, `storage`, `store`, `types`, `utils`, `styles`).
- Sistema de tema claro/escuro persistido em LocalStorage.
- Layout principal com Sidebar e Navbar.
- Dashboard com cartões de indicadores (horas do mês, meta, pendências,
  atividades), gráfico de horas dos últimos 6 meses, últimas atividades e
  ações rápidas.
- CRUD completo do módulo de Atividades: criação, edição, exclusão (com
  confirmação), busca por título, filtro por categoria e status.
- Persistência das atividades em LocalStorage via camada de serviço isolada.
- Páginas de placeholder para Plano de Trabalho, Indicadores, Relatórios e
  Configurações (com seleção de tema).
- Workflow de deploy automático para GitHub Pages via GitHub Actions.
