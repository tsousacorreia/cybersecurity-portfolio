# 📘 File permissions in Linux (Laboratório de Segurança)

## 🔹 Lab description
O objetivo deste laboratório é explorar e modificar as permissões de arquivos e diretórios em um sistema Linux de acordo com o [cenário proposto](file-permissions-scenario.md).

Como profissional de segurança em uma organização, é essencial garantir que apenas usuários autorizados tenham acesso a determinados arquivos e pastas.

Atividades a serem realizadas neste laboratório:

- Criar uma estrutura de diretórios simulando um ambiente real.
- Verificar as permissões padrão de arquivos e diretórios.
- Interpretar a string de permissões exibida com **ls -la**.
- Usar o comando **chmod** para modificar as permissões conforme necessário.
- Trabalhar com arquivos ocultos e diretórios para reforçar a segurança.

---

## 📂 Create a directory structure

Antes de gerenciar as permissões, foi necessário criar o ambiente.

### Step 1: Create the working directory
```bash
mkdir ~/pesquisa
cd ~/pesquisa
```

### Step 2: Create visible files
```bash
touch relatorio.txt dados.csv script.sh
```

### Step 3: Create hidden files
```bash
touch .confidencial.txt .config
```

### Step 4: Create a hidden directory and hidden files inside it
```bash
mkdir .oculto
cd .oculto
touch nota.txt info.log  # arquivos visíveis dentro da pasta oculta
```
---

## 🔍 Check file and directory details

Comando para verificar as informações detalhadas:
```bash
ls -la ~/pesquisa
```
O comando **ls -la** lista todos os arquivos, inclusive ocultos (**-a**), e exibe permissões, proprietários e grupos (**-l**).

Exemplo de saída:
```
-rw-rw-r--  1 usuario grupo    0 Apr 19 14:02 .confidencial.txt
-rw-rw-r--  1 usuario grupo    0 Apr 19 14:02 .config
-rw-rw-r--  1 usuario grupo    0 Apr 19 14:01 dados.csv
drwxrwxr-x  2 usuario grupo 4096 Apr 19 14:03 .oculto
-rw-rw-r--  1 usuario grupo    0 Apr 19 14:01 relatorio.txt
-rw-rw-r--  1 usuario grupo    0 Apr 19 14:01 script.sh
```

---

## 🔡 Describe the permissions string

A cadeia de 10 caracteres ( **drwxrwxrwx** ) funciona assim:

- O **1º caractere** indica o tipo (**-** arquivo, **d** diretório).
- Os 3 caracteres após o 1º representam permissões do **usuario**: **r** (read), **w** (write), **x** (execute).
- Os próximos 3 são para o **grupo**: **r** (read), **w** (write), **x** (execute).
- Os últimos 3 são para **outros**: **r** (read), **w** (write), **x** (execute).

_Exemplo:_ **-rw-r--r--**
- Permissões referente a um **arquivo**: **-**
- **Usuário** pode ler e escrever: **rw-**
- **Grupo** pode ler: **r--**
- **Outros** podem ler: **r--**

---

## 🛠️ How to use `chmod`

Aqui uma breve explicação de como utilizar o comando `chmod`.

Existem duas maneiras principais de usar o comando `chmod` para modificar permissões de arquivos e diretórios:

**Modo simbólico**

Utiliza letras para representar categorias de usuários e tipos de permissão.

    u: usuário (owner)

    g: grupo

    o: outros

    a: todos

    r: leitura

    w: escrita

    x: execução

Símbolos:

    +: adiciona permissão

    -: remove permissão

    =: define permissão

Exemplos:

```
chmod u+x arquivo.txt       # adiciona execução para o usuário
chmod go-w arquivo.txt      # remove escrita do grupo e outros
chmod a+r arquivo.txt       # adiciona leitura para todos
```


**Modo absoluto**

Utiliza números octais (0-7) para definir permissões de forma direta.

```
Valor   |   Permissão   |   Significado
  0     |     ---       |   Sem permissão
  1     |     --x       |   Executar
  2     |     -w-       |   Escrever
  3     |     -wx       |   Escrever + Executar
  4     |     r--       |   Ler
  5     |     r-x       |   Ler + Executar
  6     |     rw-       |   Ler + Escrever
  7     |     rwx       |   Total (leitura, escrita e execução)
```

**Exemplos:**

```
chmod 644 arquivo.txt   # rw-r--r--
chmod 700 arquivo.txt   # rwx------
chmod 440 arquivo.txt   # r--r-----
```

É possível usar a opção de modo recursivo (**-R**) no comando `chmod` para alterar as permissões de todos os arquivos num diretório e subdiretórios. 

```
chmod -R 700 pasta/     # altera permissões da pasta e tudo dentro
```
📌 **Nota**: Em diretórios, a permissão **x** (execução) permite o acesso ao conteúdo do diretório. Sem ela, mesmo que o diretório seja "legível" (**r**), não será possível navegar por ele.

---

## 🔐 Change file permissions

Aqui foi removida a permissão de escrita para **outros** nos arquivos visiveis:

```bash
chmod o-w ~/pesquisa/*
```

- **chmod** altera permissões.
- **o-w** remove permissão de escrita de "others".
- **_*_** aplica em todos os arquivos não ocultos.

Isso garante que nenhum usuário fora do usuário ou grupo do arquivo possa gravar nesses arquivos.

---

## 🕵️ Change file permissions on a hidden file

Os arquivos ocultos devem ser legíveis somente pelo usuário e pelo grupo, e não graváveis ​​por ninguém:

```bash
chmod u-w,g-w,o-r ~/pesquisa/.confidencial.txt
chmod u-w,g-w,o-r ~/pesquisa/.config
```

- **chmod u-w,g-w,o-r** define: somente usuario e grupo têm leitura, ninguém tem escrita ou execução.

---

## 🔐 Change directory permissions

Para o diretório .oculto e seu conteúdo, apenas o usuário poderá acessar:

```bash
chmod -R 700 ~/pesquisa/.oculto
```
- **-R** aplica recursivamente.
- **700** somente o usuário pode ler, escrever e acessar.

Isso concede permissões de leitura, gravação e execução somente ao usuário e nenhum acesso ao grupo ou outros.

---

## 📋 Check updated permissions

Para verificar novamente após todas as alterações:

```
ls -la ~/pesquisa
ls -la ~/pesquisa/.oculto
```

Ou, para checar permissões específicas:
```
stat relatorio.txt
```

---

## ✅ Summary

Neste laboratório, configuramos um ambiente Linux com diretórios e arquivos (visíveis e ocultos) e aplicamos práticas recomendadas de segurança:

- Listamos permissões com `ls -la`
- Interpretamos a cadeia de permissões de 10 caracteres
- Usamos `chmod` para remover permissões de escrita de "others"
- Garantimos que arquivos ocultos são somente leitura para usuário e grupo
- Protegemos o diretório oculto com permissão exclusiva para o usuário

Essas práticas ajudaram a manter a integridade e segurança dos dados dentro do sistema Linux no ambiente proposto.