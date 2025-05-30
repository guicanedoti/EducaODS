# Projeto EducaODS: Conscientização e Educação Digital para a Agenda 2030

---

## 🎯 Visão Geral do Projeto

O **EducaODS** é uma plataforma de educação online inovadora, desenvolvida para **conscientizar adolescentes de 12 a 18 anos sobre os Objetivos de Desenvolvimento Sustentável (ODS) da ONU**. Nosso objetivo é transformar a compreensão da Agenda 2030 em ações práticas, capacitando a nova geração a contribuir ativamente para um futuro mais sustentável. O projeto visa replicar o engajamento de redes sociais populares (como TikTok e Instagram) para tornar o aprendizado dos ODS dinâmico, interativo e divertido.

## ✨ Funcionalidades Principais (MVP - Produto Mínimo Viável)

Esta primeira versão da plataforma inclui:

* **Blocos de Unidades por ODS:** Conteúdo didático organizado em módulos dedicados a cada Objetivo de Desenvolvimento Sustentável.
* **Aulas Dinâmicas e Interativas:** Aulas curtas e envolventes que combinam **vídeos animados, infográficos interativos, textos concisos e áudios**, projetadas para manter o foco do público adolescente.
* **Exercícios de Fixação:** Atividades práticas após cada aula para reforçar o aprendizado.
* **Sistema de Progresso Visual:** Acompanhamento do percentual de conclusão de cada bloco, incentivando o aluno a avançar.
* **"Provas Finais" por Bloco:** Avaliações ao término de cada ODS para verificar a compreensão do conteúdo.
* **Critério de Avanço:** Exigência de 70% de acerto nas provas finais para liberar o próximo bloco, garantindo a absorção do conhecimento.

## 💡 Estratégias de Engajamento e UX/UI

Para manter os adolescentes engajados, aplicamos princípios de design inspirados em redes sociais e gamificação:

* **Conteúdo em Pílulas:** Vídeos curtos (2-5 minutos) e dinâmicos com ritmo acelerado e animações.
* **Interatividade Constante:** Quizzes rápidos pós-vídeo e infográficos interativos.
* **Gamificação:** Sistema de pontos, medalhas, avatares personalizáveis e potencial para desafios temáticos.
* **Design Vibrante e Intuitivo:** Interface limpa com cores modernas e iconografia clara, priorizando a usabilidade mobile ("Mobile-First").
* **Feedback Imediato:** Recompensas visuais e feedback rápido sobre o desempenho.

## 🚀 Tecnologias Utilizadas

* **Front-end:** HTML, CSS, JavaScript com Vue.js
* **Back-end:** Python com Django, Django REST Framework
* **Banco de Dados:** PostgreSQL
* **Conteinerização:** Docker, Docker Compose
* **Hospedagem (Previsão):** Vercel/Netlify (Front-end) + Render.com/Railway.app (Back-end/BD)
* **Controle de Versão:** Git & GitHub

## 🛠️ Como Rodar o Projeto Localmente

Para iniciar o projeto em seu ambiente local, siga os passos abaixo. Utilizaremos **Docker e Docker Compose** para gerenciar os ambientes de desenvolvimento do backend e do banco de dados, garantindo consistência e facilidade de configuração.

### **Pré-requisitos:**

* **Git:** Instalado e configurado.
* **Docker Desktop:** Instalado e rodando (para Windows, Mac ou Linux).

### **Instruções:**

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/educaods.git](https://github.com/seu-usuario/educaods.git)
    ```
    *Substitua `seu-usuario` pelo seu nome de usuário no GitHub.*

2.  **Navegue até a pasta raiz do projeto:**
    ```bash
    cd educaods
    ```

3.  **Configurar variáveis de ambiente:**
    * Crie um arquivo chamado `.env` na raiz do projeto (ao lado do `docker-compose.yml`).
    * Preencha-o com suas credenciais do banco de dados. Exemplo:
        ```dotenv
        # .env
        DB_NAME=educaods_db
        DB_USER=educaods_user
        DB_PASSWORD=SUA_SENHA_POSTGRES # Use a senha do seu usuário 'postgres' principal
        DB_HOST=db
        DB_PORT=5432
        ```
    * *Certifique-se de substituir `SUA_SENHA_POSTGRES` pela sua senha real.*

4.  **Iniciar os serviços com Docker Compose:**
    * Este comando construirá as imagens Docker e iniciará os contêineres do banco de dados (PostgreSQL) e do backend (Django).
    ```bash
    docker compose up --build -d
    ```
    * O `-d` (detached mode) permite que os contêineres rodem em segundo plano, liberando seu terminal.

5.  **Aplicar migrações do banco de dados:**
    * Uma vez que os contêineres estejam rodando, execute as migrações do Django para criar as tabelas no banco de dados.
    ```bash
    docker compose exec backend python manage.py migrate
    ```

6.  **Criar um superusuário (opcional, mas recomendado para acesso ao Admin Django):**
    ```bash
    docker compose exec backend python manage.py createsuperuser
    ```
    * Siga as instruções no terminal para definir as credenciais do seu usuário administrador.

7.  **Acessar o Backend:**
    * O servidor Django estará rodando dentro do contêiner e acessível em `http://localhost:8000/`.
    * Você pode acessar o painel de administração em `http://localhost:8000/admin/` usando o superusuário criado.

8.  **Configuração e Execução do Front-end (Vue.js):**
    * *Instruções detalhadas para configurar e iniciar o frontend via Docker ou localmente serão adicionadas aqui após a sua configuração.*

9.  **Parar os serviços Docker:**
    * Quando terminar de trabalhar, você pode parar todos os contêineres definidos no `docker-compose.yml` com:
    ```bash
    docker compose down
    ```

## 🤝 Contribuições

Este projeto está sendo desenvolvido como parte do meu portfólio acadêmico. Sugestões e feedback são bem-vindos!

## 📄 Licença

Este projeto está licenciado sob a Licença MIT.

---