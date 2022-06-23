# WSO2 AS 5.2.1 Docker Container

Possui já instalado e configurado:

* AS versão na `5.2.1`;

Para construir a imagem, faça:

```bash
docker build -t as-container:5.2.1 .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9443:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 as-container:5.2.1
```