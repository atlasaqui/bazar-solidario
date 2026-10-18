ENTREGA 02  /  PROJETO INTEGRADOR 3

Testes unitários
Cadastro de usuário

Entrega 2 - Parte 1

Projeto: ISAC Brechó - Bazar Solidário

Parceiro: ISAC, por meio do Porto Digital

Módulo: UsuarioService e testes de cadastro

Revisão: 3.0 | 18 de outubro de 2026

GitHub: https://github.com/Residencia-Tecnologica-2026-2/bazar-solidario

Branch local preparada: entrega/02-testes-unitarios-parte-1

Endereço previsto: https://github.com/Residencia-Tecnologica-2026-2/bazar-solidario/tree/entrega/02-testes-unitarios-parte-1

Sobre esta entrega

Para esta etapa, implementamos a classe responsável pelo cadastro no front-end. Ela verifica os dados antes do envio, faz a requisição e interpreta a resposta do servidor. O formulário usa essa mesma classe; os testes exercitam as regras sem depender de um servidor ativo.

Equipe

Victor William Monteiro da Rocha
Geovana Leticia
Silas Freitas
Mateus Ferreira
Willyanne Darline
Ruan Araujo
Suellen da Silva
Cynthia Melo
O que foi implementado
1 classe de serviço | 1 classe de teste com 7 métodos | 7 regressões HTTP adicionais
Implementação do cadastro

Classe: UsuarioService

Arquivo: frontend/src/services/usuarios.ts

Método: cadastrar(dados, confirmacao)

Interface: frontend/src/components/Cadastro.tsx

Classe de teste: UsuarioServiceTest, em frontend/tests/UsuarioService.test.ts

Responsabilidades da classe

O serviço exige nome preenchido, e-mail válido e senha entre 8 e 128 caracteres. Também compara a senha com a confirmação. Com os dados válidos, envia nome, e-mail e senha para a API. Uma resposta só é aceita quando contém um identificador válido e perfil CLIENTE; a senha é descartada antes de devolver os dados à interface.

Organização dos testes

Cenário | Verificação

Campos inválidos | Nenhuma requisição é enviada.

Confirmação diferente | O serviço rejeita as senhas divergentes.

Valores nos limites | Nome e senha nos limites são aceitos.

Resposta inesperada | ID inválido e perfil ADMIN são rejeitados.

HTTP 422 | A mensagem orienta a corrigir os dados.

HTTP 503 | A mensagem informa indisponibilidade.

HTTP 504 | A mensagem informa indisponibilidade.

Outros sete testes conferem o sucesso HTTP 201, falha de rede, HTTP 400, 409, 500 e 502, além de respostas fora do contrato.

Resultado da execução

Data da execução: 18/10/2026 às 09:18:58 (Fortaleza)

Ambiente: Node v22.23.2 | Node Test Runner

Comando: npm run test:evidencias, dentro de frontend

Estado final: 14 aprovados; 0 falhas; 0 cancelados; 0 ignorados; código de saída 0.

Registro completo: docs/pi3/evidencias/parte1/testes.tap e resultado.json

Parte da suíte | Quantidade | Resultado

UsuarioServiceTest | 7 | Aprovados

Regressões do cadastro | 7 | Aprovados

Os 14 testes do cadastro passaram na versão isolada da Parte 1. O build dessa versão também foi concluído sem erro. As classes de catálogo e sacola, com seus 20 testes, são acrescentadas somente na Parte 2.

Evidência disponível

A imagem parte1-testes-completo.png mostra os 14 cenários executados nesta etapa. A saída TAP e o resumo JSON estão separados na pasta evidencias/parte1. O registro da execução pertence ao escopo de cadastro desta versão.

Registro da versão

Repositório: https://github.com/Residencia-Tecnologica-2026-2/bazar-solidario

Branch local: entrega/02-testes-unitarios-parte-1

Endereço previsto: https://github.com/Residencia-Tecnologica-2026-2/bazar-solidario/tree/entrega/02-testes-unitarios-parte-1

Classe implementada: frontend/src/services/usuarios.ts

Testes da versão: frontend/tests/UsuarioService.test.ts
frontend/tests/usuarios.test.ts

Evidências: docs/pi3/evidencias/testes.tap
docs/pi3/evidencias/resultado.json

Conclusão

A primeira etapa concentra a verificação no cadastro. Os 14 testes foram aprovados e o build da versão foi concluído sem erro. A validação dos campos, a confirmação de senha e o tratamento das respostas HTTP estão implementados na classe usada pelo formulário.

Continuidade do trabalho

A segunda etapa mantém os testes de cadastro e acrescenta as classes de catálogo e sacola, com 20 novos testes. Essa ampliação está registrada em uma branch própria, preservando a consulta à implementação inicial.

Parte 2 preparada: https://github.com/Residencia-Tecnologica-2026-2/bazar-solidario/tree/entrega/03-testes-unitarios-parte-2

O cadastro foi testado com respostas HTTP simuladas. A verificação apresentada não inclui autenticação ou persistência no banco.
