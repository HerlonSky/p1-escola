# P1 - MongoDB com Docker
**Aluno:** Herlon V F de Almeida
**Curso:** Engenharia de Software

Este repositório contém a resolução da prova prática de Banco de Dados utilizando Docker e o terminal `mongosh`.

## ⚙️ Configuração Inicial
Criação do banco de dados `escola` e inserção dos dados utilizando um conjunto único de alunos.

```javascript
use escola;

db.alunos.insertMany([
  {
    "nome": "Herlon Almeida",
    "idade": 23,
    "curso": "Engenharia de Software",
    "notas": [9, 8.5, 10],
    "endereco": { "cidade": "Maricá", "estado": "RJ" }
  },
  {
    "nome": "Minatozaki Sana",
    "idade": 28,
    "curso": "Engenharia de Software",
    "notas": [8, 7.5, 9],
    "endereco": { "cidade": "Maricá", "estado": "RJ" }
  },
  {
    "nome": "Aemeath Illyrios",
    "idade": 21,
    "curso": "Engenharia de Software",
    "notas": [7, 8, 8.5],
    "endereco": { "cidade": "Niterói", "estado": "RJ" }
  },
  {
    "nome": "Luxanna Crownguard",
    "idade": 19,
    "curso": "ADS",
    "notas": [9.5, 9, 10],
    "endereco": { "cidade": "São Gonçalo", "estado": "RJ" }
  },
  {
    "nome": "Park Jihyo",
    "idade": 27,
    "curso": "ADS",
    "notas": [8.5, 8, 9],
    "endereco": { "cidade": "Rio de Janeiro", "estado": "RJ" }
  }
]);
<img width="684" height="948" alt="Captura de tela 2026-04-14 020048" src="https://github.com/user-attachments/assets/b045170b-c0a3-4d63-9d92-4010ec6f5bf4" />
