# Naturé Cosmetics — Sistema de Gestão de Revendas & CRM

Aplicação web desenvolvida para otimizar a gestão comercial, o controle de estoque, o acompanhamento de pedidos e a fidelização de clientes no segmento de revenda de cosméticos.

---

## Links do Projeto e Infraestrutura

* **Aplicação em Produção (Vercel):** https://apex6-nature-cosmetics.vercel.app/
* **Projeto Supabase (Dashboard):** https://supabase.com/dashboard/project/oqofdwlnxfxtwpppihbz *(substitua pelo ID do seu projeto)*
* **API Endpoint (Supabase URL):**  https://oqofdwlnxfxtwpppihbz.supabase.co
* **Repositório Principal (Base):** https://github.com/keyllacristine/apex6-nature
* **Repositório de Deploy (Fork):** https://github.com/LuisSantana625/apex6-nature-cosmetics
* **Vídeo apresentação da aplicação:** https://drive.google.com/file/d/18_dLT93I7USJ83gfdG2FyvLK1LLDesM1/view?usp=drive_link

---

## Sobre o Projeto e Objetivos

O **Naturé Cosmetics** nasceu da necessidade de substituir controles manuais e planilhas dispersas por uma plataforma centralizada, intuitiva e segura para revendedoras.

### Objetivos Principais
* **Centralização Operacional:** Reunir cadastros de clientes, catálogo de produtos e histórico de vendas em um único painel.
* **Gestão de Recompras (CRM):** Facilitar a identificação de ciclos de consumo para abordagem ativa de clientes e aumento de recorrência.
* **Segurança e Isolamento de Dados:** Garantir que cada operador acesse exclusivamente sua própria carteira de clientes e pedidos por meio de autenticação e políticas de segurança em nível de linha (RLS).
* **Disponibilidade em Nuvem:** Operar com arquitetura moderna, responsiva e hospedada em nuvem para acesso via desktop ou dispositivos móveis.

---

## Funcionalidades do Sistema

* **Autenticação Segura:** Login com e-mail e senha integrado ao Supabase Auth.
* **Dashboard Analítico:** Visão consolidada de indicadores de vendas, clientes ativos e movimentações recentes.
* **Gestão de Clientes (`customers`):** Cadastro completo, consulta e atualização de dados de contato e histórico de compras.
* **Catálogo de Produtos (`products`):** Controle de itens, preços e disponibilidade para venda.
* **Controle de Pedidos (`orders` e `order_items`):** Registro de vendas vinculadas aos clientes e detalhamento dos itens adquiridos.
* **Acompanhamento de Recompras:** Monitoramento inteligente para incentivar novas vendas recorrentes.

---

## Tecnologias Utilizadas

### Frontend
* **React + TypeScript:** Construção de interfaces reativas com tipagem estática.
* **Vite:** Empacotador (bundler) de alta performance para desenvolvimento e build de produção.
* **Tailwind CSS & Componentes UI (shadcn/ui):** Estilização responsiva, acessível e padronizada.
* **TanStack Router / React Router:** Gerenciamento de rotas client-side (SPA).
* **Vitest:** Framework para testes unitários e de integração.

### Backend, Banco de Dados & Infraestrutura
* **Supabase (PostgreSQL):** Banco de dados relacional hospedado em nuvem.
* **Supabase Auth:** Gerenciamento de usuários, sessões e redirecionamentos seguros.
* **Row Level Security (RLS):** Regras de autorização diretamente no banco de dados vinculadas ao `user_id`.
* **Drizzle ORM (`drizzle.config.ts`):** Mapeamento e configuração de schema relacional.
* **GitHub:** Controle de versão distribuído e colaboração via fork e pull requests.
* **Vercel:** Hospedagem, CI/CD automático a cada commit e configuração de roteamento SPA (`vercel.json`).

---

## Estrutura do Projeto

```text
apex6-nature-cosmetics/
├── public/                 # Arquivos estáticos e assets públicos (logo, ícones, etc.)
├── src/                    # Código-fonte principal da aplicação React + TypeScript
│   ├── components/         # Componentes reutilizáveis de interface
│   ├── pages/              # Telas e módulos (Login, Dashboard, Clientes, Produtos, Pedidos)
│   ├── hooks/              # Hooks customizados e regras de estado
│   ├── integrations/       # Cliente e tipagens de conexão com o Supabase
│   └── lib/                # Utilitários e funções auxiliares
├── supabase/               # Scripts SQL de migração, schema e políticas RLS
├── AGENTS.md               # Diretrizes e contexto para agentes de IA
├── README.md               # Documentação principal e Prompt Log do projeto
├── roadmap.md              # Planejamento e evolução de funcionalidades
├── components.json         # Configuração de componentes UI (shadcn/ui)
├── drizzle.config.ts       # Configuração do Drizzle ORM
├── index.html              # Ponto de entrada HTML da aplicação
├── package.json            # Dependências e scripts do projeto
├── tsconfig.json           # Configurações do compilador TypeScript
├── vercel.json             # Configuração de rewrites para rotas SPA na Vercel
├── vite.config.ts          # Configurações de build do Vite
└── vitest.config.ts        # Configurações de testes automatizados (Vitest)
```

