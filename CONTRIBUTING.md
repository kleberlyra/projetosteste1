# Guia de Contribuição - PetClassificados

Obrigado por considerar contribuir com o PetClassificados! Este documento contém as diretrizes e melhores práticas para colaborar no projeto.

## 📋 Índice

- [Código de Conduta](#código-de-conduta)
- [Como Começar](#como-começar)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Workflow de Desenvolvimento](#workflow-de-desenvolvimento)
- [Padrões de Código](#padrões-de-código)
- [Commits](#commits)
- [Pull Requests](#pull-requests)
- [Divisão de Responsabilidades](#divisão-de-responsabilidades)

## 📜 Código de Conduta

- Seja respeitoso e profissional
- Aceite críticas construtivas
- Foque no que é melhor para o projeto
- Ajude outros colaboradores

## 🚀 Como Começar

### 1. Clone o Repositório

```bash
git clone https://github.com/seu-usuario/pet-classificados.git
cd pet-classificados
```

### 2. Configure o Git

```bash
git config user.name "Seu Nome"
git config user.email "seu.email@exemplo.com"
```

### 3. Crie uma Branch para sua Feature

```bash
git checkout -b feature/nome-da-funcionalidade
```

## 📁 Estrutura do Projeto

```
pet-classificados/
├── index.html              # Página principal (listagem de pets)
├── detalhes.html           # Página de detalhes do anúncio
├── css/                    # Arquivos CSS customizados (futuro)
├── js/                     # Scripts JavaScript (futuro)
├── assets/                 # Imagens e recursos (futuro)
├── CONTRIBUTING.md         # Este arquivo
└── README.md              # Documentação do projeto
```

## 🔄 Workflow de Desenvolvimento

### Branch Strategy

Usamos o **GitHub Flow** simplificado:

```
main (branch principal - sempre estável)
  ↓
feature/nome-da-funcionalidade (suas mudanças)
  ↓
Pull Request → Code Review → Merge
```

### Passos para Contribuir

1. **Atualize o main**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Crie uma branch**
   ```bash
   git checkout -b feature/sua-funcionalidade
   ```

3. **Faça suas mudanças**
   - Desenvolva a funcionalidade
   - Teste localmente
   - Documente se necessário

4. **Commit suas mudanças**
   ```bash
   git add .
   git commit -m "feat: descrição clara da mudança"
   ```

5. **Atualize com o main (se necessário)**
   ```bash
   git checkout main
   git pull origin main
   git checkout feature/sua-funcionalidade
   git merge main
   ```

6. **Envie para o repositório**
   ```bash
   git push origin feature/sua-funcionalidade
   ```

7. **Abra um Pull Request**
   - Vá no GitHub
   - Clique em "New Pull Request"
   - Descreva suas mudanças
   - Aguarde revisão

## 💻 Padrões de Código

### HTML

```html
<!-- ✅ BOM -->
<div class="card pet-card h-100">
    <div class="card-body">
        <h5 class="card-title">Título</h5>
    </div>
</div>

<!-- ❌ RUIM -->
<div class="card pet-card h-100"><div class="card-body"><h5 class="card-title">Título</h5></div></div>
```

**Regras:**
- Use indentação de 4 espaços
- Sempre feche as tags
- Use aspas duplas para atributos
- Mantenha a estrutura organizada e legível
- Use nomes de classes semânticos

### CSS

```css
/* ✅ BOM */
.pet-card {
    transition: transform 0.3s, box-shadow 0.3s;
    border-radius: 10px;
}

.pet-card:hover {
    transform: translateY(-5px);
}

/* ❌ RUIM */
.pet-card{transition:transform 0.3s,box-shadow 0.3s;border-radius:10px;}
```

**Regras:**
- Use indentação de 4 espaços
- Uma propriedade por linha
- Agrupe seletores relacionados
- Use nomes descritivos em português
- Prefira classes a IDs

### JavaScript

```javascript
// ✅ BOM
function changeImage(thumb) {
    const mainImage = document.getElementById('mainImage');
    const allThumbs = document.querySelectorAll('.thumb-image');
    
    allThumbs.forEach(img => img.classList.remove('active'));
    thumb.classList.add('active');
}

// ❌ RUIM
function changeImage(thumb){const mainImage=document.getElementById('mainImage');const allThumbs=document.querySelectorAll('.thumb-image');allThumbs.forEach(img=>img.classList.remove('active'));thumb.classList.add('active');}
```

**Regras:**
- Use `const` e `let`, evite `var`
- Nomes de funções em camelCase
- Indentação de 4 espaços
- Comentários quando necessário
- Use arrow functions quando apropriado

### Bootstrap

- Use classes utilitárias do Bootstrap 5
- Mantenha consistência com o design existente
- Evite CSS customizado quando possível
- Use o sistema de grid responsivo

## 📝 Commits

### Formato do Commit

Use o padrão **Conventional Commits**:

```
tipo(escopo): descrição curta

[corpo opcional]

[rodapé opcional]
```

### Tipos de Commit

- `feat`: Nova funcionalidade
- `fix`: Correção de bug
- `docs`: Documentação
- `style`: Formatação, ponto e vírgula, etc
- `refactor`: Refatoração de código
- `test`: Adição de testes
- `chore`: Tarefas de manutenção

### Exemplos

```bash
# Boa prática
feat: adiciona filtro por raça na página inicial
fix: corrige bug no carrossel de imagens
docs: atualiza README com instruções de instalação
style: ajusta espaçamento dos cards de pets
refactor: reorganiza estrutura de pastas

# Evite
git commit -m "mudanças"
git commit -m "fix"
git commit -m "atualizações várias"
```

### Regras de Commit

✅ **Fazer:**
- Commits pequenos e focados
- Mensagens claras e descritivas
- Um commit por mudança lógica
- Escrever em português
- Começar com verbo no imperativo

❌ **Evitar:**
- Commits gigantes com múltiplas mudanças
- Mensagens vagas tipo "fix" ou "update"
- Commitar código não testado
- Commitar arquivos temporários

## 🔀 Pull Requests

### Antes de Abrir um PR

- [ ] Testei localmente
- [ ] Código segue os padrões do projeto
- [ ] Não há conflitos com a branch main
- [ ] Commits estão organizados e bem descritos

### Template do PR

```markdown
## Descrição
Breve descrição das mudanças realizadas.

## Tipo de Mudança
- [ ] Nova funcionalidade
- [ ] Correção de bug
- [ ] Melhoria de performance
- [ ] Refatoração
- [ ] Documentação

## Como Testar
1. Passo a passo para testar
2. O que deve ser observado
3. Comportamento esperado

## Screenshots (se aplicável)
[Adicione prints das mudanças visuais]

## Checklist
- [ ] Meu código segue os padrões do projeto
- [ ] Testei localmente
- [ ] Atualizei a documentação (se necessário)
- [ ] Não há conflitos com main
```

### Code Review

- Todo PR precisa de pelo menos 1 aprovação
- Responda aos comentários de forma construtiva
- Faça as alterações solicitadas
- Discuta discordâncias de forma respeitosa

## 👥 Divisão de Responsabilidades

### Desenvolvedor 1 (Frontend - Listagem)
**Responsável por:** `index.html` e funcionalidades relacionadas

- ✅ Hero section e busca
- ✅ Sistema de filtros
- ✅ Cards de listagem de pets
- ✅ Paginação
- ✅ Navbar e Footer
- ✅ Responsividade da home

### Desenvolvedor 2 (Frontend - Detalhes)
**Responsável por:** `detalhes.html` e funcionalidades relacionadas

- ✅ Galeria de imagens
- ✅ Informações detalhadas do pet
- ✅ Sistema de perguntas e respostas
- ✅ Cards do anunciante
- ✅ Anúncios relacionados
- ✅ Responsividade dos detalhes

### Áreas Compartilhadas
**Ambos podem contribuir:**

- 📋 Documentação (README, CONTRIBUTING)
- 🐛 Correção de bugs
- ♿ Acessibilidade
- 🎨 Melhorias de design
- 🔧 Configurações gerais

## 🐛 Reportando Bugs

Ao encontrar um bug, abra uma **Issue** com:

```markdown
## Descrição do Bug
Descrição clara do problema

## Como Reproduzir
1. Vá para '...'
2. Clique em '...'
3. Role até '...'
4. Veja o erro

## Comportamento Esperado
O que deveria acontecer

## Screenshots
Se aplicável

## Ambiente
- Navegador: [Chrome, Firefox, etc]
- Versão: [22]
- Sistema Operacional: [Windows, Mac, Linux]
```

## ✨ Sugerindo Melhorias

Para sugerir uma melhoria, abra uma **Issue** com:

```markdown
## Descrição da Melhoria
Descrição clara da funcionalidade sugerida

## Motivação
Por que essa melhoria é útil?

## Alternativas Consideradas
Outras formas de implementar

## Informações Adicionais
Mockups, exemplos, etc
```

## ❓ Dúvidas

- Abra uma **Issue** com a tag `question`
- Entre em contato pelo [seu-email@exemplo.com]
- Consulte a documentação no README.md

## 📚 Recursos Úteis

- [Bootstrap 5 Docs](https://getbootstrap.com/docs/5.3/)
- [Bootstrap Icons](https://icons.getbootstrap.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)

---

**Obrigado por contribuir com o PetClassificados! 🐾**
