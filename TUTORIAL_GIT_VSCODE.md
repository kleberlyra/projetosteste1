<h1>Título da versão remota</h1>
>>>>>>> feature/outra-branch (Incoming Change)
```

3. **Opções no VS Code:**
   - **Accept Current Change** - mantém sua versão
   - **Accept Incoming Change** - usa a versão do outro dev
   - **Accept Both Changes** - mantém ambas
   - **Compare Changes** - vê diferenças lado a lado

4. **Após resolver:**
   - Salve o arquivo
   - Adicione: `git add arquivo-resolvido.html`
   - Commite: `git commit -m "fix: resolve conflito de merge"`

### Exemplo Prático de Conflito

**Desenvolvedor 1 alterou:**
```html
<title>PetClassificados - Adote seu Amigo</title>
```

**Desenvolvedor 2 alterou:**
```html
<title>PetClassificados - Encontre seu Pet</title>
```

**Conflito gerado:**
```html
<<<<<<< HEAD
<title>PetClassificados - Adote seu Amigo</title>
=======
<title>PetClassificados - Encontre seu Pet</title>
>>>>>>> feature/outro-dev
```

**Resolução (escolher um ou combinar):**
```html
<title>PetClassificados - Adote ou Encontre seu Pet</title>
```

---

## 🔍 Visualizando Branches e Histórico

### Extensão GitLens (Recomendada)

1. Instale a extensão **GitLens** no VS Code:
   - `Ctrl + Shift + X` para abrir Extensions
   - Busque: "GitLens"
   - Clique em **Install**

2. **Recursos do GitLens:**
   - Ver quem modificou cada linha (blame)
   - Histórico de commits visual
   - Comparar branches facilmente
   - Ver detalhes do commit ao passar o mouse

### Extensão Git Graph (Visual)

1. Instale **Git Graph**:
   - `Ctrl + Shift + X` para abrir Extensions
   - Busque: "Git Graph"
   - Clique em **Install**

2. **Usar Git Graph:**
   - Clique no ícone do Source Control
   - Clique em "View Git Graph" no topo
   - Verá um gráfico visual das branches

---

## ⚡ Atalhos Úteis do VS Code

### Atalhos de Teclado

| Ação | Windows/Linux | Mac |
|------|---------------|-----|
| Abrir Source Control | `Ctrl + Shift + G` | `Cmd + Shift + G` |
| Abrir Terminal | `Ctrl + '` | `Cmd + '` |
| Command Palette | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| Commit | `Ctrl + Enter` | `Cmd + Enter` |
| Ver diff do arquivo | Clique no arquivo | Clique no arquivo |

### Comandos Úteis no Terminal

```bash
# Ver branches
git branch -a

# Ver branch atual
git branch --show-current

# Deletar branch local
git branch -d feature/nome-branch

# Ver log bonito
git log --oneline --graph --all

# Ver diferenças
git diff
git diff HEAD~1  # diferença do último commit

# Desfazer mudanças não commitadas
git checkout -- arquivo.html

# Desfazer último commit (mantém mudanças)
git reset --soft HEAD~1

# Ver arquivos modificados
git status -s
```

---

## 🎯 Cenário Prático Completo

### Situação: Dois Desenvolvedores Trabalhando Juntos

**Desenvolvedor 1: João (index.html)**

```bash
# Segunda-feira - 9h
git checkout main
git pull origin main
git checkout -b feature/filtros-avancados

# Trabalha no index.html
# Adiciona filtros por idade, raça, tamanho

git add index.html
git commit -m "feat: adiciona filtros avançados de busca"
git push -u origin feature/filtros-avancados

# Abre Pull Request no GitHub
# Aguarda revisão
```

**Desenvolvedor 2: Maria (detalhes.html)**

```bash
# Segunda-feira - 9h
git checkout main
git pull origin main
git checkout -b feature/sistema-favoritos

# Trabalha no detalhes.html
# Adiciona botão de favoritar

git add detalhes.html
git commit -m "feat: adiciona sistema de favoritos"
git push -u origin feature/sistema-favoritos

# Abre Pull Request no GitHub
# Aguarda revisão
```

**Aprovação e Merge**

```bash
# Pull Request do João é aprovado e mergeado no main

# Maria precisa atualizar sua branch com as mudanças do João
git checkout main
git pull origin main
git checkout feature/sistema-favoritos
git merge main  # traz mudanças do João

# Se houver conflitos, resolve no VS Code
# Continua trabalhando

git push  # envia atualização
```

---

## 🛡️ Boas Práticas

### ✅ Fazer

- Sempre criar uma branch para cada funcionalidade
- Fazer commits pequenos e frequentes
- Usar mensagens de commit descritivas
- Fazer pull antes de começar a trabalhar
- Testar antes de fazer commit
- Revisar mudanças antes de commitar (ver diff)

### ❌ Evitar

- Trabalhar diretamente na branch main
- Commits grandes com muitas mudanças
- Mensagens vagas: "fix", "update"
- Esquecer de fazer pull antes de começar
- Commitar arquivos temporários ou node_modules
- Fazer push sem testar

---

## 🚨 Comandos de Emergência

### Desfazer mudanças não commitadas

```bash
# Desfazer mudanças em um arquivo específico
git checkout -- index.html

# Desfazer todas as mudanças não commitadas
git reset --hard HEAD
```

### Desfazer último commit (mantendo mudanças)

```bash
git reset --soft HEAD~1
```

### Voltar para um commit anterior

```bash
# Ver histórico
git log --oneline