---

## Como Executar Localmente

### Pré-requisitos
* **Node.js** (versão 18 ou superior)
* **npm** ou **bun** (gerenciadores de pacotes suportados pelo repositório)
* Conta e projeto configurados no **Supabase**

### Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/LuisSantana625/apex6-nature-cosmetics.git
   cd apex6-nature-cosmetics
   ```

2. **Instale as dependências:**
   ```bash
   npm install
   ```

3. **Configure as variáveis de ambiente:**
   Crie ou ajuste o arquivo `.env` na raiz do projeto com as credenciais públicas do seu projeto Supabase:
   ```env
   VITE_SUPABASE_URL=https://<project-ref>.supabase.co
   VITE_SUPABASE_PUBLISHABLE_KEY=<sua-publishable-key>
   ```

4. **Inicie o servidor de desenvolvimento:**
   ```bash
   npm run dev
   ```

5. Acesse `http://localhost:5173` (ou a porta exibida no terminal).

---

## Documentação do Uso de Inteligência Artificial

O desenvolvimento deste projeto utilizou ferramentas de Inteligência Artificial de forma estruturada e supervisionada ao longo de todo o ciclo de vida do software:

1. **Prototipação Rápida e Geração de Interface (Lovable Cloud):**
   * Utilizada para traduzir os requisitos de negócio da **Naturé Cosmetics** em um MVP funcional com React, TypeScript e Tailwind CSS, acelerando a criação dos fluxos de CRUD e layout responsivo.
2. **Engenharia de Deploy, Migração e Troubleshooting (Assistente IA / Gemini):**
   * Utilizada como copiloto técnico para diagnosticar bloqueios de permissão de repositório (estratégia de *fork*), configurar o roteamento SPA na Vercel (`vercel.json`), estruturar a migração de banco de dados entre ambientes, corrigir variáveis de ambiente (`VITE_SUPABASE_URL`) e elaborar consultas SQL para reatribuição de integridade referencial (`user_id`).
3. **Validação Humana e Governança:**
   * Todas as sugestões, scripts SQL e configurações de segurança geradas por IA passaram por revisão técnica, testes ponta a ponta e auditoria de privacidade pela equipe antes da consolidação em produção.

---

## Equipe e Responsabilidades

| Integrante | Função | Principais Entregas |
| :--- | :--- | :--- |
| **Luis Felipe** | Tech Lead & Product Owner (PO) | Fork e versionamento no GitHub, deploy na Vercel, configuração do `vercel.json`, provisionamento e migração do Supabase, variáveis de ambiente e sincronização do repositório |
| **Keylla Cristine** | UX/UI Designer & AI Builder | Geração inicial do MVP no Lovable Cloud, design da interface, estruturação do repositório base e evolução visual do sistema |
| **Samira Borges** | QA & Privacidade | Validação de autenticação e URLs de redirecionamento, revisão de privacidade/RLS e vínculo de dados por usuário, testes funcionais (CRUD) e checagem de rotas |

---

## Prompt Log por Integrante

### 1. Luis Felipe — Tech Lead & Product Owner (PO)

1. **Gestão de Repositório e Fork**
   * **Contexto / Prompt:** Resolução de bloqueio de permissão ao tentar publicar pela Vercel apontando para o repositório original (`keyllacristine/apex6-nature`), seguido da criação do fork `LuisSantana625/apex6-nature-cosmetics` na branch `main`.
   * **Resultado:** Repositório acessível na conta própria com histórico e arquivos sincronizados na `main`.

2. **Deploy do Zero na Vercel**
   * **Contexto / Prompt:** Criação de novo projeto na Vercel a partir do fork com preset **Vite**.
   * **Resultado:** Pipeline de build configurado e primeiro deploy publicado no domínio `.vercel.app`.

3. **Suporte a Rotas SPA (`vercel.json`)**
   * **Contexto / Prompt:** Prevenção de erro `404` ao atualizar (`F5`) rotas internas gerenciadas pelo roteador client-side.
   * **Resultado:** Arquivo `vercel.json` adicionado na raiz redirecionando rotas para `/index.html`.

