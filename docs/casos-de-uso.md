# 📋 Casos de Uso — Messejana Conecta

Este documento apresenta os principais casos de uso previstos para a plataforma **Messejana Conecta**, descrevendo as interações entre os diferentes tipos de usuários e o sistema.

---

## 👥 Atores do sistema

O sistema possui quatro tipos principais de atores:

### 👤 Visitante

Pessoa que acessa a plataforma sem possuir uma conta.

Pode consultar informações públicas sobre estabelecimentos e eventos.

### 👤 Usuário

Pessoa que possui uma conta cadastrada na plataforma.

Além das funcionalidades disponíveis ao visitante, pode interagir com o conteúdo.

### 🏪 Comerciante

Usuário responsável por um estabelecimento comercial cadastrado na plataforma.

Possui funcionalidades específicas para gerenciamento do estabelecimento.

### 🛡️ Administrador

Responsável pelo gerenciamento e moderação da plataforma.

Possui permissões para administrar usuários e conteúdos.

---

# 🔎 UC01 — Pesquisar estabelecimento

**Ator principal:** Visitante, Usuário ou Comerciante

**Objetivo:** Encontrar um estabelecimento através de seu nome ou informações relacionadas.

### Fluxo principal

1. O usuário acessa a plataforma.
2. O usuário localiza a barra de pesquisa.
3. O usuário informa um termo.
4. O sistema processa a pesquisa.
5. O sistema apresenta os resultados correspondentes.

### Resultado esperado

O usuário visualiza uma lista de estabelecimentos relacionados à pesquisa.

---

# 🏪 UC02 — Visualizar estabelecimento

**Ator principal:** Visitante, Usuário ou Comerciante

**Objetivo:** Consultar informações detalhadas sobre um estabelecimento.

### Fluxo principal

1. O usuário realiza uma pesquisa ou acessa uma categoria.
2. O sistema apresenta os estabelecimentos disponíveis.
3. O usuário seleciona um estabelecimento.
4. O sistema apresenta a página do estabelecimento.

### Informações apresentadas

- Nome;
- Descrição;
- Categoria;
- Endereço;
- Telefone;
- Horário de funcionamento;
- Redes sociais;
- Faixa de preço;
- Avaliação;
- Localização.

---

# 🏷️ UC03 — Filtrar estabelecimentos

**Ator principal:** Visitante, Usuário ou Comerciante

**Objetivo:** Refinar os resultados apresentados pelo sistema.

### Fluxo principal

1. O usuário acessa a área "Explorar".
2. O sistema apresenta os estabelecimentos.
3. O usuário seleciona uma categoria ou filtro.
4. O sistema atualiza os resultados.
5. O usuário visualiza apenas os estabelecimentos correspondentes aos filtros selecionados.

### Exemplos de filtros

- Gastronomia;
- Compras;
- Serviços;
- Beleza;
- Saúde;
- Lazer.

---

# 🎉 UC04 — Visualizar evento

**Ator principal:** Visitante, Usuário ou Comerciante

**Objetivo:** Consultar informações sobre eventos divulgados na plataforma.

### Fluxo principal

1. O usuário acessa a área de eventos.
2. O sistema apresenta os eventos disponíveis.
3. O usuário seleciona um evento.
4. O sistema apresenta os detalhes do evento.

### Informações apresentadas

- Nome;
- Imagem;
- Descrição;
- Data;
- Horário;
- Local;
- Categoria;
- Informações adicionais.

---

# 👤 UC05 — Criar conta

**Ator principal:** Visitante

**Objetivo:** Criar uma conta para acessar funcionalidades exclusivas.

### Fluxo principal

1. O visitante seleciona "Criar conta".
2. O sistema apresenta o formulário de cadastro.
3. O visitante informa seus dados.
4. O sistema valida as informações.
5. O sistema cria a conta.
6. O sistema confirma o cadastro.

### Dados iniciais

- Nome;
- E-mail;
- Senha.

### Resultado esperado

O visitante passa a possuir uma conta de usuário.

---

# 🔐 UC06 — Realizar login

**Ator principal:** Usuário ou Comerciante

**Objetivo:** Acessar sua conta.

### Fluxo principal

1. O usuário acessa a página de login.
2. Informa e-mail e senha.
3. O sistema verifica as credenciais.
4. O sistema autentica o usuário.
5. O usuário é direcionado para sua área correspondente.

### Exceção

Caso as credenciais estejam incorretas, o sistema deverá informar que os dados fornecidos são inválidos.

---

# 📢 UC07 — Enviar evento

**Ator principal:** Usuário

**Objetivo:** Permitir que membros da comunidade divulguem eventos.

### Pré-condição

O usuário deverá estar autenticado.

### Fluxo principal

