# Guia Completo de Git & GitHub para Pop!_OS 🚀

Este README reúne **todo o conteúdo que estudamos** sobre Git e GitHub: instalação, configuração, SSH, comandos essenciais, workflows e envio de projetos ao GitHub.

---

## 📌 1️⃣ O que é Git?

Git é um **sistema de controle de versão** que:

* Armazena histórico de alterações do seu projeto
* Permite trabalhar em equipe de forma segura
* Possibilita voltar para versões anteriores
* Facilita colaboração com branches e merges

📌 Git trabalha localmente no seu PC.

---

## 🌍 2️⃣ O que é GitHub?

GitHub é uma plataforma online que:

* Hospeda seus repositórios Git
* Permite colaboração remota
* Fornece ferramentas de gestão de código, issues e deploys

📌 GitHub trabalha remotamente na nuvem.

---

## 🛠️ 3️⃣ Instalando o Git no Pop!_OS

```bash
sudo apt update
sudo apt install git
```

Verificar instalação:

```bash
git --version
```

---

## ⚙️ 4️⃣ Configurações iniciais do Git

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
git config --list
```

---

## 🔑 5️⃣ Criando e configurando SSH com GitHub

### Gerar chave SSH

```bash
ssh-keygen -t ed25519 -C "seuemail@example.com"
```

Pressione **Enter** em tudo.

### Iniciar agente e adicionar chave

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Copiar chave para o GitHub

```bash
cat ~/.ssh/id_ed25519.pub
```

No GitHub → **Settings → SSH and GPG keys → New SSH Key**

📌 Testar conexão:

```bash
ssh -T git@github.com
```

Se aparecer “successfully authenticated”, tá top! 😎

---

## 🌱 6️⃣ Criando Repositórios

📍 Criar localmente:

```bash
mkdir meu-projeto
cd meu-projeto
git init
```

📍 Criar no GitHub através da interface e conectar usando:

```bash
git remote add origin git@github.com:Usuario/Repositorio.git
```

---

## 📤 7️⃣ Subindo arquivos para o GitHub

```bash
git add .
git commit -m "Minha primeira versão"
git branch -M main
git push -u origin main
```

---

## 🔄 8️⃣ Atualizando repositório existente

📌 Baixar alterações do GitHub:

```bash
git pull origin main
```

Se houver históricos diferentes:

```bash
git pull origin main --allow-unrelated-histories
```

📌 Resolver conflitos → depois:

```bash
ESC
:wq
ENTER
```

📌 Enviar novas versões:

```bash
git add .
git commit -m "Update do projeto"
git push
```

---

## 🌿 9️⃣ Branches — Trabalhando com versões paralelas

Criar branch:

```bash
git checkout -b nova-feature
```

Trocar de branch:

```bash
git checkout main
```

Fazer merge após finalizar trabalho:

```bash
git merge nova-feature
```

Deletar branch após merge:

```bash
git branch -d nova-feature
```

---

## 📌 1️⃣0️⃣ Comandos Essenciais do Dia a Dia

| Comando               | Função                        |
| --------------------- | ----------------------------- |
| `git status`          | Ver estado dos arquivos       |
| `git log`             | Histórico de commits          |
| `git add .`           | Adiciona tudo para commit     |
| `git commit -m "msg"` | Salva alteração localmente    |
| `git push`            | Envia ao GitHub               |
| `git pull`            | Baixa atualizações do GitHub  |
| `git clone URL`       | Baixa um repositório da nuvem |

---

## 🧰 1️⃣1️⃣ Configurando HTTPS → SSH (opcional)

Ver origem remota:

```bash
git remote -v
```

Trocar para SSH:

```bash
git remote set-url origin git@github.com:Usuario/Repositorio.git
```

---

## 🌐 1️⃣2️⃣ Colocar Projeto Online com GitHub Pages

GitHub → Repositório → **Settings** → **Pages**
Selecione branch: `main` → `/root`

✔ Aguarde alguns segundos
🌍 Seu site estará no ar!

---

## 🎯 Conclusão

Agora você domina:
✔ Instalação e configuração do Git
✔ Conexão segura com SSH
✔ Controle de versão com commits
✔ Upload de projetos para o GitHub
✔ Resolução de conflitos
✔ Branches e colaboração
✔ Deploy com GitHub Pages

📌 Você está oficialmente trabalhando como **desenvolvedor Git profissional!** 🧑‍💻🔥

Se quiser, posso continuar te acompanhando com workflows avançados como:
🔹 Git Flow
🔹 Pull Requests
🔹 Code Review
🔹 Issues e Projects

É só chamar! 🚀🔥

## Atualizando Repositórios no GitHub Usando Terminal / VSCode

Quando você já tem um repositório conectado ao GitHub, o processo de atualização segue estes passos:

### 🔄 1️⃣ Certificar-se de que está na pasta do projeto

```bash
cd nome-do-seu-projeto
```

### 📌 2️⃣ Verificar o status — o que foi modificado?

```bash
git status
```

Isso mostra arquivos alterados, novos ou excluídos.

### ➕ 3️⃣ Adicionar as alterações para o commit

```bash
git add .
```

Ou selecionar arquivos específicos:

```bash
git add index.html estilo.css
```

### ✍️ 4️⃣ Criar o commit com uma mensagem descritiva

```bash
git commit -m "Atualizando layout da galeria"
```

### 🔁 5️⃣ Primeiro, sincronizar com o GitHub para evitar conflitos

```bash
git pull origin main
```

Se surgir um conflito, ele deve ser resolvido antes de continuar.

### 🚀 6️⃣ Enviar as modificações para o GitHub

```bash
git push origin main
```

Agora seu repositório remoto está atualizado! 🎉

---

### 🧠 Dicas úteis

| Situação                                          | Comando                       |
| ------------------------------------------------- | ----------------------------- |
| Criar commit rápido adicionando tudo              | `git commit -am "Mensagem"`   |
| Forçar reenvio sobrescrevendo remoto (⚠ perigoso) | `git push --force`            |
| Trocar para outra branch                          | `git checkout nome-da-branch` |
| Ver branches locais e remotas                     | `git branch -a`               |

---

Se quiser, posso adicionar imagens ilustrando o fluxo e até um diagrama mostrando como o **Git sincroniza Local ↔️ Remoto**. 😊

## 🔁 Fluxo do Git: Local ↔️ GitHub (Remote)

Para entender como o Git trabalha na prática, pense no fluxo de arquivos entre seu computador e o repositório remoto no GitHub:

```
┌────────────────────┐        git push        ┌─────────────────────┐
|  Repositório Local  | --------------------> |  Repositório Remoto  |
|  (seu PC / VSCode)  |                        |     (GitHub)         |
└────────────────────┘ <-------------------- └─────────────────────┘
                  git pull