# Voltar para um commit específico
git checkout abc1234  # substitua pelo hash do commit
```

### Criar branch a partir de commit anterior

```bash
git checkout -b feature/recuperar-codigo abc1234
```

---

## 📚 Recursos Adicionais

### Extensões Recomendadas para VS Code

1. **GitLens** - Supercharge Git
2. **Git Graph** - Visualização de branches
3. **Git History** - Ver histórico de arquivos
4. **GitHub Pull Requests** - Gerenciar PRs no VS Code

### Links Úteis

- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [VS Code Git Documentation](https://code.visualstudio.com/docs/sourcecontrol/overview)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)

---

## 💡 Dicas Finais

1. **Commit frequentemente** - É melhor muitos commits pequenos que um grande
2. **Sempre teste antes de commitar** - Abra o HTML no navegador
3. **Use branches descritivas** - `feature/filtros-busca` é melhor que `teste`
4. **Faça pull regularmente** - Mantenha-se atualizado com o trabalho do time
5. **Resolva conflitos rapidamente** - Não deixe acumular
6. **Comunique-se com o time** - Avise quando for trabalhar em algo

---

**Dúvidas? Consulte este guia ou peça ajuda ao time! 🚀**
=======
# Tutorial: Git e Branches no VS Code (Interface Gráfica)

Guia prático para trabalhar com Git e branches usando apenas a **interface visual** do Visual Studio Code para o projeto PetClassificados.

## 📋 Índice

- [Configuração Inicial](#configuração-inicial)
- [Criando e Gerenciando Branches](#criando-e-gerenciando-branches)
- [Fazendo Commits](#fazendo-commits)
- [Sincronizando com GitHub](#sincronizando-com-github)
- [Resolvendo Conflitos](#resolvendo-conflitos)
- [Visualizando Histórico](#visualizando-histórico)
- [Extensões Essenciais](#extensões-essenciais)

---

## 🚀 Configuração Inicial

### 1. Instalar Git

**Windows:**
1. Acesse: https://git-scm.com/download/win
2. Baixe o instalador
3. Execute e clique em **Next** em todas as etapas (configurações padrão)
4. Reinicie o VS Code após a instalação

**Linux (Ubuntu/Debian):**
1. Abra o terminal do sistema
2. Digite: `sudo apt-get install git`
3. Confirme com sua senha

**Mac:**
1. Abra o Terminal
2. Digite: `git --version`
3. Se não estiver instalado, o macOS oferecerá instalar automaticamente

### 2. Verificar Instalação do Git no VS Code

1. Abra o VS Code
2. Pressione `Ctrl + Shift + P` (Windows/Linux) ou `Cmd + Shift + P` (Mac)
3. Digite: **Git: Version**
4. Pressione `Enter`
5. Verá a versão do Git instalada (ex: "2.40.0")

### 3. Configurar seu Nome e Email

1. Pressione `Ctrl + Shift + P`
2. Digite: **Preferences: Open User Settings**
3. Na busca, digite: **git.user**
4. Configure:
   - **Git: User Name** → Seu nome completo
   - **Git: User Email** → Seu email

**Ou configure pelo Command Palette:**

1. Pressione `Ctrl + Shift + P`
2. Digite: **Git: Config**
3. Selecione **user.name** e digite seu nome
4. Repita para **user.email**

### 4. Abrir a Pasta do Projeto

1. No VS Code, clique em **File → Open Folder**
2. Navegue até a pasta `pet-classificados`
3. Clique em **Selecionar Pasta**

### 5. Inicializar Repositório Git

**Se ainda não iniciou o Git:**

1. Clique no ícone **Source Control** (3º ícone na barra lateral esquerda) - parece três bolinhas conectadas
2. Clique no botão **Initialize Repository**
3. Pronto! O Git foi iniciado na pasta

### 6. Conectar com GitHub

**Método 1: Publicar diretamente pelo VS Code (Recomendado)**

1. No **Source Control**, clique no botão **⋯** (três pontinhos) no topo
2. Selecione **Remote → Add Remote...**
3. Escolha **Add remote from GitHub**
4. VS Code pedirá para fazer login no GitHub (clique em **Allow**)
5. Após logar, clique em **Publish to GitHub**
6. Escolha:
   - **Publish to GitHub public repository** (público)
   - Ou **Publish to GitHub private repository** (privado)
7. Selecione todos os arquivos
8. Clique em **OK**

**Método 2: Conectar a um repositório existente**

1. Crie o repositório no GitHub (https://github.com/new)
2. No VS Code, clique em **Source Control**
3. Clique no botão **⋯** (três pontinhos)
4. Selecione **Remote → Add Remote...**
5. Cole a URL do seu repositório: `https://github.com/seu-usuario/pet-classificados.git`
6. Dê um nome: **origin**
7. Pressione `Enter`

---

## 🌿 Criando e Gerenciando Branches

### 🎯 Método 1: Barra de Status (Mais Fácil e Rápido)

**Localização:** Canto inferior esquerdo do VS Code

#### Ver branch atual:

Olhe no canto inferior esquerdo. Verá algo como:

```
🔄 main
```

#### Criar nova branch:

1. **Clique no nome da branch** (ex: `main`) no canto inferior esquerdo
2. Um menu aparecerá no topo da tela
3. Selecione: **+ Create new branch...**
4. Digite o nome da branch: `feature/filtros-busca`
5. Pressione `Enter`
6. ✅ Pronto! Você está agora na nova branch

#### Trocar entre branches:

1. **Clique no nome da branch** no canto inferior esquerdo
2. Uma lista de branches aparecerá
3. **Clique na branch** que deseja usar
4. ✅ Mudança feita!

#### Criar branch a partir de outra branch:

1. Primeiro, **troque para a branch base** (ex: `main`)
2. Clique no nome da branch no canto inferior esquerdo
3. Selecione: **+ Create new branch...**
4. Digite o nome: `feature/minha-nova-funcionalidade`
5. A nova branch será criada a partir da branch atual

### 🎯 Método 2: Command Palette

1. Pressione `Ctrl + Shift + P`
2. Digite: **Git: Create Branch**
3. Pressione `Enter`
4. Digite o nome da branch: `feature/sistema-avaliacoes`
5. Pressione `Enter`

**Trocar de branch:**

1. Pressione `Ctrl + Shift + P`
2. Digite: **Git: Checkout to...**
3. Selecione a branch desejada da lista

### 🎯 Método 3: Source Control (Visual)

1. Clique no ícone **Source Control** (barra lateral esquerda)
2. Clique no botão **⋯** (três pontinhos) no topo
3. Navegue: **Branch → Create Branch...**
4. Digite o nome da branch
5. Pressione `Enter`

### 📋 Ver Todas as Branches

1. No **Source Control**, clique em **⋯**
2. Selecione **Branch → Show All Branches**
3. Verá uma lista completa de branches locais e remotas

### 🗑️ Deletar Branch

1. Clique no nome da branch (canto inferior esquerdo)
2. Na lista, passe o mouse sobre a branch que deseja deletar
3. Clique no ícone **🗑️** (lixeira) ao lado da branch
4. Confirme a exclusão

**Ou:**

1. Pressione `Ctrl + Shift + P`
2. Digite: **Git: Delete Branch**
3. Selecione a branch a ser deletada
4. Confirme

---

## 📝 Fazendo Commits (Interface Visual)

### Interface do Source Control

1. **Clique no ícone Source Control** (3º ícone na barra lateral)
   - Atalho: `Ctrl + Shift + G`

2. **Visualização da interface:**

```
🔍 SOURCE CONTROL

📝 Message: [Digite sua mensagem aqui]
   [✓ Commit]  [✕ Cancel]

📂 Changes (3)                    [+ Stage All Changes]
   M  index.html                  [+] [↶]
   M  detalhes.html              [+] [↶]
   A  CONTRIBUTING.md            [+] [↶]

📦 Staged Changes (0)
   (nenhum arquivo aqui ainda)
```

### Passo a Passo: Fazer um Commit

#### 1. Ver as Mudanças

- Na seção **Changes**, você verá todos os arquivos modificados
- **M** = Modified (modificado)
- **A** = Added (adicionado)
- **D** = Deleted (deletado)
- **U** = Untracked (não rastreado)

#### 2. Visualizar Diferenças (Diff)

- **Clique em um arquivo** na lista
- Uma nova aba se abrirá mostrando:
  - **Esquerda:** Versão antiga
  - **Direita:** Versão nova
  - **Verde:** Linhas adicionadas
  - **Vermelho:** Linhas removidas

#### 3. Adicionar Arquivos ao Commit (Stage)

**Opção A: Adicionar todos os arquivos**

1. Passe o mouse sobre **Changes**
2. Clique no ícone **+** (Stage All Changes)
3. Todos os arquivos irão para **Staged Changes**

**Opção B: Adicionar arquivos específicos**

1. Passe o mouse sobre o arquivo desejado
2. Clique no ícone **+** ao lado do arquivo
3. O arquivo irá para **Staged Changes**

**Opção C: Adicionar partes específicas do arquivo**

1. Clique com botão direito no arquivo
2. Selecione **Stage Selected Ranges**
3. Selecione apenas as linhas que deseja commitar

#### 4. Remover Arquivo do Stage (Unstage)

- Na seção **Staged Changes**, clique no ícone **-** ao lado do arquivo
- O arquivo volta para **Changes**

#### 5. Descartar Mudanças

⚠️ **ATENÇÃO:** Isso apagará suas alterações permanentemente!

1. Na seção **Changes**, clique no ícone **↶** (desfazer) ao lado do arquivo
2. Confirme a ação
3. As mudanças serão perdidas

#### 6. Escrever Mensagem do Commit

No campo **Message** no topo:

**✅ Boas mensagens:**
```
feat: adiciona filtros de busca por raça e idade
fix: corrige bug no carrossel de imagens
style: ajusta espaçamento dos cards de pets
docs: atualiza guia de contribuição
```

**❌ Mensagens ruins:**
```
update
fix
mudanças
teste
```

**Tipos de commit:**
- `feat:` - Nova funcionalidade
- `fix:` - Correção de bug
- `style:` - Mudanças visuais/CSS
- `refactor:` - Refatoração de código
- `docs:` - Documentação
- `chore:` - Tarefas de manutenção

#### 7. Fazer o Commit

**Método 1: Botão Commit**
1. Digite a mensagem
2. Clique no botão **✓ Commit**

**Método 2: Atalho de teclado**
1. Digite a mensagem
2. Pressione `Ctrl + Enter`

