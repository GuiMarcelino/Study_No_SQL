# Instalação MongoDB no Ubuntu com Docker:

### Puxe a Imagem do MongoDB
```bash
docker pull mongo
```

### Criar a Imagem do MongoDB
```bash
docker run --name meu-mongo -d -p 27017:27017 mongo  
```

### Acessar o MongoDB via Docker
```bash
docker exec -it meu-mongo mongosh 
```

### Selecionar ou Criar a Base de Dados
```bash
use minhaBaseDeDados 
```

### Sair do Shell do MongoDB
```bash
quit() 
```

# Instalação do client Robo3T:

- Esse é um das interfaces mais utilizadas para trabalhar com MongoDB:

### Instalação via linha de comando(Ubuntu):
- Pacotes:
```bash
wget https://download-test.robomongo.org/linux/robo3t-1.3.1-linux-x86_64-7419c406.tar.gz
```

- Criar Path para o Robo3T:
```bash
mkdir -p /data/robo3t
```

- Extrair arquivos:
```bash
tar -xvzf robo3t-1.3.1-linux-x86_64-7419c406.tar.gz -C /data/robo3t
```

- Acessar Path:
```bash
cd /data/robot3t
```

- Iniciar app:
```bash
./robot3t
```

- Executar em segundo plano:
```bash
nohup./robot3t&
```
### Instalação com snap:

- Instalar via snap:
```bash
sudo snap instalar robo3t-snap
```

- Executar via snap:
```bash
robo3t
```

### Instalação via download:
- Site oficial: https://robomongo.org/

### Após a instalação basta acessar o app e criar uma conexão, basta deixar com as configuração dessa forma:
```text
type: Direct Connection
Name: NomeDaSuaConexao
Address:localhost
Port:27017