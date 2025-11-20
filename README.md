Este projeto é uma plataforma completa de descoberta vocacional, assistente de carreira com IA e dashboard profissional de carreiras, totalmente voltado para orientar estudantes e iniciantes na área de tecnologia.

O sistema é composto por:

Teste Vocacional (carreer_vocacional.html)

Agente de Carreira com IA (career_agent.html + career_agent.json)

Dashboard Profissional de Carreiras (careers_dashboard.html)

Base de Carreiras Tech (careers.json)

Mapeamento de IDs (ids,carreira.txt)

Página Inicial (index.html)

🚀 Funcionalidades Principais
✅ 1. Teste Vocacional

O usuário responde perguntas simples que identificam suas preferências profissionais.
Ao final, o sistema calcula a carreira ideal e:

gera um ID correspondente

salva no navegador via localStorage

redireciona automaticamente para o dashboard

Arquivo responsável:
carreer_vocacional.html

✅ 2. Agente de IA (Career Agent)

O usuário conversa com um agente inteligente baseado no arquivo:

career_agent.json

Esse agente analisa:

histórico da conversa

perfil do usuário

objetivos profissionais

áreas de afinidade

Ao final ele entrega apenas 1 resultado (Opção A):

salva o mesmo ID no navegador

redireciona automaticamente para o dashboard

Arquivo responsável:
career_agent.html

✅ 3. Dashboard de Carreira

O dashboard exibe informações completas da carreira selecionada:

salário médio

nível de demanda

porcentagem de trabalho remoto

perspectiva de crescimento

gráfico de skills

gráfico de senioridades

lista de cursos

lista de universidades

vídeos recomendados

O dashboard lê automaticamente:

localStorage.career_result_id

ou fallback ?id=

carrega os dados de careers.json

renderiza a carreira correta

Arquivo responsável:
careers_dashboard.html

🗂 Estrutura do Projeto
/ (raiz)
├── index.html
├── carreer_vocacional.html
├── career_agent.html
├── career_agent.json
├── careers_dashboard.html
├── careers.json
├── ids,carreira.txt
├── README.md  ← (este arquivo)

🧠 Fluxo Lógico do Sistema
🟦 Fluxo 1: Teste Vocacional
carreer_vocacional.html
    → calcula carreira
    → id = "desenvolvedor-front-end"
    → localStorage.setItem("career_result_id", id)
    → redireciona para careers_dashboard.html

🟩 Fluxo 2: Career Agent (IA)
career_agent.html
    → conversa do usuário
    → agente escolhe carreira principal
    → id = result.principal
    → localStorage.setItem("career_result_id", id)
    → redireciona automaticamente

🟧 Fluxo 3: Dashboard
careers_dashboard.html
    → lê id de localStorage
    → carrega careers.json
    → monta dashboard da carreira selecionada

📦 Formato do careers.json

Cada carreira segue esta estrutura:

{
  "desenvolvedor-front-end": {
    "id": "desenvolvedor-front-end",
    "title": "Desenvolvedor Front-End",
    "salaryAvg": 5500,
    "demandLevel": "Alta",
    "remotePercent": 72,
    "growth": 14,
    "skills": [
      { "name": "HTML/CSS", "score": 90 },
      { "name": "JavaScript", "score": 95 }
    ],
    "seniority": {
      "Junior": 45,
      "Pleno": 35,
      "Senior": 20
    },
    "universities": [],
    "courses": [],
    "videos": []
  }
}

🧪 Como Testar Localmente

Para testar sem servidor:

Abra carreer_vocacional.html no navegador

Faça o teste

Veja o dashboard carregando a carreira correspondente

Para testar servidor local (recomendado para fetch):

npx http-server .


ou

python -m http.server 8080

🌐 Deploy no GitHub Pages

Commit e envie todos os arquivos para o GitHub

Vá em:

Settings → Pages → Deploy from branch


Escolha a branch main

Pasta raíz /

O sistema ficará acessível em:

https://seuusuario.github.io/nome-do-projeto/

👨‍💻 Tecnologias Utilizadas

HTML5 / CSS3

JavaScript Vanilla

TailwindCSS

Chart.js

Google Gemini API

localStorage

Fetch API

📝 Licença

Este projeto é totalmente livre para uso, modificação e implementação.
