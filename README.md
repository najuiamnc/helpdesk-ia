🎧 Helpdesk IA — Triagem Automática de Chamados

Sistema de helpdesk que usa Inteligência Artificial para triar chamados de suporte automaticamente: ao receber um chamado, a IA classifica a categoria, define a prioridade, gera um resumo e sugere uma resposta ao usuário.

Projeto pessoal desenvolvido para praticar integração de APIs de IA, back-end com Python e construção de interfaces com React.

✨ Funcionalidades
Abertura de chamados por formulário
Triagem automática por IA:
Categoria (acesso, hardware, rede, software, outros)
Prioridade (baixa, média, alta, crítica)
Resumo em uma frase para o atendente
Resposta sugerida ao usuário
Indicação se o chamado precisa de atendimento humano
Listagem de chamados com os dados da triagem
API REST documentada automaticamente (Swagger em /docs)
🛠️ Tecnologias
Back-end: Python, FastAPI, Pydantic
IA: Claude API (Anthropic)
Front-end: React
Banco de dados: SQLite
Versionamento: Git e GitHub
🧠 Como funciona
Usuário abre chamado → API (FastAPI) → Claude API (classificação em JSON)
                              ↓
                      Chamado salvo com a triagem
                              ↓
                  Painel exibe chamados triados

A IA recebe o título e a descrição do chamado e devolve um JSON estruturado, que é validado antes de ser salvo.

Exemplo de resposta da triagem:

json
{
  "categoria": "acesso",
  "prioridade": "alta",
  "resumo": "Usuário não consegue fazer login no sistema interno.",
  "resposta_sugerida": "Olá! Vamos te ajudar com o acesso. Pode confirmar se aparece alguma mensagem de erro?",
  "precisa_humano": false
}
🚀 Como rodar o projeto
Pré-requisitos
Python 3.10+
Node.js 18+ (para o front-end)
Uma chave de API da Anthropic (platform.claude.com)
1. Clonar o repositório
bash
git clone https://github.com/najuiamnc/helpdesk-ia.git
cd helpdesk-ia
2. Configurar o back-end
bash
cd backend
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt

Crie um arquivo .env na pasta backend baseado no .env.example:

ANTHROPIC_API_KEY=sua_chave_aqui

⚠️ Nunca compartilhe sua chave nem suba o arquivo .env para o GitHub.

Inicie a API:

bash
uvicorn main:app --reload

A API ficará disponível em http://localhost:8000 e a documentação interativa em http://localhost:8000/docs.

3. Configurar o front-end
bash
cd frontend
npm install
npm start
📡 Endpoints principais
Método	Rota	Descrição
POST	/chamados	Cria um chamado e executa a triagem por IA
GET	/chamados	Lista os chamados com os dados da triagem
📁 Estrutura do projeto
helpdesk-ia/
├── backend/
│   ├── main.py
│   ├── triagem.py
│   └── requirements.txt
├── frontend/
├── .env.example
├── .gitignore
└── README.md
📸 Demonstração
<!-- Adicione aqui prints da tela ou um GIF do sistema funcionando --> <!-- Exemplo: ![Painel de chamados](docs/painel.png) -->
🔮 Próximos passos
 Autenticação de usuários e atendentes
 Base de conhecimento (FAQ) para respostas mais precisas
 Métricas de acerto da triagem
 Deploy online
👩‍💻 Autora

Julia de Souza Amâncio

GitHub: @najuiamnc
LinkedIn: linkedin.com/in/julia-amâncio
Portfólio: najuiamnc.github.io/portfolio-pessoal