4. **Provisionamento do Supabase e Schema**
   * **Contexto / Prompt:** Criação de projeto próprio no Supabase, coleta da **Project URL** e **Publishable Key** e execução dos 3 arquivos `.sql` no **SQL Editor**.
   * **Resultado:** Estrutura de tabelas e políticas recriada no novo banco PostgreSQL.

5. **Configuração de Variáveis na Vercel**
   * **Contexto / Prompt:** Ajuste das variáveis `VITE_SUPABASE_URL` e `VITE_SUPABASE_PUBLISHABLE_KEY` no modo **Config** para os ambientes **Production** e **Preview**, corrigindo o erro `Invalid path specified in request URL` após garantir a URL raiz `.supabase.co`.
   * **Resultado:** Build recompilado com sucesso apontando para a nova instância do Supabase.

6. **Migração e Vínculo de Dados (`user_id`)**
   * **Contexto / Prompt:** Consulta ao `information_schema.columns` e execução de comandos `UPDATE` nas tabelas `customers`, `orders`, `products` e `order_items` para associar os registros importados ao `User UID` criado no novo Supabase.
   * **Resultado:** Dados históricos visíveis e operacionais no painel da aplicação.

7. **Governança entre Fork e Repositório Principal**
   * **Contexto / Prompt:** Definição do fluxo de **Pull Request** (`LuisSantana625/apex6-nature-cosmetics` -> `keyllacristine/apex6-nature`) e decisão de manter o deploy ativo a partir do fork para autonomia operacional.
   * **Resultado:** Fluxo de colaboração documentado sem risco ao ambiente de produção.

---

### 2. Keylla Cristine — UX/UI Designer & AI Builder

1. **Prototipação e Geração do MVP**
   * **Contexto / Prompt:** Construção do sistema de gerenciamento de revendas de cosméticos no Lovable Cloud e porte do projeto para React + Vite.
   * **Resultado:** Módulos de autenticação, clientes, produtos, pedidos e acompanhamento de recompras estruturados.

2. **Refinamento Visual e UX/UI**
   * **Contexto / Prompt:** Atualizações de layout, identidade visual (*"Atualiza projeto Nature Cosmetics com novo design"*) e ajustes de exibição de logo.
   * **Resultado:** Interface padronizada e navegação intuitiva entre as áreas operacionais.

3. **Organização do Código Fonte**
   * **Contexto / Prompt:** Manutenção do repositório base com as pastas `src/`, `public/`, `supabase/` e arquivos de configuração (`drizzle.config.ts`, `components.json`, `roadmap.md`, `AGENTS.md`).
   * **Resultado:** Base de código versionada e compartilhada com a equipe.

---

### 3. Samira Borges — QA & Privacidade

1. **Validação de Autenticação e Sessão**
   * **Contexto / Prompt:** Verificação de criação de usuário em **Authentication -> Users**, confirmação de credenciais e configuração de **Site URL** / **Redirect URLs** no Supabase.
   * **Resultado:** Login funcional no ambiente publicado na Vercel.

2. **Privacidade, Isolamento e RLS**
   * **Contexto / Prompt:** Conferência de políticas de segurança (**RLS**) e associação da coluna `user_id` aos registros de `customers`, `orders`, `products` e `order_items`.
   * **Resultado:** Dados isolados por usuário autenticado sem exposição indevida.

3. **Segurança de Credenciais**
   * **Contexto / Prompt:** Separação entre chave pública (`sb_publishable_...` em `VITE_SUPABASE_PUBLISHABLE_KEY`) e chave secreta (`Secret key`).
   * **Resultado:** Nenhuma chave privilegiada de backend exposta no código cliente.

4. **Testes Funcionais e de Regressão (QA)**
   * **Contexto / Prompt:** Conferência de leitura dos dados migrados, testes de criação/edição/exclusão (CRUD) e atualização de página (`F5`) em rotas internas.
   * **Resultado:** Fluxos principais validados após a migração de banco e deploy.

---

## Variáveis de Ambiente Necessárias (Vercel)

| Variável | Descrição | Exemplo |
| :--- | :--- | :--- |
| `VITE_SUPABASE_URL` | URL raiz do projeto no Supabase (sem caminhos adicionais) | `https://seu-id.supabase.co` |
| `VITE_SUPABASE_PUBLISHABLE_KEY` | Chave pública da API do Supabase configurada como **Config** | `sb_publishable_...` |
