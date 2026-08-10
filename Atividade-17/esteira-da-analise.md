# Esteira da Análise — BiblioTech

**Estudante:** João Pedro Mauda

## Funcionalidade 1: Emprestar livro

- **1.2 Fala do cliente:** "O aluno chega no balcão com a carteirinha e o livro, e eu preciso registrar a saída no sistema para controlar a data de devolução."
- **2.4 História de usuário:** Como leitor, quero pegar um livro emprestado, para estudar em casa e manter minhas leituras em dia.
- **3.6 Requisito:** RF01 — O sistema deve permitir o registro do empréstimo de livros para leitores cadastrados.
- **4.8 Caso de uso (RF01):** Ator Bibliotecário → "Emprestar livro"

## Funcionalidade 2: Cadastrar leitor

- **1.2 Fala do cliente:** "Quando entra um aluno novo ou professor, preciso salvar os dados dele no sistema antes de liberar qualquer empréstimo."
- **2.4 História de usuário:** Como leitor, quero me cadastrar na biblioteca, para ter acesso ao acervo e poder retirar livros.
- **3.6 Requisito:** RF02 — O sistema deve permitir o cadastro de novos leitores com seus dados pessoais e de contato.
- **4.8 Caso de uso (RF02):** Ator Bibliotecário → "Cadastrar leitor"

## Rastreabilidade

| Elipse no diagrama | Veio do requisito | Que veio da fala |
|---|---|---|
| Emprestar livro (RF01) | RF01 — O sistema deve permitir o registro do empréstimo de livros | "O aluno chega no balcão com a carteirinha e o livro, e eu preciso registrar a saída no sistema..." |
| Cadastrar leitor (RF02) | RF02 — O sistema deve permitir o cadastro de novos leitores | "Quando entra um aluno novo ou professor, preciso salvar os dados dele no sistema..." |
| Buscar livro do acervo (RF03) | RF03 — O sistema deve permitir a busca de livros no acervo | "Preciso encontrar onde o livro está e verificar se ele está disponível." |
| Devolver livro (RF040) | RF040 — O sistema deve permitir o registro da devolução de um livro | "Quando o aluno traz o livro de volta, eu preciso dar baixa na hora, senão fica parecendo que ele ainda está com o livro." |

<!-- Nível A: conte o caminho completo de cada funcionalidade,
     da fala do cliente até o que está desenhado no diagrama. -->

### Percurso Completo da Rastreabilidade (Nível A)
1. **Empréstimo de Livro:** A necessidade trazida pelo cliente (*"registrar a saída no sistema"*) deu origem à história do usuário na perspectiva do benefício do leitor. Esta se transformou no requisito formal **RF01**, que culminou no caso de uso **"Emprestar livro (RF01)"**, operado no sistema pelo ator **Bibliotecário** e desenhado dentro da fronteira no diagrama.
2. **Cadastro de Leitor:** A dor verbalizada (*"salvar os dados dele no sistema antes de liberar qualquer empréstimo"*) virou a história do leitor, convertida no requisito **RF02** e mapeada na elipse **"Cadastrar leitor (RF02)"**, acionada pelo **Bibliotecário**.

## Relacionamento entre casos de uso (nível A)

- **Tipo:** «include»
- **Entre:** "Emprestar livro (RF01)" e "Buscar livro do acervo (RF03)"
- **Por que é esse e não o outro:** Foi utilizado o relacionamento `«include»` porque a busca/localização do livro no acervo é uma etapa **obrigatória** e indispensável (acontece SEMPRE) para a realização do empréstimo. O sistema precisa obrigatoriamente localizar e validar o livro para efetivar a saída.

## Autoavaliação

**Conceito pretendido:** A

- **Conversei sobre esta atividade com:** ninguém
- **Esteira da análise:** As 2 esteiras estão completas nas 4 estações na ordem correta, com a fala do cliente entre aspas, história no padrão Como/quero/para, RF numerado e caso de uso no formato verbo+objeto identificando o Bibliotecário como operador.
- **Diagrama e notação:** Diagrama no draw.io com fronteira "BiblioTech", ator "Bibliotecário" do lado de fora, elipses internas com o nome do caso de uso e o código RF, além do relacionamento `«include»` com notação tracejada e seta aberta para o caso incluído.
- **Rastreabilidade:** Mapeada na tabela e detalhada em parágrafo contando todo o caminho percorrido da fala até o desenho no diagrama.
- **Organização da entrega:** Todos os 4 arquivos com nomes exatos criados na pasta `Atividade-17`, com o `README.md` configurado como índice e justificativas de modelagem inseridas.