# 📚 Organizador de Estudos (StudyOrganizer)

**Organize suas tarefas, matérias e prazos de forma prática e inteligente.**  
Um SaaS/MVP pensado para estudantes, com dashboard de tarefas, alertas automáticos e gestão de matérias. Ideal para facilitar os estudos e nunca perder um prazo.

---

## 🎯 Objetivo do Projeto

O **Organizador de Estudos** é uma plataforma que ajuda estudantes a:  
- Cadastrar suas matérias e tarefas.  
- Visualizar tarefas pendentes e concluídas em um dashboard simples.  
- Receber alertas automáticos de tarefas próximas do prazo via WhatsApp ou Telegram (integração n8n).  

O objetivo é criar um **MVP funcional**, que possa ser vendido ou apresentado como portfólio em faculdades ou hackathons.

---

## ⚙ Funcionalidades do MVP

- [x] Cadastro de usuários (alunos)  
- [x] Login e autenticação  
- [x] Cadastro de matérias  
- [x] Cadastro de tarefas (título, descrição, data, prioridade, matéria)  
- [x] Dashboard com tarefas pendentes e concluídas  
- [x] Marcar tarefas como concluídas  
- [x] Alertas automáticos via WhatsApp/Telegram (via n8n)  

**Funcionalidades futuras (versão 2):**  
- Estatísticas de produtividade  
- Tags/categorias de tarefas  
- Integração com Google Calendar  
- Compartilhamento de tarefas entre alunos  

---

## 🖥 Telas do Sistema

1. **Login / Cadastro**  
   - Campos: nome, email, senha  
   - Botões: "Cadastrar / Entrar"

2. **Dashboard principal**  
   - Lista de matérias  
   - Lista de tarefas pendentes e concluídas  
   - Botão para adicionar nova tarefa  
   - Filtro por matéria ou data  

3. **Criar Tarefa**  
   - Campos: título, descrição, matéria, data de entrega, prioridade  
   - Botão: "Salvar"

4. **Visualizar Tarefa**  
   - Mostra detalhes da tarefa  
   - Botão: “Marcar como concluída”  
   - Botão: “Editar” (opcional MVP)  
   - Botão: “Deletar” (opcional MVP)  

---

## 🗄 Estrutura do Banco de Dados

**Usuários**  
| id | nome | email | senha_hash | data_criacao |

**Matérias**  
| id | nome | usuario_id |

**Tarefas**  
| id | titulo | descricao | materia_id | usuario_id | data_entrega | prioridade | concluida (bool) | data_criacao |

> Inicialmente recomendado usar **SQLite**, fácil para testes locais. Pode evoluir para **PostgreSQL** ou **MySQL**.

---

## 🔧 Tecnologias Utilizadas

- **Frontend:** React (Web) ou PySide6 (Desktop)  
- **Backend:** Python (FastAPI) ou Node.js (Express)  
- **Banco de Dados:** SQLite (MVP) / PostgreSQL (futuro)  
- **Automação:** n8n para envio de alertas no WhatsApp/Telegram  
- **Hospedagem:** Render, Railway ou Vercel  

---

## ⚡ Fluxo de Alertas com n8n

1. Agendador diário verifica tarefas próximas do prazo.  
2. Filtra tarefas pendentes com entrega em até 1 dia.  
3. Envia mensagem no WhatsApp/Telegram com resumo das tarefas:  

> “Olá, Vinícius! Você tem 2 tarefas vencendo amanhã: *Matemática - Exercícios Cap 4*, *História - Resumo Guerra Fria*.”

---

## 🚀 Como Executar o Projeto (MVP)

1. Clone o repositório:  
```bash
git clone https://github.com/seu-usuario/studyorganizer.git
cd studyorganizer
