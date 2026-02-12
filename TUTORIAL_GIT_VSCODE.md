# 🎯 Tutorial Git e Branches no VS Code
## Guia Visual - PetClassificados

> **🖱️ 100% Interface Gráfica** - Este tutorial ensina Git usando apenas menus e botões do VS Code, sem comandos de terminal (exceto instalação inicial do Git).

---

## 📋 Índice

1. [Configuração Inicial](#-1-configuração-inicial)
2. [Conhecendo a Interface Git do VS Code](#-2-conhecendo-a-interface-git-do-vs-code)
3. [Criando e Gerenciando Branches](#-3-criando-e-gerenciando-branches)
4. [Fazendo Commits](#-4-fazendo-commits)
5. [Sincronizando com GitHub](#-5-sincronizando-com-github)
6. [Workflow para Dois Desenvolvedores](#-6-workflow-para-dois-desenvolvedores)
7. [Resolvendo Conflitos](#-7-resolvendo-conflitos)
8. [Extensões Essenciais](#-8-extensões-essenciais)
9. [Atalhos de Teclado](#-9-atalhos-de-teclado)
10. [Dicas e Boas Práticas](#-10-dicas-e-boas-práticas)

---

## 🚀 1. Configuração Inicial

### 1.1 Instalar o Git (Apenas uma vez)

**Windows:**
1. Baixe em: https://git-scm.com/download/win
2. Execute o instalador
3. Use as opções padrão (clique Next em tudo)

**Mac:**
1. Abra o Terminal
2. Digite: `git --version`
3. Se não instalado, o macOS oferecerá para instalar

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install git
```

### 1.2 Verificar Instalação (Visual)

1. Abra o **VS Code**
2. Pressione `Ctrl + Shift + P` (Command Palette)
3. Digite: `Git: Version`
4. Deve mostrar a versão instalada

### 1.3 Configurar Nome e Email (Visual)

**Método 1 - Usando Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Edit Configuration`
3. Escolha: **User Settings**
4. Adicione suas informações:

```
[user]
    name = Seu Nome
    email = seuemail@exemplo.com
```

**Método 2 - Usando Terminal Integrado (apenas esta vez):**
1. Pressione `` Ctrl + ` `` para abrir Terminal
2. Digite:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```

### 1.4 Abrir o Projeto no VS Code

1. **File** → **Open Folder**
2. Navegue até a pasta **PetClassificados**
3. Clique em **Selecionar Pasta**

### 1.5 Inicializar Repositório Git (Visual)

**Opção 1 - Pelo Source Control:**
1. Clique no ícone do **Source Control** (3º ícone da barra lateral, ou `Ctrl + Shift + G`)
2. Clique no botão **Initialize Repository**

**Opção 2 - Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Initialize Repository`
3. Selecione a pasta do projeto

### 1.6 Conectar com GitHub (Visual)

1. No **Source Control**, clique no menu `...` (três pontinhos)
2. Selecione: **Remote** → **Add Remote**
3. Digite a URL do repositório GitHub:
   ```
   https://github.com/seu-usuario/PetClassificados.git
   ```
4. Digite um nome para o remote (geralmente: `origin`)

**Alternativa - Publicar Diretamente:**
1. No **Source Control**, clique no botão **Publish Branch** (na barra superior)
2. Escolha: **Publish to GitHub**
3. Selecione: **Public** ou **Private**
4. Confirme

---

## 🖥️ 2. Conhecendo a Interface Git do VS Code

### 2.1 Ícones Principais

| Ícone | Localização | Função |
|-------|-------------|--------|
| **Source Control** | Barra lateral esquerda (3º ícone) | Gerenciar commits, branches |
| **Sync** ↻ | Barra de status (canto inferior esquerdo) | Push/Pull do GitHub |
| **Branch** 🌿 | Barra de status (canto inferior esquerdo) | Ver e trocar de branch |
| **Extensions** 🧩 | Barra lateral esquerda (5º ícone) | Instalar extensões Git |

### 2.2 Painel Source Control

Quando você abre o **Source Control** (`Ctrl + Shift + G`), verá:

```
SOURCE CONTROL
├── 📝 Changes (arquivos modificados)
│   ├── index.html
│   └── detalhes.html
├── 📌 Staged Changes (prontos para commit)
│   └── style.css
└── 💬 Message (campo para escrever mensagem de commit)
```

### 2.3 Indicadores Visuais

- **M** (Modified) - Arquivo modificado
- **A** (Added) - Arquivo novo
- **D** (Deleted) - Arquivo deletado
- **U** (Untracked) - Arquivo não rastreado pelo Git
- **C** (Conflict) - Arquivo com conflito

---

## 🌿 3. Criando e Gerenciando Branches

### 3.1 Criar Nova Branch (3 Métodos Visuais)

**Método 1 - Pela Barra de Status (Mais Rápido):**
1. Clique no nome da branch (canto inferior esquerdo)
2. Clique em **Create new branch...**
3. Digite o nome: `feature/minha-feature`
4. Pressione **Enter**

**Método 2 - Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Create Branch`
3. Digite o nome: `feature/nova-funcionalidade`
4. Pressione **Enter**

**Método 3 - Pelo Source Control:**
1. Abra **Source Control** (`Ctrl + Shift + G`)
2. Clique no menu `...` (três pontinhos)
3. Selecione: **Branch** → **Create Branch**
4. Digite o nome da branch

### 3.2 Trocar de Branch (Checkout)

**Método 1 - Pela Barra de Status:**
1. Clique no nome da branch atual
2. Escolha a branch desejada na lista

**Método 2 - Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Checkout to...`
3. Escolha a branch

### 3.3 Ver Todas as Branches

**Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Show Branches`

**Pela Barra de Status:**
- Clique no nome da branch
- Verá lista de todas as branches

### 3.4 Deletar Branch

**Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Delete Branch`
3. Escolha a branch para deletar
4. Confirme

**⚠️ Não delete a branch `main` ou branches em uso!**

---

## ✅ 4. Fazendo Commits

### 4.1 Visualizar Mudanças (Diff)

1. Abra **Source Control** (`Ctrl + Shift + G`)
2. Clique em qualquer arquivo modificado
3. Verá comparação lado a lado:
   - **Esquerda:** Versão anterior
   - **Direita:** Versão atual

### 4.2 Adicionar Arquivos (Stage)

**Opção 1 - Arquivo Individual:**
1. No **Source Control**, passe o mouse sobre o arquivo
2. Clique no ícone **+** (Stage Changes)

**Opção 2 - Todos os Arquivos:**
1. Clique no ícone **+** ao lado de "Changes"

**Opção 3 - Via Menu:**
1. Clique com botão direito no arquivo
2. Selecione: **Stage Changes**

### 4.3 Remover do Stage (Unstage)

1. No **Staged Changes**, passe o mouse sobre o arquivo
2. Clique no ícone **−** (Unstage Changes)

### 4.4 Descartar Mudanças

**⚠️ ATENÇÃO: Isso apaga suas alterações permanentemente!**

1. No **Source Control**, clique com botão direito no arquivo
2. Selecione: **Discard Changes**
3. Confirme

### 4.5 Escrever Mensagem de Commit

**Formato Recomendado (Conventional Commits):**

```
tipo: descrição curta

Descrição detalhada (opcional)
```

**Tipos:**
- `feat:` - Nova funcionalidade
- `fix:` - Correção de bug
- `style:` - Mudanças visuais (CSS)
- `refactor:` - Refatoração de código
- `docs:` - Documentação
- `test:` - Testes

**Exemplos:**
```
feat: adiciona filtro de busca por raça

fix: corrige botão de favoritar no detalhes.html

style: altera cor de fundo para verde claro
```

### 4.6 Fazer o Commit

1. No campo **Message**, escreva a mensagem
2. Clique no botão **✓ Commit** (ou `Ctrl + Enter`)

### 4.7 Commit e Push Direto

1. Clique na setinha ao lado do botão **Commit**
2. Selecione: **Commit & Push**

### 4.8 Alterar Último Commit (Amend)

Se esqueceu algo no último commit:

1. Faça as mudanças necessárias
2. Adicione ao Stage
3. No **Source Control**, clique no menu `...`
4. Selecione: **Commit** → **Commit Staged (Amend)**

---

## 🔄 5. Sincronizando com GitHub

### 5.1 Push (Enviar Commits para GitHub)

**Método 1 - Pela Barra de Status:**
1. Após fazer commit, verá um ícone de **seta para cima** com número
2. Clique no ícone
3. Confirme o Push

**Método 2 - Pelo Source Control:**
1. Clique no menu `...` (três pontinhos)
2. Selecione: **Push**

**Método 3 - Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Push`

### 5.2 Pull (Baixar Mudanças do GitHub)

**Método 1 - Pela Barra de Status:**
1. Clique no ícone de **seta para baixo** (se houver mudanças)
2. Confirme o Pull

**Método 2 - Pelo Source Control:**
1. Menu `...` → **Pull**

**Método 3 - Pelo Command Palette:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Pull`

### 5.3 Sync (Push + Pull Automático)

**Pela Barra de Status:**
1. Clique no ícone **↻** (Sync Changes)
2. Isso faz Pull e Push de uma vez

### 5.4 Publicar Branch Nova no GitHub

Quando criar uma branch nova localmente:

1. Faça o primeiro commit
2. No **Source Control**, clique em **Publish Branch**
3. A branch será criada no GitHub automaticamente

---

## 👥 6. Workflow para Dois Desenvolvedores

### 6.1 Cenário Real: João e Maria

**João** trabalha em `index.html`  
**Maria** trabalha em `detalhes.html`

### 6.2 Passo a Passo - João (Visual)

**Segunda-feira - 9h**

1. **Atualizar branch main:**
   - Clique na branch (barra de status) → escolha `main`
   - Clique no ícone **↻ Sync**

2. **Criar nova branch:**
   - Clique na branch → **Create new branch**
   - Nome: `feature/filtros-avancados`

3. **Trabalhar no código:**
   - Abra `index.html`
   - Adicione filtros de busca

4. **Fazer commit:**
   - `Ctrl + Shift + G` (Source Control)
   - Clique no **+** ao lado de `index.html`
   - Mensagem: `feat: adiciona filtros avançados de busca`
   - Clique em **✓ Commit**

5. **Publicar no GitHub:**
   - Clique em **Publish Branch**

6. **Abrir Pull Request:**
   - Vá ao GitHub no navegador
   - Clique em **Compare & pull request**
   - Preencha descrição
   - Clique em **Create pull request**

### 6.3 Passo a Passo - Maria (Visual)

**Segunda-feira - 9h**

1. **Atualizar branch main:**
   - Branch → `main`
   - **↻ Sync**

2. **Criar nova branch:**
   - Branch → **Create new branch**
   - Nome: `feature/sistema-favoritos`

3. **Trabalhar no código:**
   - Abra `detalhes.html`
   - Adicione botão de favoritar

4. **Fazer commit e publicar:**
   - Stage → Commit → Publish Branch

5. **Abrir Pull Request no GitHub**

### 6.4 Atualizar Branch com Mudanças do Colega

**Situação:** João fez merge no `main`, Maria precisa atualizar sua branch.

**Maria faz (Visual):**

1. **Voltar para main:**
   - Clique na branch → `main`

2. **Puxar mudanças:**
   - Clique no **↻ Sync**

3. **Voltar para sua branch:**
   - Branch → `feature/sistema-favoritos`

4. **Mesclar main na sua branch:**
   - `Ctrl + Shift + P`
   - Digite: `Git: Merge Branch`
   - Escolha: `main`

5. **Se houver conflitos:**
   - VS Code mostrará arquivos com **C**
   - Veja seção de Resolução de Conflitos

6. **Enviar atualização:**
   - Clique no **↑ Push**

---

## 🔥 7. Resolvendo Conflitos

### 7.1 Identificando Conflitos

Após fazer **Merge** ou **Pull**, se houver conflitos:

- Arquivos com **C** aparecem no Source Control
- VS Code abre automaticamente os arquivos

### 7.2 Interface de Resolução

O arquivo mostrará algo assim:

```html
<<<<<<< HEAD (Current Change)
<h1>Título da sua versão</h1>
=======
<h1>Título da versão remota</h1>
>>>>>>> feature/outra-branch (Incoming Change)
```

### 7.3 Botões de Resolução

Acima do conflito, verá 4 botões:

1. **Accept Current Change** - Mantém sua versão
2. **Accept Incoming Change** - Usa a versão do outro dev
3. **Accept Both Changes** - Mantém ambas as versões
4. **Compare Changes** - Abre comparação lado a lado

### 7.4 Resolução Manual

Se preferir resolver manualmente:

1. Apague as linhas:
   - `<<<<<<< HEAD`
   - `=======`
   - `>>>>>>> feature/outra-branch`

2. Mantenha apenas o código correto final

**Exemplo de resolução:**

```html
<h1>PetClassificados - Adote ou Encontre seu Pet</h1>
```

### 7.5 Finalizar Resolução (Visual)

1. **Salve o arquivo** (`Ctrl + S`)
2. **Source Control** → Clique no **+** do arquivo resolvido
3. Escreva mensagem: `fix: resolve conflito de merge`
4. Clique em **✓ Commit**

### 7.6 Usar Merge Editor (VS Code 2022+)

Para conflitos complexos:

1. Quando aparecer conflito, clique em **Resolve in Merge Editor**
2. Verá 3 colunas:
   - **Incoming:** Mudanças do outro dev
   - **Current:** Suas mudanças
   - **Result:** Resultado final
3. Clique nas caixas de seleção para aceitar mudanças
4. Clique em **Complete Merge**

---

## 🧩 8. Extensões Essenciais

### 8.1 GitLens

**Instalar:**
1. `Ctrl + Shift + X` (Extensions)
2. Busque: **GitLens**
3. Clique em **Install**

**Funcionalidades:**
- Ver quem modificou cada linha (Git Blame)
- Histórico de commits visual
- Comparar branches facilmente
- Detalhes ao passar mouse sobre código

**Usar:**
- Abra qualquer arquivo
- Verá autor e data ao lado de cada linha
- Clique em **GitLens** na barra lateral para ver histórico

### 8.2 Git Graph

**Instalar:**
1. Extensions → **Git Graph**
2. Install

**Usar:**
1. Abra **Source Control**
2. Clique no ícone **View Git Graph** (topo do painel)
3. Verá gráfico visual de todas as branches e commits

**Funcionalidades:**
- Ver histórico visual de commits
- Comparar branches
- Fazer checkout clicando na branch
- Ver detalhes do commit

### 8.3 Git History

**Instalar:**
1. Extensions → **Git History**
2. Install

**Usar:**
1. Clique com botão direito em qualquer arquivo
2. Selecione: **Git: View File History**
3. Verá todos os commits que modificaram aquele arquivo

### 8.4 GitHub Pull Requests

**Instalar:**
1. Extensions → **GitHub Pull Requests and Issues**
2. Install

**Funcionalidades:**
- Ver Pull Requests diretamente no VS Code
- Revisar código
- Aprovar ou solicitar mudanças
- Fazer merge

**Usar:**
1. Clique no ícone **GitHub** na barra lateral
2. Faça login no GitHub
3. Verá lista de PRs abertos
4. Clique para revisar

---

## ⌨️ 9. Atalhos de Teclado

### 9.1 Principais Atalhos

| Ação | Windows/Linux | Mac |
|------|---------------|-----|
| Abrir Source Control | `Ctrl + Shift + G` | `Cmd + Shift + G` |
| Command Palette | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| Commit (após escrever mensagem) | `Ctrl + Enter` | `Cmd + Enter` |
| Abrir Terminal | `` Ctrl + ` `` | `` Cmd + ` `` |
| Abrir Extensions | `Ctrl + Shift + X` | `Cmd + Shift + X` |
| Ver diff do arquivo | Clique no arquivo | Clique no arquivo |
| Stage arquivo | `Ctrl + Enter` (no arquivo) | `Cmd + Enter` |

### 9.2 Comandos via Command Palette

Digite `Ctrl + Shift + P` e depois:

- `Git: Create Branch` - Criar branch
- `Git: Checkout to` - Trocar branch
- `Git: Merge Branch` - Mesclar branch
- `Git: Push` - Enviar commits
- `Git: Pull` - Baixar commits
- `Git: Stash` - Guardar mudanças temporariamente
- `Git: Sync` - Push + Pull

---

## 💡 10. Dicas e Boas Práticas

### 10.1 Antes de Começar o Dia

1. **Sempre atualize o main:**
   - Branch → `main`
   - **↻ Sync**

2. **Crie branch para sua tarefa:**
   - Nome descritivo: `feature/nome-funcionalidade`

### 10.2 Durante o Trabalho

- **Commits pequenos e frequentes**
- **Mensagens claras** (use Conventional Commits)
- **Revise o diff** antes de commitar
- **Não comite arquivos temporários** (.log, .tmp, etc.)

### 10.3 Antes de Fazer Push

1. **Veja suas mudanças:**
   - Source Control → clique nos arquivos
   - Verifique se está tudo correto

2. **Teste seu código:**
   - Abra o HTML no navegador
   - Teste funcionalidades

### 10.4 Trabalhando em Equipe

- **Combine nomes de branches** com seu colega
- **Use prefixos:**
  - `feature/` - Novas funcionalidades
  - `fix/` - Correções
  - `style/` - Mudanças visuais
  - `refactor/` - Refatoração

- **Pull Requests:**
  - Descreva o que fez
  - Adicione screenshots se mudou visual
  - Peça revisão do colega

### 10.5 O Que NUNCA Fazer

❌ **Trabalhar direto na branch `main`**  
❌ **Fazer push sem testar**  
❌ **Commitar com mensagens vagas ("fix", "update")**  
❌ **Forçar push (`push --force`) sem necessidade**  
❌ **Deletar branches de outros desenvolvedores**  
❌ **Fazer merge sem revisar conflitos**

### 10.6 Checklist Diário

**Início do dia:**
- [ ] Abri VS Code
- [ ] Fui para branch `main`
- [ ] Fiz Sync para atualizar
- [ ] Criei/voltei para minha branch de trabalho

**Durante o trabalho:**
- [ ] Faço commits pequenos
- [ ] Escrevo mensagens claras
- [ ] Reviso diff antes de commitar
- [ ] Testo antes de fazer push

**Fim do dia:**
- [ ] Fiz push de todos os commits
- [ ] Abri Pull Request (se feature completa)
- [ ] Avisei o colega sobre mudanças

---

## 🚨 Resolução de Problemas

### Problema: "Não consigo fazer Push"

**Solução:**
1. Clique no **↻ Sync** para fazer Pull primeiro
2. Resolva conflitos se houver
3. Tente Push novamente

### Problema: "Mudei de branch e perdi minhas alterações"

**Solução:**
1. `Ctrl + Shift + P`
2. Digite: `Git: Stash`
3. Escolha: `Pop Latest Stash`

### Problema: "Comitei no arquivo errado"

**Solução:**
1. Source Control → Menu `...`
2. **Commit** → **Undo Last Commit**
3. Suas mudanças voltam para Changes

### Problema: "Não vejo o ícone Source Control"

**Solução:**
1. `View` → `SCM` (Source Control)
2. Ou pressione `Ctrl + Shift + G`

### Problema: "Branch não aparece no GitHub"

**Solução:**
1. Faça commit na branch
2. Clique em **Publish Branch**
3. Aguarde sincronização

---

## 📚 Recursos Visuais do VS Code

### Elementos da Interface Git

```
BARRA LATERAL ESQUERDA:
├── 📄 Explorer (Arquivos)
├── 🔍 Search (Busca)
├── 🌿 Source Control ← PRINCIPAL PARA GIT
├── ▶️ Run and Debug
└── 🧩 Extensions

BARRA DE STATUS (Inferior):
├── 🌿 main ← BRANCH ATUAL (clicável)
├── ↻ 2↓ 1↑ ← SYNC (2 commits para baixar, 1 para subir)
├── ⚠️ 0 🛑 0 ← Erros e avisos
└── Ln 45, Col 12 ← Linha e coluna

PAINEL SOURCE CONTROL:
├── 💬 Message ← Escrever mensagem de commit
├── ✓ Commit ← Botão de commit
├── 📝 Changes ← Arquivos modificados
│   ├── M index.html ← Modified
│   └── A novo.html ← Added
└── 📌 Staged Changes ← Prontos para commit
```

---

## 🎓 Workflow Recomendado Completo

### Passo a Passo para o Projeto PetClassificados

**1. Configuração Inicial (Uma vez):**
1. Instale Git
2. Configure nome e email
3. Clone ou abra projeto no VS Code
4. Conecte com GitHub

**2. Início de Nova Funcionalidade:**
1. Branch → `main`
2. **↻ Sync**
3. Create new branch → `feature/minha-funcionalidade`

**3. Desenvolvimento:**
1. Modifique arquivos (`index.html`, `detalhes.html`, etc.)
2. Salve (`Ctrl + S`)
3. Veja mudanças no Source Control
4. Clique em arquivos para ver diff

**4. Commit:**
1. Source Control (`Ctrl + Shift + G`)
2. Clique no **+** nos arquivos (Stage)
3. Escreva mensagem: `feat: adiciona sistema de favoritos`
4. **✓ Commit** (ou `Ctrl + Enter`)

**5. Enviar para GitHub:**
1. **Publish Branch** (primeira vez)
2. Ou clique no **↑** (Push)

**6. Pull Request:**
1. Abra GitHub no navegador
2. **Compare & pull request**
3. Descreva mudanças
4. **Create pull request**

**7. Após Aprovação:**
1. Merge no GitHub
2. Volte ao VS Code
3. Branch → `main`
4. **↻ Sync**

**8. Limpar:**
1. `Ctrl + Shift + P`
2. `Git: Delete Branch`
3. Escolha branch antiga

---

## ✅ Conclusão

Este tutorial cobriu **100% da interface visual do VS Code** para trabalhar com Git. Você aprendeu:

✅ Configurar Git e GitHub  
✅ Criar e gerenciar branches visualmente  
✅ Fazer commits usando interface gráfica  
✅ Sincronizar com GitHub (Push/Pull)  
✅ Resolver conflitos com botões  
✅ Trabalhar em equipe (workflow para 2 devs)  
✅ Usar extensões (GitLens, Git Graph)  
✅ Atalhos de teclado úteis  

**Você não precisa digitar comandos de terminal!** Tudo pode ser feito clicando em botões e menus.

---

## 📞 Dúvidas?

Se tiver problemas:
1. Consulte a seção "Resolução de Problemas"
2. Use o Command Palette (`Ctrl + Shift + P`) e busque por "Git"
3. Veja a documentação oficial: [VS Code Git Docs](https://code.visualstudio.com/docs/sourcecontrol/overview)

**Bom trabalho no PetClassificados! 🐶🐱**
