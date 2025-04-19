# 🔐 File Permissions Scenario

## 🧑‍💼 Cenário

Você é um **profissional de segurança** em uma **grande organização**. Seu trabalho é garantir que os usuários da **equipe de pesquisa** tenham **apenas as permissões adequadas** para acessar arquivos e diretórios. Isso é fundamental para manter a integridade e a segurança do sistema.

Sua responsabilidade inclui revisar e ajustar as permissões no sistema de arquivos sempre que necessário.

---

## 🎯 Objetivo

Avaliar e modificar as permissões dos arquivos e diretórios para garantir que estejam **de acordo com as políticas de segurança** da organização.

---

## 📋 Requisitos e regras de permissão

Durante este laboratório, siga as diretrizes abaixo:

1. **Nenhum usuário fora do proprietário ou do grupo** pode ter **permissão de escrita** em **qualquer arquivo**.

2. Os **arquivos ocultos** (iniciados com `.`):
   - Devem **ser legíveis** apenas pelo **usuário** e pelo **grupo**.
   - **Ninguém** deve ter permissão de escrita ou execução nesses arquivos.
   - Use o comando `chmod` para ajustar essas permissões.

3. O **diretório oculto** (e todos os arquivos dentro dele):
   - Deve ser **acessível apenas pelo proprietário**.
   - Nenhum outro usuário ou grupo deve conseguir acessar, ler ou modificar esses arquivos.
   - Use permissões **restritivas** com o comando `chmod -R`.

---

## 💻 Exemplo de comandos úteis

### 🧪 Resultado esperado

Ao final deste laboratório, o ambiente deve estar com permissões corretamente configuradas:

- **Arquivos comuns**: leitura e escrita apenas para o proprietário e grupo; sem escrita para outros.

- **Arquivos ocultos**: leitura para proprietário e grupo; nenhum acesso para outros.

- **Diretório oculto**: acesso total apenas para o usuário; sem acesso para grupo ou outros.

Este cenário simula uma situação real em ambientes corporativos, onde a **segurança da informação** e o **controle de acesso** são essenciais para proteger dados sensíveis e evitar violações.

🔗 [Acesse o relatório completo](file-permissions.md)