**Método 3: Menu**
1. Digite a mensagem
2. Clique em **⋯** (três pontinhos)
3. Selecione **Commit → Commit**

#### 8. Commit com Amend (Corrigir último commit)

Se esqueceu de adicionar algo no último commit:

1. Faça as mudanças necessárias
2. Adicione ao stage (ícone +)
3. Clique em **⋯** (três pontinhos)
4. Selecione **Commit → Commit (Amend)**
5. Edite a mensagem se necessário
6. Confirme

### 📊 Ver Histórico de Commits

**Método 1: GitLens (após instalar extensão)**
1. Clique na aba **Source Control**
2. Na seção inferior, clique em **Commits**
3. Verá lista de todos os commits

**Método 2: Timeline**
1. Abra um arquivo
2. Na barra lateral, clique em **Timeline** (ícone de relógio)
3. Verá histórico de mudanças daquele arquivo

**Método 3: Git Graph (após instalar extensão)**
1. Clique em **Source Control**
2. Clique no ícone **Git Graph** no topo
3. Verá gráfico visual de todos os commits e branches

---

## 🔄 Sincronizando com GitHub

### 📤 Enviar Mudanças (Push)

#### Método 1: Barra de Status (Mais Fácil)

Após fazer commit, olhe na barra de status (canto inferior):

1. Clique no ícone **↑** com um número (ex: ↑1)
2. Suas mudanças serão enviadas ao GitHub
3. ✅ Pronto!

#### Método 2: Source Control

1. No **Source Control**, clique em **⋯** (três pontinhos)
2. Selecione **Push**
3. Aguarde confirmação

#### Método 3: Sync (Sincronizar)

Sincroniza tudo (pull + push):

1. Clique no ícone **↻** (circular com setas) na barra de status
2. Ou clique em **⋯** → **Sync**

### 📥 Receber Mudanças (Pull)

#### Método 1: Barra de Status

1. Clique no ícone **↓** com um número (ex: ↓2)
2. Mudanças do GitHub serão baixadas
3. ✅ Pronto!

#### Método 2: Source Control

1. No **Source Control**, clique em **⋯**
2. Selecione **Pull**
3. Aguarde download

### 🔄 Sincronizar (Pull + Push)

1. Clique no ícone **↻** (sincronizar) na barra de status
2. Ou: **⋯** → **Sync**
3. Faz pull e push automaticamente

### 🌐 Publicar Branch no GitHub

Quando cria uma branch local nova:

1. Faça um commit na nova branch
2. Clique no ícone **☁️ Publish Branch** na barra de status
3. Ou: **⋯** → **Push**
4. A branch será criada no GitHub

### 🔍 Ver Mudanças Remotas

1. **⋯** → **Remote → Fetch**
2. Busca atualizações do GitHub sem baixar
3. Você verá quantos commits estão disponíveis

---

## 🔀 Workflow Completo: Dois Desenvolvedores

### 👨‍💻 Desenvolvedor 1: João (trabalhando em index.html)

#### Segunda-feira - Início do dia

1. **Abrir VS Code** na pasta do projeto
2. **Atualizar branch main:**
   - Clicar na branch (canto inferior esquerdo)
   - Selecionar **main**
   - Clicar no ícone **↓** (pull) para baixar atualizações
3. **Criar nova branch:**
   - Clicar em **main** (canto inferior esquerdo)
   - Selecionar **+ Create new branch...**
   - Digite: `feature/filtros-avancados`
   - Pressione `Enter`
4. **Trabalhar no index.html:**
   - Adicionar filtros de busca por raça, idade e tamanho
   - Salvar o arquivo (`Ctrl + S`)
5. **Ver mudanças:**
   - Abrir **Source Control** (`Ctrl + Shift + G`)
   - Clicar em **index.html** para ver diff
6. **Fazer commit:**
   - Clicar no **+** ao lado de **index.html** (stage)
   - Digitar mensagem: `feat: adiciona filtros avançados de busca`
   - Clicar em **✓ Commit** (ou `Ctrl + Enter`)
7. **Enviar para GitHub:**
   - Clicar no ícone **☁️ Publish Branch** na barra de status
8. **Criar Pull Request:**
   - VS Code mostrará notificação
   - Clicar em **Create Pull Request**
   - Ou ir no GitHub e clicar em **Compare & pull request**

### 👩‍💻 Desenvolvedor 2: Maria (trabalhando em detalhes.html)

#### Segunda-feira - Mesmo horário

1. **Abrir VS Code** na pasta do projeto
2. **Atualizar branch main:**
   - Clicar na branch → **main**
   - Clicar no ícone **↓** (pull)
3. **Criar nova branch:**
   - Clicar em **main** → **+ Create new branch...**
   - Digite: `feature/sistema-favoritos`
4. **Trabalhar no detalhes.html:**
   - Adicionar botão e funcionalidade de favoritar
   - Salvar o arquivo
5. **Fazer commit:**
   - **Source Control** → Clicar no **+** ao lado de **detalhes.html**
   - Mensagem: `feat: adiciona sistema de favoritos`
   - **✓ Commit**
6. **Enviar para GitHub:**
   - Clicar em **☁️ Publish Branch**
7. **Criar Pull Request** no GitHub

### ✅ Após Aprovação

#### João teve seu PR aprovado e mergeado no main

#### Maria precisa atualizar sua branch:

1. **Ir para branch main:**
   - Clicar na branch → **main**
   - Clicar no ícone **↓** (pull) para baixar mudanças do João
