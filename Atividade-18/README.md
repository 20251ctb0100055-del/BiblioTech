# Atividade 18 — Diagrama de Classes do BiblioTech

**Nome:**JOAO PEDRO MAUDA 
**Turma:** 2º ano — Técnico em Informática Integrado  

## Diagrama

![Diagrama de Classes do BiblioTech](diagrama-classes.png)

## Por que estes números (associação Bibliotecario — Emprestimo)

- Perto de **Emprestimo** eu coloquei `0..*` porque um único bibliotecário pode realizar e registrar vários empréstimos ao longo do seu turno de trabalho no balcão.
- Perto de **Bibliotecario** eu coloquei `1` porque cada registro de empréstimo no sistema é efetuado por exatamente um bibliotecário responsável.

## Rastreabilidade (Nível B)

- A operação `podePegarEmprestado()` da classe `Leitor` atende ao caso de uso **"Realizar Empréstimo"** (UC01) identificado na Atividade 17.

## Refinamento do Modelo e Nível A

### 1. Enxugamento do Diagrama
- Removi o atributo `statusLivro` da classe `Livro` e o substituí pela operação dinâmica `estaDisponivel(): boolean`, evitando redundância com o estado armazenado na classe `Emprestimo`.

### 2. Resposta à Objeção (Bibliotecario como Atributo vs. Classe)
**Objeção do colega:** "Bibliotecario nem precisava ser classe — bastava um atributo `bibliotecario: String` dentro de `Emprestimo`."

**Defesa do Modelo:**  
O colega está equivocado do ponto de vista de Análise e Projeto de Sistemas. Tratar `Bibliotecario` apenas como uma `String` viola o princípio de orientação a objetos pelas seguintes razões:
1. **Atribuição de Papéis e Autenticação:** O bibliotecário é um usuário do sistema com comportamento de herança (possui `matriculaFuncional`, herdando `nome` e `matricula` de `Usuario`), necessitando de privilégios de acesso e operações de login que uma simples string não suporta.
2. **Integridade de Dados:** Se armazenássemos uma string no empréstimo, qualquer erro de digitação ("Ana Silva" vs "Ana S.") corromperia relatórios do sistema. Ao manter uma associação de classe, garantimos a integridade referencial com a entidade real que realizou a operação.

## Autoavaliação

- **Conceito que pretendo:** A (Excelente)
- **Onde isso se prova no diagrama:**
  - **Classes e Notação (Nível A):** 6 classes estruturadas (`Usuario`, `Leitor`, `Bibliotecario`, `Emprestimo`, `Livro` e a nova classe `Reserva`), sem redundâncias.
  - **Associações (Nível A):** Todas as linhas contínuas com multiplicidade, incluindo a nova classe `Reserva` (`1` Leitor solicita `0..*` Reservas; `0..*` Reservas reservam `1` Livro) e a ligação `Bibliotecario` `1` —— `registra` —— `0..*` `Emprestimo`.
  - **Herança (Nível A):** Triângulo vazado apontando para `Usuario` a partir de `Leitor` e `Bibliotecario`.
  - **Justificativa e Rastreabilidade (Nível A):** Rastreabilidade com caso de uso descrita, enxugamento justificado e resposta à objeção apresentada.