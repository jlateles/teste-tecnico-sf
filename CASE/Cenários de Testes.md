## **QA responsável: Júlia Teles**
> Objetivo: permitir que o usuário calcule o valor e o prazo de entrega de um envio com base nas informações fornecidas (como CEP de origem, CEP de destino, peso, dimensões, tipo de serviço, etc.)

## 📌 1. Identificação
-  Nome do Projeto: Super frete - Sistema de Calcular frete pelo Correios
-  Versão Avaliada: Demo pública
-  Ambiente de Testes: https://web.superfrete.com/#/calcular-correios
-  Tipo de Teste: Testes Funcionais Manuais
-  Data do Documento: 11/11/2025

🧩 2. Escopo

**Incluído:**
  - Sidebar
  - Tela `Calcular`
  - Funcionalidade `Calcular frete`
  - Campos e botões

**Excluído:**
  - Testes de integração com sistemas externos (não disponíveis na demo)
  - Testes de performance ou carga
--- 

### Cenários de Testes

**1. Preenchimento básico**

| ID     | Cenário                                       | Descrição / Objetivo                                               | Resultado Esperado                                               |
| ------ | --------------------------------------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------- |
| CT-001 | Calcular frete com dados válidos              | Inserir CEP de origem e destino válidos, peso e dimensões corretas | Sistema exibe valor e prazo de entrega                           |
| CT-002 | Calcular frete apenas com campos obrigatórios | Preencher somente os campos mínimos necessários                    | Cálculo é realizado corretamente                                 |
| CT-003 | Não preencher nenhum campo                    | Clicar em “Calcular” sem inserir dados                             | Sistema exibe mensagem informando que os campos são obrigatórios |

**2. Validação de campos**

| ID     | Cenário                                                                  | Descrição / Objetivo                         | Resultado Esperado                           |
| ------ | ------------------------------------------------------------------------ | -------------------------------------------- | -------------------------------------------- |
| CT-004 | Inserir CEP de origem inválido (menos de 8 dígitos)                      | Testar validação de formato de CEP           | Mensagem de erro “CEP inválido”              |
| CT-005 | Inserir CEP de destino inexistente                                       | Testar comportamento com CEP não reconhecido | Exibir mensagem de erro adequada             |
| CT-006 | Inserir caracteres não numéricos no campo CEP                            | Ex: letras, símbolos                         | Bloquear caracteres inválidos ou exibir mensagem de erro |
| CT-007 | Inserir peso em formato inválido (ex: letras ou símbolo negativo)        | Validar campo de peso                        | Bloquear caracteres inválidos ou exibir mensagem “Peso inválido”   |
| CT-008 | Inserir valores de dimensão fora dos limites aceitos                      | Validar regra de valor mínimo               | Exibir erro ou impedir cálculo               |
| CT-009 | Copiar e colar CEP com hífen (ex: 24130-080)                              | Verificar formatação aceita                 | Sistema deve aceitar e interpretar corretamente |

**3. Usabilidade e interface**

| ID     | Cenário                                  | Descrição / Objetivo                   | Resultado Esperado                  |
| ------ | ---------------------------------------- | -------------------------------------- | ----------------------------------- |
| CT-009 | Verificar alinhamento e nomes dos campos | Garantir clareza na interface          | Campos e labels legíveis e corretos |
| CT-010 | Verificar responsividade da página       | Redimensionar tela / testar  mobile    | Página se ajusta corretamente       |
| CT-011 | Testar botão “Limpar”                     | Verificar se limpa todos os campos     | Campos voltam ao estado inicial     |