2. **Voltar para sua branch:**
   - Clicar na branch → **feature/sistema-favoritos**
3. **Trazer mudanças do main:**
   - **⋯** → **Branch → Merge Branch...**
   - Selecionar **main**
   - Confirmar merge
4. **Resolver conflitos se houver** (veja próxima seção)
5. **Continuar trabalhando**
6. **Enviar atualização:**
   - Clicar no ícone **↑** (push)

---

## ⚔️ Resolvendo Conflitos (Interface Visual)

### O que é um Conflito?

Acontece quando você e outro desenvolvedor modificam a **mesma linha** do **mesmo arquivo**.

### Quando Aparecem?

- Ao fazer **Pull** (baixar mudanças)
- Ao fazer **Merge** de branches

### Como Resolver no VS Code

#### 1. Identificar Conflito

Ao fazer pull/merge, VS Code mostrará:

- ⚠️ Notificação: **"Merge conflicts detected"**
- No **Source Control**, arquivos em conflito terão ícone **⚠️**
- Arquivos conflitantes aparecem em **Merge Changes**

#### 2. Abrir Arquivo em Conflito

1. No **Source Control**, clique no arquivo com **⚠️**
2. O VS Code abrirá o arquivo com marcações visuais

#### 3. Interface de Resolução

O arquivo mostrará algo assim:

```html
<<<<<<< HEAD (Current Change)
<title>PetClassificados - Adote seu Amigo</title>
=======
<title>PetClassificados - Encontre seu Pet</title>
>>>>>>> feature/outro-dev (Incoming Change)
```

**O VS Code mostrará botões acima do conflito:**

```
┌─────────────────────────────────────────────────┐
│ Accept Current Change | Accept Incoming Change  │
│ Accept Both Changes   | Compare Changes         │
└─────────────────────────────────────────────────┘
<<<<<<< HEAD (Current Change)
<title>PetClassificados - Adote seu Amigo</title>
=======
<title>PetClassificados - Encontre seu Pet</title>
>>>>>>> feature/outro-dev (Incoming Change)
```

#### 4. Escolher Resolução

**Opção 1: Accept Current Change**
- Mantém **sua versão** (do HEAD)
- Descarta a versão do outro desenvolvedor

**Opção 2: Accept Incoming Change**
- Usa a **versão do outro dev**
- Descarta sua versão

**Opção 3: Accept Both Changes**
- Mantém **ambas as versões**
- Fica uma após a outra

**Opção 4: Compare Changes**
- Abre visualização lado a lado
- Você pode editar manualmente

**Opção 5: Editar Manualmente**
- Delete as linhas marcadas (`<<<<<<<`, `=======`, `>>>>>>>`)
- Escreva a versão final desejada

#### 5. Exemplo Prático

**Conflito:**
```html
<<<<<<< HEAD
<title>PetClassificados - Adote seu Amigo</title>
=======
<title>PetClassificados - Encontre seu Pet</title>
>>>>>>> feature/outro-dev
```

**Resolução Manual (melhor opção):**
```html
<title>PetClassificados - Adote ou Encontre seu Pet</title>
```

#### 6. Finalizar Resolução

1. **Resolver todos os conflitos** do arquivo
2. **Salvar o arquivo** (`Ctrl + S`)
3. No **Source Control**, o arquivo sairá de **Merge Changes**
4. Clicar no **+** para fazer stage
5. **Commit** com mensagem: `fix: resolve conflito de merge`
6. Clicar em **✓ Commit**
7. Clicar no ícone **↑** (push)

#### 7. Abortar Merge (Se der muito errado)

1. **⋯** → **Branch → Abort Merge**
2. Tudo volta ao estado anterior
3. Você pode tentar novamente

### 🎨 Extensão Merge Editor

Para conflitos complexos:

1. Instale a extensão **GitLens** (veja seção de extensões)
2. Ao abrir conflito, clique em **Resolve in Merge Editor**
3. Interface com 3 painéis:
   - **Esquerda:** Suas mudanças
   - **Centro:** Resultado final (editável)
   - **Direita:** Mudanças do outro dev
4. Clique nas mudanças que deseja aceitar
5. Edite o painel central se necessário
6. Clique em **Complete Merge**

---

## 🔍 Visualizando Histórico e Diferenças

### Timeline (Nativo do VS Code)

1. **Abra um arquivo** (ex: index.html)
2. Na barra lateral, clique no ícone **📊 Timeline** (parece um relógio)
3. Verá lista de todas as modificações daquele arquivo
4. **Clique em um commit** para ver o que mudou

### Ver Commit Específico

1. No **Timeline**, clique em um commit
2. Aparecerá diff mostrando mudanças
3. **Verde:** Linhas adicionadas
4. **Vermelho:** Linhas removidas

### Comparar Arquivos

1. Abra um arquivo
2. Clique com botão direito no arquivo
3. **Select for Compare**
4. Abra outro arquivo
5. Clique com botão direito → **Compare with Selected**

### Ver Mudanças Antes de Commitar

1. No **Source Control**, clique em um arquivo em **Changes**
2. Diff será aberto automaticamente
3. Revise todas as mudanças
4. Se estiver OK, adicione ao stage

---

## 🎯 Extensões Essenciais

### 1. GitLens (Imprescindível!)

