# WSO2 AS 5.2.1 Docker Container

Possui já instalado e configurado:

* AS versão na `5.2.1`;

Para construir a imagem, faça:

```
#!shell-session
docker build -t wso2senai/as-container:5.2.1 .
```

Exemplo de como executá-la (em portão não padrão):

```
#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/as-container:5.2.1
```