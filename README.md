# P1 - MongoDB com Docker
**Aluno:** Herlon V F de Almeida - 202413733
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
```
<img width="684" height="948" alt="Captura de tela 2026-04-14 020048" src="https://github.com/user-attachments/assets/b045170b-c0a3-4d63-9d92-4010ec6f5bf4" />


**1. Buscar todos os alunos:** - **db.alunos.find().pretty();**

<img width="855" height="978" alt="Captura de tela 2026-04-14 020149" src="https://github.com/user-attachments/assets/5293c630-9a09-489f-b61f-ada41644152f" />


**2. Buscar alunos do curso "ADS"** - **db.alunos.find({ curso: "ADS" });**

<img width="577" height="387" alt="Captura de tela 2026-04-14 020221" src="https://github.com/user-attachments/assets/7104efcf-4235-414e-bcd7-6ae3f0634a4c" />

**3. Buscar alunos com idade maior que 21** - **db.alunos.find({ idade: { $gt: 21 } });**

<img width="544" height="534" alt="Captura de tela 2026-04-14 020243" src="https://github.com/user-attachments/assets/115b4189-3357-4984-80d5-fc67cd4b185f" />


**4. Atualizar a idade de um aluno "Atualizada a idade da aluna Minatozaki Sana para 29 anos."** -**db.alunos.updateOne({ nome: "Minatozaki Sana" }, { $set: { idade: 29 } });**

<img width="775" height="183" alt="Captura de tela 2026-04-14 020810" src="https://github.com/user-attachments/assets/f67f324c-8a8d-4c92-9545-2d19677dafe0" />


**5. Adicionar uma nova nota a um aluno "Adicionada a nota 10 para o aluno Herlon Almeida."** - **db.alunos.updateOne({ nome: "Herlon Almeida" }, { $push: { notas: 10 } });**

<img width="797" height="169" alt="Captura de tela 2026-04-14 020930" src="https://github.com/user-attachments/assets/11496fd3-3576-4e90-913b-8abde76b79d3" />


**6. Remover um aluno "Removida a aluna Aemeath Illyrios."** - **db.alunos.deleteOne({ nome: "Aemeath Illyrios" });**

<img width="575" height="72" alt="Captura de tela 2026-04-14 021000" src="https://github.com/user-attachments/assets/22b12bd2-65e2-4d0f-80f9-f6bbb9ba511f" />


**7. Média de notas por aluno** - 
**db.alunos.aggregate([
  {
    $project: {
      nome: 1,
      media: { $avg: "$notas" }
    }
  }
]);**

<img width="495" height="687" alt="Captura de tela 2026-04-14 021136" src="https://github.com/user-attachments/assets/044c5e49-41f4-45bf-9194-4e2a0eda4987" />


**8. Quantidade de alunos por curso** -
**db.alunos.aggregate([
  {
    $group: {
      _id: "$curso",
      quantidade: { $sum: 1 }
    }
  }
]);**

<img width="493" height="264" alt="Captura de tela 2026-04-14 021212" src="https://github.com/user-attachments/assets/07f4b751-90ee-4ada-ae73-be9bce0867ea" />