**Instalar:**
1. `Ctrl + Shift + X` (abrir Extensions)
2. Buscar: **GitLens**
3. Clicar em **Install**
4. Reiniciar VS Code

**Recursos:**

- **Blame inline:** Vê quem modificou cada linha
  - Passe o mouse sobre qualquer linha
  - Aparecerá quem, quando e em qual commit alterou

- **File History:**
  - Clique com botão direito no arquivo
  - **GitLens → Show File History**
  - Vê todos os commits que modificaram o arquivo

- **Line History:**
  - Selecione uma linha
  - Clique com botão direito
  - **GitLens → Show Line History**

- **Compare:**
  - **⋯** → **GitLens → Compare With...**
  - Compare branches, commits, etc

- **Search Commits:**
  - **⋯** → **GitLens → Search Commits**
  - Busque por autor, mensagem, arquivo

### 2. Git Graph (Visualização de Branches)

**Instalar:**
1. `Ctrl + Shift + X`
2. Buscar: **Git Graph**
3. **Install**

**Usar:**
1. No **Source Control**, clique no ícone **Git Graph** no topo
2. Verá gráfico visual bonito com:
   - Todas as branches (linhas coloridas)
   - Commits (bolinhas)
   - Merges (linhas se juntando)
3. **Clique em um commit** para ver detalhes
4. **Clique com botão direito** para:
   - Criar branch a partir daquele commit
   - Fazer checkout
   - Copiar hash do commit

### 3. Git History

**Instalar:**
1. `Ctrl + Shift + X`
2. Buscar: **Git History**
3. **Install**

**Usar:**
1. Clique com botão direito em um arquivo
2. **Git: View File History**
3. Verá lista de commits
4. Clique para ver mudanças

### 4. GitHub Pull Requests

**Instalar:**
1. `Ctrl + Shift + X`
2. Buscar: **GitHub Pull Requests and Issues**
3. **Install**
4. Faça login no GitHub quando solicitar

**Recursos:**

- **Ver PRs no VS Code:**
  - Novo ícone na barra lateral: **GitHub**
  - Veja PRs abertos, fechados, seus PRs

- **Revisar PR:**
  - Clique em um PR
  - Veja arquivos modificados
  - Adicione comentários inline
  - Aprove ou solicite mudanças

- **Criar PR:**
  - **⋯** → **Pull Request → Create Pull Request**
  - Preencha título e descrição
  - Escolha reviewers
  - Crie direto do VS Code!

### 5. Git File History

**Instalar:**
1. `Ctrl + Shift + X`
2. Buscar: **Git File History**
3. **Install**

**Usar:**
- Clique com botão direito → **Git File History**
- Interface visual bonita do histórico

---

## ⚡ Atalhos de Teclado

| Ação | Windows/Linux | Mac |
|------|---------------|-----|
| Abrir Source Control | `Ctrl + Shift + G` | `Cmd + Shift + G` |
| Command Palette | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| Commit | `Ctrl + Enter` | `Cmd + Enter` |
| Ver diff (arquivo selecionado) | Clique no arquivo | Clique no arquivo |
| Abrir Extensions | `Ctrl + Shift + X` | `Cmd + Shift + X` |
| Fechar painel lateral | `Ctrl + B` | `Cmd + B` |
| Buscar arquivo | `Ctrl + P` | `Cmd + P` |
| Salvar | `Ctrl + S` | `Cmd + S` |

### Personalizar Atalhos

1. `Ctrl + K` seguido de `Ctrl + S`
2. Busque: **git**
3. Clique no ícone de lápis ao lado do comando
4. Pressione a combinação desejada
5. `Enter` para confirmar

---

## 🛡️ Boas Práticas

### ✅ Sempre Fazer

1. **Fazer Pull antes de começar o dia**
   - Clicar no ícone **↓** logo ao abrir o VS Code
   - Garante que você tem as últimas mudanças

2. **Criar branch para cada funcionalidade**
   - Nunca trabalhar direto na **main**
   - Use nomes descritivos: `feature/nome-claro`

3. **Commits pequenos e frequentes**
   - Melhor fazer 5 commits pequenos que 1 gigante
   - Facilita reverter se algo der errado

4. **Revisar mudanças antes de commitar**
   - Sempre clicar no arquivo para ver o diff
   - Garante que não está commitando algo errado

5. **Mensagens claras de commit**
   - Use o padrão: `tipo: descrição`
   - Exemplos: `feat:`, `fix:`, `style:`

6. **Fazer Pull Request ao invés de merge direto**
   - Permite revisão do código
   - Outro dev pode verificar antes de mergear

### ❌ Evitar

1. **Trabalhar direto na main**
   - Sempre crie uma branch

2. **Commits com mensagens vagas**
   - "update", "fix", "mudanças" não dizem nada

3. **Commitar arquivos temporários**
   - `.DS_Store`, `node_modules`, `*.log`
   - Use `.gitignore`

4. **Fazer push sem testar**
   - Sempre abra o HTML no navegador antes
   - Garanta que está funcionando

5. **Ignorar conflitos**
   - Resolva imediatamente
   - Não deixe acumular

6. **Esquecer de fazer pull**
   - Sempre atualize antes de começar
   - Evita conflitos desnecessários

---

## 🚨 Solução de Problemas

### Problema: Não consigo fazer Pull

**Causa:** Você tem mudanças não commitadas

**Solução:**
1. Faça commit das mudanças
2. Ou descarte as mudanças (ícone **↶**)
3. Depois faça pull