1. O usuário seleciona "Divulgar evento".
2. O sistema apresenta o formulário.
3. O usuário preenche as informações.
4. O usuário envia o formulário.
5. O sistema valida os dados.
6. O evento recebe o status "Pendente".
7. O sistema informa ao usuário que o evento foi enviado para análise.

### Status possíveis

```text
Pendente
Aprovado
Rejeitado
```

### Resultado esperado

Após aprovação administrativa, o evento ficará disponível publicamente na plataforma.

---

# 🏪 UC08 — Cadastrar estabelecimento

**Ator principal:** Comerciante

**Objetivo:** Permitir que um comerciante cadastre seu estabelecimento na plataforma.

### Pré-condição

O comerciante deverá possuir uma conta.

### Fluxo principal

1. O comerciante acessa sua área administrativa.
2. Seleciona "Cadastrar estabelecimento".
3. Preenche as informações solicitadas.
4. Envia o cadastro.
5. O sistema valida os dados.
6. O estabelecimento recebe o status "Pendente".
7. O administrador analisa o cadastro.
8. O estabelecimento é aprovado ou rejeitado.

### Informações do estabelecimento

- Nome;
- Descrição;
- Categoria;
- Endereço;
- Telefone;
- Horário;
- Redes sociais;
- Faixa de preço;
- Imagens.

---

# ⭐ UC09 — Avaliar estabelecimento

**Ator principal:** Usuário

**Objetivo:** Permitir que usuários compartilhem sua experiência com estabelecimentos.

### Pré-condição

O usuário deverá estar autenticado.

### Fluxo principal

1. O usuário acessa um estabelecimento.
2. Seleciona a opção "Avaliar".
3. Informa uma nota.
4. Opcionalmente adiciona um comentário.
5. Envia a avaliação.
6. O sistema registra a avaliação.
7. O sistema atualiza a média do estabelecimento.

### Regra

Cada usuário poderá possuir apenas uma avaliação por estabelecimento, podendo editá-la posteriormente.

---

# ❤️ UC10 — Favoritar estabelecimento

**Ator principal:** Usuário

**Objetivo:** Permitir que usuários salvem estabelecimentos para consultar posteriormente.

### Pré-condição

O usuário deverá estar autenticado.

### Fluxo principal

1. O usuário acessa um estabelecimento.
2. Seleciona o botão de favorito.
3. O sistema registra o estabelecimento na lista de favoritos.
4. O estabelecimento passa a aparecer na área "Meus favoritos".

O usuário poderá remover o estabelecimento dos favoritos posteriormente.

---

# 🛡️ UC11 — Moderar conteúdo

**Ator principal:** Administrador

**Objetivo:** Analisar conteúdos enviados pelos usuários e comerciantes.

### Conteúdos que podem ser moderados

- Eventos;
- Estabelecimentos;
- Avaliações;
- Outros conteúdos enviados pela comunidade.

### Fluxo principal

1. O administrador acessa o painel administrativo.
2. O sistema apresenta conteúdos pendentes.
3. O administrador seleciona um conteúdo.
4. Analisa as informações.
5. Escolhe uma ação.
6. O sistema atualiza o status do conteúdo.

### Ações possíveis

```text
Aprovar
Rejeitar
Solicitar alteração
Remover
```

---

# 🗺️ UC12 — Visualizar mapa

**Ator principal:** Visitante, Usuário ou Comerciante

**Objetivo:** Visualizar a localização de estabelecimentos e eventos.

### Fluxo principal

1. O usuário acessa a área "Mapa".
2. O sistema apresenta o mapa.
3. O sistema apresenta os pontos cadastrados.
4. O usuário seleciona um ponto.
5. O sistema apresenta informações resumidas.
6. O usuário poderá acessar a página completa do estabelecimento ou evento.

---

# 📊 Resumo dos casos de uso

| Código | Caso de uso | Ator principal |
|---|---|---|
| UC01 | Pesquisar estabelecimento | Visitante / Usuário |
| UC02 | Visualizar estabelecimento | Visitante / Usuário |
| UC03 | Filtrar estabelecimentos | Visitante / Usuário |
| UC04 | Visualizar evento | Visitante / Usuário |
| UC05 | Criar conta | Visitante |
| UC06 | Realizar login | Usuário / Comerciante |
| UC07 | Enviar evento | Usuário |
| UC08 | Cadastrar estabelecimento | Comerciante |
| UC09 | Avaliar estabelecimento | Usuário |
| UC10 | Favoritar estabelecimento | Usuário |
| UC11 | Moderar conteúdo | Administrador |
| UC12 | Visualizar mapa | Visitante / Usuário |

---

## 📌 Observação

Os casos de uso apresentados representam o escopo planejado do sistema e poderão ser modificados durante o desenvolvimento conforme novas necessidades sejam identificadas.

O projeto será desenvolvido de forma incremental, priorizando inicialmente as funcionalidades essenciais do MVP.
