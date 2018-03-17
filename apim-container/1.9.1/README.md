# WSO2 APIM Docker Container

Possui já instalado e configurado:

* AS versão na `1.9.1`;

Para construir a imagem, faça:

```
#!shell-session
docker build -t wso2senai/apim-container:1.9.1 .
```

Exemplo de como executá-la (em portão não padrão):

```
#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/apim-container:1.9.1
```