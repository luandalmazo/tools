# Testbed para Proxies de Gestão de Identidades: Uma Análise Prática do Shibboleth, SimpleSAMLphp e SATOSA

Este repositório apresenta um conjunto de artefatos desenvolvidos para viabilizar e avaliar o uso de proxies de autenticação — como Shibboleth, Satosa e SimpleSAMLphp — em diferentes cenários, como instituições de ensino, sistemas de gestão e laboratórios científicos. O estudo é baseado no artigo _“Estudo sobre proxies de autenticação aplicados a diferentes contextos com ambiente de experimentação baseado no Keycloak”_.

# Estrutura do readme.md

Este repositório está organizado com os seguintes componentes:

- Código-fonte dos três proxies: Shibboleth, Satosa e SimpleSAMLphp.
- Ambiente de experimentação com Keycloak, acessível via navegador.
- Instruções completas de configuração no arquivo [`CONFIG.md`](CONFIG.md).
- Scripts de automação baseados em Docker para facilitar a reprodução dos testes.

# Selos Considerados

Os selos considerados são: **Disponíveis**, **Funcionais** e **Reproduzíveis**.

# Informações básicas

O repositório contém três artefatos principais:

- Proxy Shibboleth
- Proxy Satosa
- Proxy SimpleSAMLphp

Estes artefatos estão disponíveis em um ambiente online de degustação, acessível via:

🔗 https://keycloak.gidlab.rnp.br/realms/SBRC2025/account/#/

O código-fonte está hospedado no GitHub:

🔗 https://github.com/luandalmazo/tools

Requisitos básicos para replicação dos experimentos:

- Navegador moderno (para modo degustação)
- Docker instalado (para execução local)
- Git instalado

# Dependências

As seguintes dependências são necessárias:

- **Docker**: para execução local dos proxies (ao menos um dos artefatos está dockerizado).
- **Git**: para clonar o repositório com os artefatos e scripts.
- Não há dependências adicionais além das que já estão descritas e automatizadas no repositório.

# Preocupações com segurança

Todo o ambiente de experimentação é **fictício**, sem dados sensíveis ou sistemas reais. Isso elimina qualquer risco de segurança para os avaliadores.

As **credenciais de acesso** estão documentadas no  [`CONFIG.md`](CONFIG.md) do repositório e são de uso público, garantindo fácil acesso e segurança.

# Instalação

## Modo degustação (sem instalação)

1. Acesse: https://keycloak.gidlab.rnp.br/realms/SBRC2025/account/#/
2. Utilize as credenciais fornecidas no repositório GitHub.
3. Explore diretamente os proxies via navegador.

## Modo local (com Docker)

1. Clone o repositório:
   ```bash
   git clone https://github.com/luandalmazo/tools
   cd tools
   ```
2. Siga o passo a passo disponível no [`CONFIG.md`](CONFIG.md) do repositório.
3. Execute os containers Docker conforme instruções.

# Teste mínimo

Um teste mínimo pode ser executado via navegador:

1. Acesse o menu degustação.
2. Selecione um dos proxies (Shibboleth, Satosa ou SimpleSAMLphp).
3. Realize o processo de login com as credenciais fornecidas.
4. Observe o redirecionamento e a autenticação via Keycloak.

Esse teste garante que o proxy esteja funcional e integrado corretamente ao provedor de identidade.

# Experimentos

Para validar as propostas do artigo, foi criado um ambiente completo com:

- Provedor de Serviço (SP)
- Proxy (Shibboleth, Satosa ou SimpleSAMLphp)
- Provedor de Identidade (IdP)

## Etapas de configuração

1. Conectar o SP ao Proxy (o SP enxerga o proxy como um IdP).
2. Conectar o Proxy ao IdP (o IdP enxerga o proxy como um SP).
3. Realizar o fluxo de autenticação ponta a ponta.
4. Verificar sucesso da autenticação via Keycloak.

Todos os arquivos de configuração e comandos necessários estão no repositório GitHub.

## Reivindicação #1

A principal proposta dos artefatos é viabilizar todo o processo de autenticação e autorização entre SPs e IdPs via **proxy de autenticação**, o que traz:

- Maior **flexibilidade** na gestão de identidades.
- **Interoperabilidade** entre diferentes sistemas e protocolos.
- Possibilidade de **manipulação de atributos**, transformação de protocolos e aplicação de políticas específicas.
- **Abstração** da complexidade de autenticação, centralizando a gestão.

### Resultado esperado

- SPs conectam-se apenas ao proxy, que intermedia o processo.
- O proxy lida com transformações necessárias.
- Autenticação é realizada com sucesso e atributos manipulados conforme regras configuradas.

