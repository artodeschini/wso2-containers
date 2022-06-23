# WSO2 IS 5.0.0 Docker Container

Possui já instalado e configurado:

* IS versão `5.0.0`;

Para construir a imagem, faça:

```bash
docker build -t is-container:essilor .
```

Exemplo de como executá-la (em porta padrão):

```bash
docker run -d -p 8080:8080 -p 9443:9443 is-container:essilor
```

Exemplo de como executá-la (em porta não padrão):

```bash
docker run -d -p 8080:8080 -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 is-container:essilor
```

Este container contém um sample de aplicação SSO e também habilitada a autenticação *multi-factor*.
