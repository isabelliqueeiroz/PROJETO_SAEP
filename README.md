
# ⚙️ AutoMecânica Pro

### Sistema de gerenciamento para oficina mecânica

**Projeto acadêmico • SAEP / SENAI**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0.3-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css&logoColor=white)](https://developer.mozilla.org/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/docs/Web/JavaScript)

*Organização, praticidade e centralização das informações de uma oficina
em um só sistema.*
:::📌 Sobre o projeto
O AutoMecânica Pro é um sistema web desenvolvido como proposta de
projeto acadêmico para o contexto SAEP / SENAI. A aplicação foi
planejada para auxiliar na organização das rotinas de uma oficina
mecânica, reunindo informações de clientes, veículos e agendamentos em
uma única plataforma.

A aplicação utiliza Python com Flask no backend, MySQL para
persistência dos dados e uma interface web construída com HTML, CSS e
JavaScript puro.
Status: projeto em desenvolvimento/implementação. Os itens
descritos neste README representam o escopo previsto no guia; confirme
cada funcionalidade no ambiente executável antes de considerá-la
validada.

✨ Funcionalidades previstas
  Módulo                              Recursos
  🔐 Autenticação                 Login de funcionários, mensagens de
                                      erro, encerramento de sessão e
                                      configuração de expiração

  👥 Clientes                     Cadastro, consulta, pesquisa,
                                      edição e exclusão de registros

  🚘 Veículos                     Cadastro vinculado a um cliente,
                                      consulta, edição e exclusão

  🗓️ Agendamentos                 Registro de serviços, consulta em
                                      ordem cronológica e atualização de
                                      data/horário

  📊 Dashboard                    Indicadores de clientes, veículos e
                                      agendamentos, além de próximos
                                      serviços

  🛡️ Proteção de dados            Uso de Bcrypt no fluxo de
                                      autenticação e tratamento de CPF
                                  previsto no projeto
🧰 Tecnologias utilizadas
- Python --- linguagem utilizada no backend.
- Flask --- rotas, sessões e renderização de páginas.
- MySQL --- banco de dados relacional.
- mysql-connector-python --- comunicação entre Python e MySQL.
- Bcrypt --- hash de senhas e implementação de hash para CPF
  descrita no guia.
- HTML5 --- estrutura das páginas.
- CSS3 --- apresentação visual.
- JavaScript puro --- interações da interface, incluindo funções
  para modais.
🗂️ Estrutura do projeto
oficina_mecanica/
├── saep_db.sql
└── sistema/
    ├── app.py
    ├── autenticacao.py
    ├── banco.py
    ├── clientes.py
    ├── veiculos.py
    ├── agendamento.py
    ├── rotas.py
    ├── requirements.txt
    ├── templates/
    │   ├── base.html
    │   ├── login.html
    │   ├── dashboard.html
    │   ├── clientes.html
    │   ├── veiculos.html
    │   └── agendamentos.html
    └── static/
        ├── css/
        │   └── style.css
        └── js/
            └── main.js
Observação: os arquivos dashboard.html, clientes.html,
veiculos.html, agendamentos.html e style.css devem existir para
que as respectivas páginas sejam exibidas. Ajuste a árvore acima se a
estrutura real do repositório for diferente.
⚙️ Pré-requisitos
Antes de iniciar, tenha instalado e configurado:
- Python
- MySQL em execução
- Um editor de código, como Visual Studio
  Code
- Terminal com acesso ao comando python ou python3
🚀 Instalação e execução
1. Clone o repositório
Substitua SEU_USUARIO e NOME_DO_REPOSITORIO pelos dados reais do seu
GitHub.
git clone https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git
cd NOME_DO_REPOSITORIO
2. Crie e ative um ambiente virtual
Windows --- PowerShell:
python -m venv venv
.\venv\Scripts\Activate.ps1
Windows --- CMD:
python -m venv venv
venv\Scripts\activate.bat
Linux / macOS:
python3 -m venv venv
source venv/bin/activate
3. Instale as dependências
Na raiz do projeto, execute:
pip install -r sistema/requirements.txt
4. Crie o banco de dados
Com o MySQL em execução, execute o script SQL conforme o seu ambiente.
mysql -u root -p < saep_db.sql
O comando solicitará a senha do usuário MySQL. Se o comando mysql não
estiver disponível no terminal, execute o arquivo saep_db.sql por uma
ferramenta gráfica, como MySQL Workbench.
Atenção: o script de exemplo contém comandos DROP TABLE. Revise
o arquivo antes de executá-lo, pois eles podem apagar tabelas
existentes com os mesmos nomes.

5. Configure a conexão
O módulo sistema/banco.py lê estas variáveis de ambiente:

  Variável        Finalidade
  DB_HOST       Servidor do banco
  DB_USER       Usuário do MySQL
  DB_PASSWORD   Senha do MySQL
  DB_NAME       Nome do banco; padrão indicado no código: saep_db
  DB_PORT       Porta do MySQL; padrão indicado no código: 3306

Configure as variáveis de acordo com seu ambiente. Não publique senhas,
chaves secretas ou credenciais reais no GitHub.
6. Teste a conexão com o banco
Na raiz do projeto:
python sistema/banco.py
O script deve informar se conseguiu se conectar e listar as tabelas
encontradas. Em caso de falha, confira se o MySQL está ativo, se o banco
foi criado e se as credenciais estão corretas.
7. Inicie a aplicação
python sistema/app.py
Depois, abra no navegador:
http://127.0.0.1:5000
Para encerrar o servidor, volte ao terminal e pressione Ctrl + C.
🔑 Acesso de demonstração
O guia de desenvolvimento inclui credenciais destinadas ao ambiente de
teste:

  Perfil          Login        Senha de demonstração
  Administração   admin      admin123
  Mecânico        mecanico   senha123
  Recepção        recepcao   rec123

Importante: altere essas credenciais antes de qualquer uso real. Não
reutilize senhas de demonstração em produção e não inclua dados pessoais
reais no banco de teste.
🔒 Segurança e privacidade
O projeto prevê medidas relacionadas à segurança, mas elas precisam ser
revisadas e testadas antes de qualquer implantação real:
- Usar hash seguro para senhas e verificar corretamente os hashes
  armazenados.
- Configurar SECRET_KEY por variável de ambiente, sem manter uma
  chave padrão no código.
- Não armazenar nem exibir CPF de forma desnecessária. Bcrypt é um
  hash unidirecional, não criptografia reversível; avalie como o
  sistema precisará consultar o CPF antes de definir a estratégia de
  armazenamento.
- Restringir o acesso às páginas e ações que exigem autenticação.
- Usar dados fictícios nos testes e proteger informações pessoais
  conforme a LGPD.
- Desativar o modo de depuração (debug) e revisar configurações de
  sessão antes da publicação.
🧪 Checklist de validação
Use este checklist durante os testes. Marque cada item somente depois de
executá-lo e confirmar o resultado.
- [ ] Login válido e tratamento de credenciais incorretas
- [ ] Bloqueio de acesso às páginas internas sem autenticação
- [ ] Conexão com o banco de dados
- [ ] Cadastro, pesquisa, edição e exclusão de clientes
- [ ] Validação do CPF com exatamente 11 dígitos numéricos
- [ ] Cadastro de veículo vinculado a cliente existente
- [ ] Edição e exclusão de veículos
- [ ] Listagem de agendamentos em ordem cronológica
- [ ] Atualização de data/horário de agendamento
- [ ] Dashboard com dados do banco
- [ ] Encerramento de sessão e expiração conforme configurado
🎯 Objetivos de aprendizagem
- Praticar a integração entre frontend, backend e banco de dados
  relacional.
- Organizar uma aplicação Flask em módulos.
- Trabalhar com operações CRUD (criar, consultar, atualizar e
  excluir).
- Implementar autenticação e validação de formulários.
- Aplicar relacionamentos entre tabelas e consultas SQL.
- Planejar testes para verificar regras de negócio.
👩‍💻 Contexto acadêmico
Projeto desenvolvido no contexto de atividades de SAEP / SENAI, com
finalidade educacional.
📄 Licença
Nenhuma licença foi informada no material de referência. Caso o projeto
seja publicado, escolha e adicione uma licença apropriada ao
repositório.
::: {align="center"}
**⚙️ AutoMecânica Pro**\
*Tecnologia para uma oficina mais organizada.*
:::