### Problema: Meu commit foi para branch errada

**Solução:**
1. Anote o hash do commit (veja no GitLens ou Git Graph)
2. Troque para a branch correta
3. **⋯** → **Branch → Cherry Pick...**
4. Cole o hash do commit
5. Na branch errada: **⋯** → **Undo Last Commit**

### Problema: Quero desfazer último commit

**Solução (mantém mudanças):**
1. **⋯** → **Commit → Undo Last Commit**
2. Os arquivos voltam para **Changes**
3. Você pode refazer o commit

### Problema: Arquivos sensíveis foram commitados

**Solução:**
1. Adicione ao `.gitignore`
2. **⋯** → **Changes → Unstage All**
3. Remova os arquivos sensíveis
4. Commit novamente

---

## 🎓 Fluxo de Trabalho Recomendado

### Início do Dia

1. ☕ Abrir VS Code
2. 📥 **Pull** na branch main (ícone **↓**)
3. 🌿 Criar nova branch ou trocar para branch de trabalho
4. 👨‍💻 Começar a trabalhar

### Durante o Trabalho

5. 💾 Salvar frequentemente (`Ctrl + S`)
6. 👀 Abrir **Source Control** para ver mudanças
7. ✅ Fazer commits pequenos a cada funcionalidade completa
8. 📤 **Push** ao terminar cada commit (ícone **↑**)

### Fim do Dia

9. 🔍 Revisar todas as mudanças do dia
10. ✅ Garantir que tudo está commitado
11. 📤 **Push** final
12. 🔄 Se terminou a funcionalidade, criar **Pull Request**

### Quando PR for Aprovado

13. 🎉 Merge no GitHub
14. 🔄 Trocar para branch **main**
15. 📥 Fazer **Pull** para baixar o merge
16. 🌿 Criar nova branch para próxima funcionalidade

---

## 📚 Recursos Visuais do VS Code

### Barra Lateral Esquerda (Ícones)

```
📁 Explorer         - Arquivos e pastas
🔍 Search          - Buscar em arquivos
⚡ Source Control  - Git (O QUE MAIS USAMOS!)
🐞 Debug           - Depuração
🧩 Extensions      - Extensões
```

### Barra de Status (Parte Inferior)

```
🌿 main           - Branch atual (CLICAR AQUI para mudar)
↻ 0↓ 0↑          - Sincronizar (pull + push)
⚠️ 0  ⓘ 0         - Erros e avisos
🔔                - Notificações
```

### Botões do Source Control

```
⋯                 - Menu com todas as opções Git
✓                - Commit
+                - Stage (adicionar ao commit)
-                - Unstage (remover do stage)
↶                - Discard (descartar mudanças)
🔄               - Refresh (atualizar)
```

---

## 💡 Dicas Finais

1. **Use o mouse à vontade** - VS Code foi feito para ser intuitivo
2. **Explore o menu ⋯** - Tem TODAS as opções Git lá
3. **Instale GitLens** - Melhora MUITO a experiência
4. **Use Git Graph** - Visualizar branches fica muito mais fácil
5. **Não tenha medo de clicar** - VS Code sempre pede confirmação em ações destrutivas
6. **Passe o mouse nos ícones** - Tooltips explicam o que cada botão faz
7. **Command Palette é seu amigo** - `Ctrl + Shift + P` e digite o que quer fazer

---

## 🎯 Comandos Principais (Via Command Palette)

Pressione `Ctrl + Shift + P` e digite:

- **Git: Create Branch** - Criar branch
- **Git: Checkout to** - Trocar branch
- **Git: Commit** - Fazer commit
- **Git: Push** - Enviar ao GitHub
- **Git: Pull** - Baixar do GitHub
- **Git: Sync** - Sincronizar (pull + push)
- **Git: Clone** - Clonar repositório
- **Git: Show Output** - Ver log do Git
- **Git: Undo Last Commit** - Desfazer commit
- **Git: Delete Branch** - Deletar branch

---

**Pronto para começar! Use este guia sempre que tiver dúvida. 🚀**

**Lembre-se: A melhor forma de aprender é praticando. Não tenha medo de explorar os menus e botões do VS Code!**
=======
<h1>Título da versão remota</h1>
>>>>>>> feature/outra-branch (Incoming Change)
```

3. **Opções no VS Code:**
   - **Accept Current Change** - mantém sua versão
   - **Accept Incoming Change** - usa a versão do outro dev
   - **Accept Both Changes** - mantém ambas
   - **Compare Changes** - vê diferenças lado a lado

4. **Após resolver:**
   - Salve o arquivo
   - Adicione: `git add arquivo-resolvido.html`
   - Commite: `git commit -m "fix: resolve conflito de merge"`

### Exemplo Prático de Conflito

**Desenvolvedor 1 alterou:**
```html
<title>PetClassificados - Adote seu Amigo</title>
```

**Desenvolvedor 2 alterou:**
```html
<title>PetClassificados - Encontre seu Pet</title>
```

**Conflito gerado:**
```html
<<<<<<< HEAD
<title>PetClassificados - Adote seu Amigo</title>
=======
<title>PetClassificados - Encontre seu Pet</title>
>>>>>>> feature/outro-dev
```

**Resolução (escolher um ou combinar):**
```html
<title>PetClassificados - Adote ou Encontre seu Pet</title>
```

---

## 🔍 Visualizando Branches e Histórico

### Extensão GitLens (Recomendada)

1. Instale a extensão **GitLens** no VS Code:
   - `Ctrl + Shift + X` para abrir Extensions
   - Busque: "GitLens"
   - Clique em **Install**

2. **Recursos do GitLens:**
   - Ver quem modificou cada linha (blame)
   - Histórico de commits visual
   - Comparar branches facilmente
   - Ver detalhes do commit ao passar o mouse

### Extensão Git Graph (Visual)

1. Instale **Git Graph**:
   - `Ctrl + Shift + X` para abrir Extensions
   - Busque: "Git Graph"
   - Clique em **Install**

2. **Usar Git Graph:**
   - Clique no ícone do Source Control
   - Clique em "View Git Graph" no topo
   - Verá um gráfico visual das branches

---

## ⚡ Atalhos Úteis do VS Code

### Atalhos de Teclado

| Ação | Windows/Linux | Mac |
|------|---------------|-----|
| Abrir Source Control | `Ctrl + Shift + G` | `Cmd + Shift + G` |
| Abrir Terminal | `Ctrl + '` | `Cmd + '` |
| Command Palette | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| Commit | `Ctrl + Enter` | `Cmd + Enter` |
| Ver diff do arquivo | Clique no arquivo | Clique no arquivo |

### Comandos Úteis no Terminal

```bash
# Ver branches
git branch -a

