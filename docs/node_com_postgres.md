### Instalando Node.js

1. **Atualize o sistema:**
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```

2. **Instale Node.js usando o NodeSource (recomendado):**
   - Primeiro, adicione o repositório do NodeSource:
     ```bash
     curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
     ```
   - Em seguida, instale o Node.js:
     ```bash
     sudo apt install -y nodejs
     ```

3. **Verifique a instalação do Node.js e npm:**
   ```bash
   node -v
   npm -v
   ```

### Instalando PostgreSQL

1. **Atualize o sistema (se não feito antes):**
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```

2. **Instale PostgreSQL:**
   ```bash
   sudo apt install -y postgresql postgresql-contrib
   ```

3. **Inicie o serviço PostgreSQL:**
   ```bash
   sudo systemctl start postgresql
   sudo systemctl enable postgresql
   ```

4. **Acesse o PostgreSQL:**
   - Mude para o usuário `postgres`:
     ```bash
     sudo -i -u postgres
     ```
   - Abra o shell do PostgreSQL:
     ```bash
     psql
     ```

5. **Configuração inicial (opcional):**
   - Crie uma nova senha para o usuário `postgres`:
     ```sql
     \password postgres
     ```
   - Saia do shell do PostgreSQL:
     ```sql
     \q
     ```
   - Saia do usuário `postgres`:
     ```bash
     exit
     ```

### Verificando a instalação

1. **Verifique a instalação do PostgreSQL:**
   ```bash
   psql --version
   ```

2. **Verifique se o serviço PostgreSQL está ativo:**
   ```bash
   sudo systemctl status postgresql
   ```

### Conexão ao PostgreSQL

Para conectar-se ao PostgreSQL e começar a usar, você pode usar o seguinte comando:
```bash
sudo -u postgres psql
```

Ou, para se conectar a um banco de dados específico:
```bash
sudo -u postgres psql -d nome_do_banco
```

### Ferramentas Adicionais

Você pode instalar algumas ferramentas adicionais para facilitar o uso:

1. **pgAdmin (Interface gráfica para PostgreSQL):**
   - Adicione o repositório do pgAdmin:
     ```bash
     curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add -
     sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/focal pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list'
     sudo apt update
     ```
   - Instale o pgAdmin:
     ```bash
     sudo apt install pgadmin4
     ```
   - Configuração inicial:
     ```bash
     sudo /usr/pgadmin4/bin/setup-web.sh
     ```