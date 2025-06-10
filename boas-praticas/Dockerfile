# Usa imagem oficial do Bun
FROM oven/bun:1.1.3

# Cria diretório da aplicação
WORKDIR /app

# Copia arquivos para dentro do container
COPY . .

# Instala dependências
RUN bun install --frozen-lockfile

# Expõe a porta padrão da aplicação
EXPOSE 3333

# Comando para iniciar o servidor
CMD ["bun", "run", "src/main.ts"]