```

📍 As ações mais comuns nesse fluxo:

* **git add** → prepara arquivos para commit
* **git commit** → salva as mudanças localmente
* **git pull** → sincroniza com atualizações do GitHub
* **git push** → envia atualizações para o GitHub

> Sempre que possível, faça `git pull` antes do `git push` para evitar conflitos.

---

## ⚔️ Resolvendo Conflitos de Merge

Conflitos acontecem quando duas versões do mesmo arquivo são alteradas de formas diferentes no GitHub e no seu PC.
Eles surgem normalmente após:

```bash
git pull origin main
```

Se houver conflito, o VSCode/Git mostrará algo assim dentro do arquivo afetado:

```
<<<<<< HEAD
(Seu código local)
=======
(Código do GitHub)
>>>>>> origin/main
```

### Como resolver

1️⃣ Editar manualmente escolhendo qual código manter (ou mesclar os dois)
2️⃣ Remover os marcadores `<<<<`, `====`, `>>>>`
3️⃣ Adicionar o arquivo corrigido:

```bash
git add nome-do-arquivo
```

4️⃣ Finalizar o merge:

```bash
git commit -m "Resolvendo conflito de merge"
```

5️⃣ Enviar ao GitHub:

```bash
git push origin main
```

---

### 💡 Dicas Importantes

* Faça commits pequenos → facilita entender conflitos
* Sempre sincronize antes de começar a trabalhar (`git pull`)
* Leia com calma o que foi alterado antes de decidir

Se quiser, posso adicionar **imagens visuais do VS Code** mostrando como resolver conflitos na interface, ou até uma **seção especial somente sobre Branches** para evitar conflitos no futuro. Quer que eu adicione também? 😄

## 🌿 Uso de Branches para Evitar Conflitos

Branches permitem desenvolver novas funcionalidades **sem alterar diretamente** o código principal (`main`).

### Criando e usando branches

```bash
git branch minha-feature     # cria uma nova branch
git checkout minha-feature  # muda para a nova branch
```

Ou criar e mudar ao mesmo tempo:

```bash
git checkout -b minha-feature
```

Após finalizar a alteração:

```bash
git add .
git commit -m "Nova funcionalidade"
```

### Enviando a branch para o GitHub

```bash
git push origin minha-feature
```

Então, você pode **abrir um Pull Request** no GitHub para revisar e **mesclar** com `main`.

### Fundindo (merge) a branch no main

```bash
git checkout main
git pull origin main
git merge minha-feature
```

> 💡 Trabalhar com branches reduz drasticamente conflitos e mantém o código principal limpo e estável.

---

## 🧩 Comandos Avançados do Git

| Comando                           | Descrição                                                   |
| --------------------------------- | ----------------------------------------------------------- |
| `git stash`                       | Guarda temporariamente alterações sem commitar              |
| `git stash pop`                   | Recupera o stash aplicado mais recente                      |
| `git log --oneline --graph`       | Visualiza histórico em formato resumido com gráfico         |
| `git diff`                        | Mostra diferenças entre versões de arquivo(s)               |
| `git checkout -- nome-do-arquivo` | Desfaz mudanças locais não commitadas                       |
| `git reset --hard`                | Restaura estado exato do último commit (⚠ perde alterações) |
| `git revert <hash>`               | Reverte um commit específico **sem apagar histórico**       |
| `git cherry-pick <hash>`          | Copia um commit específico para a branch atual              |
| `git tag`                         | Marca versões importantes do projeto                        |
| `git fetch`                       | Obtém alterações do remoto sem mesclar                      |

> 🛑 Sempre tenha cuidado com `reset --hard` e `push --force`: ambos podem causar perda de dados.

---

## 🤝 Boas Práticas de Versionamento em Equipe

🔹 **Use branches para cada tarefa** → organização e segurança

🔹 **Commits pequenos e frequentes** com mensagens claras

```
feat: adiciona menu responsivo
fix: corrige bug no formulário de login
style: melhora espaçamento dos cards
```

🔹 **Atualize a branch antes de trabalhar**

```bash
git pull origin main
```

🔹 **Revise o código de outros membros** via Pull Requests

* melhora a qualidade
* reduz bugs
* cria colaboração real

🔹 **Evite subir arquivos gigantes ou sensíveis**
Adicionar ao `.gitignore` sempre que necessário

🔹 **Organize o roadmap** com Issues e Projects do GitHub


