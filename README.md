
# 🧰 Guia Prático de Comandos Git

Este documento reúne os principais comandos utilizados no Git, com exemplos, explicações e dicas para iniciantes.

---

## ✅ Configurações Iniciais

### Definir nome e e-mail do usuário (globalmente)
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

### Ver nome e e-mail configurados
```bash
git config user.name
git config user.email
```

### Ver ou definir o nome padrão para novas branches
```bash
git config init.defaultBranch        # mostra o padrão atual
git config --global init.defaultBranch main   # define 'main' como padrão
```

### Listar todas as configurações Git salvas
```bash
git config --global --list
```

---

## ☁️ Conectar ao Repositório Remoto

1. Crie um repositório no GitHub.
2. Copie a URL HTTPS (ex: `https://github.com/seu-usuario/seu-repositorio.git`).
3. Execute:
```bash
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
```

> `origin` é um nome padrão para o repositório remoto. Pode ser outro nome, mas é recomendado manter `origin`.

---

## 📄 Criação e Manipulação de Arquivos

### Criar arquivos
```bash
touch README.md                     # cria um arquivo vazio
echo "Hello World" > arquivo.txt    # cria ou sobrescreve conteúdo
echo "Nova linha" >> arquivo.txt    # adiciona ao final do arquivo
```

### Remover arquivos ou diretórios
```bash
rm arquivo.txt
rm -rf nome-da-pasta/
```

---

## 📥 Controle de Versão

### Adicionar arquivos ao stage
```bash
git add nome_do_arquivo
git add .             # adiciona todas as alterações
```

### Criar commit
```bash
git commit -m "mensagem descritiva do que foi feito"
```

### Ver histórico de commits
```bash
git log
```

### Ver status atual do repositório
```bash
git status
```

---

## 🔁 Desfazendo Alterações

### Restaurar um arquivo ao último estado salvo (`add` ou `commit`)
```bash
git restore nome_do_arquivo
```

### Alterar a mensagem do último commit
```bash
git commit --amend -m "nova mensagem"
```

### Resetar commits (atenção: pode apagar histórico!)

- **--soft**: desfaz commits, mantém staging (`git add`)
- **--mixed**: desfaz commits e staging, mantém alterações no código
- **--hard**: apaga tudo (commits e alterações locais)

```bash
git reset --soft hash-do-commit
git reset --mixed hash-do-commit
git reset --hard hash-do-commit
```

> Para encontrar o hash do commit, use `git log`.

---

## 🚀 Enviar e Receber Alterações

### Enviar commits para o GitHub
```bash
git push -u origin main
```

### Baixar alterações do repositório remoto
```bash
git pull
```

---

## 🌿 Branches (Ramificações)

### Criar e mudar para nova branch
```bash
git checkout -b nome-da-branch
```

### Trocar de branch
```bash
git checkout nome-da-branch
```

### Ver todas as branches
```bash
git branch
```

### Mesclar uma branch com a atual
```bash
git merge nome-da-branch
```

### Excluir branch
```bash
git branch -d nome-da-branch
```

---

## ⚔️ Se Der Conflito...

Conflitos acontecem quando duas branches alteram a mesma parte de um arquivo. Veja como resolver:

### 🔁 Exemplo de conflito:
```bash
git merge nome-da-branch
```

Você verá uma mensagem como:
```
CONFLICT (content): Merge conflict in arquivo.java
Automatic merge failed; fix conflicts and then commit the result.
```

### ✅ Passo a passo para resolver:

1. **Abra os arquivos com conflito**
   - O Git marcará os trechos assim:
     ```java
     <<<<<<< HEAD
     código da sua branch atual
     =======
     código da branch que você está mesclando
     >>>>>>> nome-da-branch
     ```

2. **Edite manualmente** o arquivo e remova os marcadores (`<<<<<<<`, `=======`, `>>>>>>>`).

3. **Depois de resolver:**
   ```bash
   git add arquivo-resolvido
   git commit -m "resolvendo conflito de merge"
   ```

> Dica: editores como VS Code ajudam muito com conflitos, oferecendo botões como “Aceitar ambos” ou “Aceitar atual”.

---

## 🧰 Outros Comandos Úteis

### Ver diferenças entre arquivos alterados e últimos commits
```bash
git diff
```

### Clonar um repositório existente
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

### Inicializar repositório Git local
```bash
git init
```

---

## 📌 Dicas Finais

- Faça commits pequenos e frequentes.
- Escreva mensagens de commit claras.
- Use branches para organizar o desenvolvimento de features, correções ou testes.

---

✍️ **Feito por murilocamargo05**

> Use este arquivo como referência rápida para seus projetos com Git!