# Ver branch atual
git branch --show-current

# Deletar branch local
git branch -d feature/nome-branch

# Ver log bonito
git log --oneline --graph --all

# Ver diferenças
git diff
git diff HEAD~1  # diferença do último commit

# Desfazer mudanças não commitadas
git checkout -- arquivo.html

# Desfazer último commit (mantém mudanças)
git reset --soft HEAD~1

# Ver arquivos modificados
git status -s
```

---

## 🎯 Cenário Prático Completo

### Situação: Dois Desenvolvedores Trabalhando Juntos

**Desenvolvedor 1: João (index.html)**

```bash
# Segunda-feira - 9h
git checkout main
git pull origin main
git checkout -b feature/filtros-avancados

# Trabalha no index.html
# Adiciona filtros por idade, raça, tamanho

git add index.html
git commit -m "feat: adiciona filtros avançados de busca"
git push -u origin feature/filtros-avancados

# Abre Pull Request no GitHub
# Aguarda revisão
```

**Desenvolvedor 2: Maria (detalhes.html)**

```bash
# Segunda-feira - 9h
git checkout main
git pull origin main
git checkout -b feature/sistema-favoritos

# Trabalha no detalhes.html
# Adiciona botão de favoritar

git add detalhes.html
git commit -m "feat: adiciona sistema de favoritos"
git push -u origin feature/sistema-favoritos

# Abre Pull Request no GitHub
# Aguarda revisão
```

**Aprovação e Merge**

```bash
# Pull Request do João é aprovado e mergeado no main

# Maria precisa atualizar sua branch com as mudanças do João
git checkout main
git pull origin main
git checkout feature/sistema-favoritos
git merge main  # traz mudanças do João

# Se houver conflitos, resolve no VS Code
# Continua trabalhando

git push  # envia atualização
```

---

## 🛡️ Boas Práticas

### ✅ Fazer

- Sempre criar uma branch para cada funcionalidade
- Fazer commits pequenos e frequentes
- Usar mensagens de commit descritivas
- Fazer pull antes de começar a trabalhar
- Testar antes de fazer commit
- Revisar mudanças antes de commitar (ver diff)

### ❌ Evitar

- Trabalhar diretamente na branch main
- Commits grandes com muitas mudanças
- Mensagens vagas: "fix", "update"
- Esquecer de fazer pull antes de começar
- Commitar arquivos temporários ou node_modules
- Fazer push sem testar

---

## 🚨 Comandos de Emergência

### Desfazer mudanças não commitadas

```bash
# Desfazer mudanças em um arquivo específico
git checkout -- index.html

# Desfazer todas as mudanças não commitadas
git reset --hard HEAD
```

### Desfazer último commit (mantendo mudanças)

```bash
git reset --soft HEAD~1
```

### Voltar para um commit anterior

```bash
# Ver histórico
git log --oneline

# Voltar para um commit específico
git checkout abc1234  # substitua pelo hash do commit
```

### Criar branch a partir de commit anterior

```bash
git checkout -b feature/recuperar-codigo abc1234
```

---

## 📚 Recursos Adicionais

### Extensões Recomendadas para VS Code

1. **GitLens** - Supercharge Git
2. **Git Graph** - Visualização de branches
3. **Git History** - Ver histórico de arquivos
4. **GitHub Pull Requests** - Gerenciar PRs no VS Code

### Links Úteis

- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [VS Code Git Documentation](https://code.visualstudio.com/docs/sourcecontrol/overview)
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)

---

## 💡 Dicas Finais

1. **Commit frequentemente** - É melhor muitos commits pequenos que um grande
2. **Sempre teste antes de commitar** - Abra o HTML no navegador
3. **Use branches descritivas** - `feature/filtros-busca` é melhor que `teste`
4. **Faça pull regularmente** - Mantenha-se atualizado com o trabalho do time
5. **Resolva conflitos rapidamente** - Não deixe acumular
6. **Comunique-se com o time** - Avise quando for trabalhar em algo

---

**Dúvidas? Consulte este guia ou peça ajuda ao time! 🚀**
