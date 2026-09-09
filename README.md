# FutPontos 5

Base enxuta e genérica do **FutPontos** para grupos esportivos.

## Núcleo do MVP

- Criar e consultar grupos;
- Cadastrar atletas por grupo;
- Registrar desempenho individual;
- Ranking do ciclo mensal atual;
- Fechamento mensal com preservação do ranking;
- Interface web simples, pronta para virar PWA ou aplicativo Android.

O projeto não depende de Telegram, n8n ou vídeos para funcionar. Essas integrações podem ser adicionadas depois como módulos opcionais.

## Estrutura

```text
api/   API Node.js + PostgreSQL
web/   interface web estática do MVP
```

## Executar a API

```bash
cd api
cp .env.example .env
npm install
npm start
```

Variáveis principais:

```env
PORT=3000
DATABASE_URL=postgresql://usuario:senha@localhost:5432/futpontos
```

## API principal

```text
GET  /health
GET  /grupos
POST /grupos
GET  /grupos/:slug
GET  /grupos/:grupoId/atletas
POST /grupos/:grupoId/atletas
POST /grupos/:grupoId/desempenho
GET  /grupos/:grupoId/ranking
GET  /grupos/:grupoId/ciclos
POST /grupos/:grupoId/ciclos/fechar
```

A primeira execução cria o schema e um grupo de demonstração chamado **Sem Domínio**, sem vincular o produto a esse grupo.

## Próximas etapas

1. Adicionar autenticação;
2. Adicionar autorização por grupo;
3. Migrar o grupo atual para este modelo;
4. Adicionar armazenamento de fotos;
5. Empacotar o frontend como PWA/Android.
