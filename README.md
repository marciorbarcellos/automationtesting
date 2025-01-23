# Automação de Testes com Cypress

> Este repositório contém uma abordagem completa sobre automação de testes utilizando o Cypress. Conceitos práticos e dicas úteis para criar testes end-to-end divididos em categorias de testes de validação, de funcionalidade, de Interface do Usuário (UI), de segurança, de fluxos alternativos, de performance e de Internacionalização.

![Automation Testing with Cypress](https://github.com/user-attachments/assets/ee8b9bce-f927-4676-b79d-15aae3638dad)
<a name="inicio"><a/>
<br/>

## Estrutura do Repositório

- **[01 - Introdução](#introducao):** Apresentação do projeto e contexto.
- **[02 - O que é Cypress?](#cypress):** Explicação sobre o Cypress e seu funcionamento.
- **[03 - Principais Vantagens](#vantagem):** Benefícios de usar Cypress.
- **[04 - Objetivo](#objetivo):** Propósitos deste repositório.
- **[05 - Para quem é este Projeto?](#projeto):** Público-alvo do projeto.
- **[06 - Pré-requisitos](#prerequisito):** Ferramentas e conhecimentos necessários.
- **[07 - Principais Comandos do Cypress](#comandos):** Lista e explicação de comandos importantes.
- **[08 - Inspecionando Elementos](#inspecionar):** Uso do inspetor do Cypress.
- **[09 - Testes de Validação de Campos](#validarcampos):** Como validar campos de entrada.
- **[10 - Testes de Funcionalidade](#funcionalidades):** Testes para ações de login e afins.
- **[11 - Testes de Interface do Usuário (UI)](#interface):** Garantir consistência da interface.
- **[12 - Testes de Segurança](#seguranca):** Validação contra vulnerabilidades.
- **[13 - Testes de Fluxos Alternativos](#fluxos):** Testes para cenários menos comuns.
- **[14 - Testes de Performance](#performance):** Avaliação do desempenho do sistema.
- **[15 - Testes de Internacionalização](#internacionalizacao):** Validação de idiomas e formatos regionais.
- **[16 - Código Cypress](#codigo):** Código implementado no projeto.

<br/>

## 1. Introdução <a name="introducao"><a/>

Bem-vindo ao repositório de automação de testes com Cypress! 

Este projeto foi desenvolvido para demonstrar, implementar e facilitar a automação de testes end-to-end (E2E), testes de integração e testes de interface para aplicações web utilizando o Cypress, uma das ferramentas mais populares e poderosas do mercado para automação de testes. 
**[Início](#inicio):**
<br/>

## 2. O que é o Cypress?  <a name="cypress"><a/>

O Cypress é um framework moderno de automação de testes que foi projetado especificamente para desenvolvedores e testadores. Ele oferece uma abordagem única e inovadora para testar aplicativos web, proporcionando uma experiência simplificada e eficiente. Com o Cypress, você pode escrever, depurar e executar testes de forma mais rápida e confiável, graças à sua arquitetura baseada em JavaScript e à integração nativa com o navegador. 
**[Início](#inicio):**
<br/>

## 3. Principais Vantagens do Cypress  <a name="vantagem"><a/>

- Facilidade de uso: Configuração inicial rápida e simples. 

- Execução em tempo real: Monitore seus testes em execução diretamente no navegador. 

- Depuração avançada: Acesse capturas de tela, logs detalhados e inspeções de elementos durante o teste. 

- API intuitiva: Escrita de testes clara e legível, com uma sintaxe moderna baseada em JavaScript. 

- Testes abrangentes: Suporte para testes de interface, integração e E2E. 

- Execução rápida: Graças à execução no mesmo loop de eventos do navegador. 
**[Início](#inicio):**
<br/>

## 4. Objetivo deste Repositório  <a name="objetivo"><a/>

Este repositório foi criado com os seguintes objetivos: 


- Educar: Fornecer exemplos práticos e bem documentados sobre como usar o Cypress para testar diferentes cenários em aplicações web. 

- Facilitar a adoção: Ajudar desenvolvedores e testadores a integrarem o Cypress aos seus fluxos de trabalho de desenvolvimento. 

- Melhorar a qualidade: Demonstrar como os testes automatizados podem ajudar a garantir a qualidade e a estabilidade de aplicações, reduzindo erros e falhas. 
**[Início](#inicio):**
<br/>

## 5. Para quem é este projeto?  <a name="projeto"><a/>

Este repositório é ideal para:

- Desenvolvedores que desejam integrar testes automatizados em seus projetos. 

- Testadores que querem aprender ou aprofundar seus conhecimentos em automação com Cypress. 

- Equipes que buscam melhorar a cobertura de testes e a qualidade do software. 


Se você é novo no Cypress ou está buscando aprimorar seus conhecimentos, este repositório será um excelente ponto de partida. Confira a documentação fornecida e experimente os exemplos incluídos para entender como o Cypress pode ser integrado e utilizado em diferentes cenários de teste. 
**[Início](#inicio):**
<br/>

## 6. Pré-requisitos  <a name="prerequisito"><a/>


- NodeJS 

- Visual Studio Code (ou um editor de texto que preferir) 

- Conhecimento mínimo em alguma linguagem de programação (utilizaremos JavaScript em nossos testes) 
**[Início](#inicio):**
<br/>

## 7. Principais comandos do Cypress  <a name="comandos"><a/>

- cy.visit(url): Visita uma URL específica da aplicação. 

- cy.get(selector): Seleciona um elemento do DOM usando um seletor CSS. 

- cy.contains(text): Seleciona o primeiro elemento que contém o texto especificado. 

- cy.click(): Clica no elemento selecionado. 

- cy.type(text): Digita o texto especificado no elemento selecionado (geralmente campos de entrada). 

- cy.submit(): Submete um formulário. 

- cy.reload(): Recarrega a página atual. 

- cy.url(): Obtém a URL atual da página. 

- cy.title(): Obtém o título da página atual. 

- cy.viewport(width, height): Define a largura e a altura da janela do navegador. 

- should(assertion, value): Esta função é usada para fazer asserções sobre o estado do elemento ou valor atualmente encadeado. 

- and(assertion, value): É usada para encadear várias asserções em um único comando. 

- expect(actual).to.have.something(expected): É usada para fazer asserções fora do contexto de um comando Cypress encadeado. 
**[Início](#inicio):**
<br/>

## 8. Inspecionando elementos  <a name="inspecionar"><a/>


O Inspector do Cypress é uma ferramenta interativa que ajuda a desenvolver, depurar e entender os testes end-to-end (E2E) enquanto são executados no Cypress Test Runner. Ele permite que você inspecione elementos na aplicação testada, veja o estado do DOM em diferentes pontos do teste e rastreie ações e eventos do Cypress. 

Para utilizar é bem simples: Basta clicar no botão de inspecionar, clicar sobre o elemento que deseja identificar, e em seguida copiar o path apresentado, como mostrado no GIF a seguir: 

![Inspecionar elementos](https://github.com/user-attachments/assets/000cdff5-c1f2-4b04-8cc8-c521b4949d7a)

Após copiar o path, basta colocar em seu código de acordo com as ações que deseja executar.  
**[Início](#inicio):**
<br/>

## 9. Testes de Validação de Campos  <a name="validarcampos"><a/>

- Verificar se os campos de e-mail e senha são obrigatórios. 

- Garantir que o formulário exiba uma mensagem de erro apropriada se os campos estiverem vazios ao enviar. 

- Validação de formato de e-mail: 

- Testar entradas inválidas como "email.com", "user@com", "12345". 

- Garantir que apenas e-mails válidos sejam aceitos. 

- Validação do campo de senha: 

- Testar com senha em branco e verificar se a mensagem de erro aparece. 

- Verificar requisitos mínimos de senha (como tamanho mínimo ou caracteres especiais, se aplicável). 
**[Início](#inicio):**
<br/>

## 10. Testes de Funcionalidade  <a name="funcionalidades"><a/>

- Login com credenciais válidas: Garantir que o usuário é autenticado com sucesso ao fornecer e-mail e senha válidos. 

- Login com credenciais inválidas: Testar com e-mail inválido e senha inválida e verificar se a mensagem de erro correta aparece. 

- Lidar com conta bloqueada: Verificar se o sistema exibe uma mensagem apropriada para contas desativadas ou bloqueadas. 

- Exceder tentativas de login: Garantir que o sistema bloqueie a conta ou solicite verificação adicional após várias tentativas fracassadas. 

- Esqueci minha senha: Verificar se o link ou botão de "Esqueci minha senha" redireciona corretamente. Testar o envio do e-mail de redefinição de senha. 

- Logout:  Garantir que o botão ou link de logout funcione corretamente e redirecione para a tela de login.
**[Início](#inicio):**
<br/>

## 11. Testes de Interface do Usuário (UI)  <a name="interface"><a/>


- Layout e elementos visíveis: Garantir que todos os elementos da tela de login (campos, botões, links) sejam exibidos corretamente. 

- Estado do botão de login:  Verificar se o botão de login permanece desabilitado até que todos os campos necessários sejam preenchidos corretamente. 

- Mensagens de erro:  Garantir que as mensagens de erro desaparecem quando o campo é corrigido. 

- Responsividade:  Testar a tela de login em diferentes tamanhos de dispositivo (desktop, tablet, celular). 
**[Início](#inicio):**
<br/>

## 12. Testes de Segurança  <a name="seguranca"><a/>

- Prevenção de SQL Injection:  Testar entradas maliciosas como "' OR '1'='1" ou comandos SQL similares. 

- Proteção contra XSS: Testar inputs com scripts como <script>alert("XSS")</script>. 

- Senha mascarada: Garantir que o campo de senha mostre apenas asteriscos ou pontos. 

- Exibição de informações:  Garantir que mensagens de erro não revelem detalhes sobre credenciais inválidas (e.g., “usuário inexistente” vs. “senha incorreta”). 

- Prevenção de força bruta: Verificar se há limite para tentativas de login e se o sistema bloqueia acessos excessivos. 

- Sessão segura: Garantir que dados sensíveis, como a senha, não sejam exibidos no console ou armazenados localmente no navegador. 
**[Início](#inicio):**
<br/>
 
## 13. Testes de Fluxos Alternativos  <a name="fluxos"><a/>

- Lembrar-me: Testar se a opção "Lembrar-me" mantém o login mesmo após o fechamento do navegador. 

- Login com provedores externos (se aplicável):  Testar autenticação por provedores como Google, Facebook, etc. 

- Redirecionamentos: Garantir que, após o login, o usuário seja redirecionado para a página correta. Verificar se um usuário não autenticado acessando uma URL protegida é redirecionado para a tela de login. 
**[Início](#inicio):**
<br/>
 
## 14. Testes de Performance  <a name="performance"><a/>

- Tempo de resposta: Garantir que a tela de login carregue em um tempo aceitável. 

- Latência do servidor:  Testar o comportamento do sistema ao simular conexões lentas. 

- Manutenção sob carga: Simular múltiplos usuários tentando fazer login simultaneamente. 
**[Início](#inicio):**
<br/>

## 15. Testes de Internacionalização (se aplicável)  <a name="internacionalizacao"><a/>

- Idiomas suportados:  Testar o funcionamento da tela de login em diferentes idiomas.

- Formatos regionais:  Verificar se mensagens e formatação de datas (se aplicável) respeitam o idioma/país. 
**[Início](#inicio):**
<br/>

## 16. Código Cypress para validação dos critérios de teste  <a name="codigo"><a/>

Por fim, o Cypress oferece uma experiência simplificada e eficiente, destacando suas principais vantagens como configuração simples, execução em tempo real, depuração avançada e uma API intuitiva. Nestes tópicos, verificamos os seguintes pontos identificados nas seções do código desenvolvido para o teste de automação e suas principais categorias:

#### Principais Comandos utilizados

- Configuração inicial (beforeEach): Define que a página será carregada antes de cada teste.
- Testes de campos obrigatórios: Usa os atributos required do HTML e valida com o seletor :invalid.
- Mensagens de erro: Testa a presença das mensagens nativas do navegador usando validationMessage.
- Validação de formato de e-mail: Envia entradas inválidas e verifica erros usando o seletor :invalid.
- Senhas inválidas: Testa com valores vazios e curtos, conforme o requisito de validação.

#### Principais Categorias de Testes

- Validação de Campos: Verificação de obrigatoriedade, formatos corretos (e.g., e-mails), e mensagens de erro apropriadas.
- Funcionalidade: Testes de login com credenciais válidas e inválidas, esquecimento de senha, e logout.
- Interface do Usuário (UI): Garantia de layout correto, responsividade, e feedback visual apropriado.
- Segurança: Prevenção contra SQL Injection, ataques XSS, e limitações contra força bruta.
- Fluxos Alternativos: Testes com opções como "Lembrar-me" e provedores externos.
- Performance: Avaliação de tempos de resposta e comportamentos sob carga.
- Internacionalização: Suporte a múltiplos idiomas e formatações regionais.
**[Início](#inicio):**
<br/>

![Cypress](https://github.com/user-attachments/assets/d7de2213-c43e-4b7a-bce2-3c963ffcbda6)
<br/>
**[Início](#inicio):**
<br/>

## Como Usar

1. Clone o repositório: `git clone https://github.com/seu-usuario/Automacao-de-Testes-com-Cypress.git`
2. Navegue até o tópico desejado e siga as instruções no README correspondente.
**[Início](#inicio):**
<br/>
---

Explore cada seção para mais detalhes e exemplos práticos sobre automação de testes com Cypress.
