# WSO2 IS 5.0.0 Docker Container

Possui já instalado e configurado:

* IS versão `5.0.0`;

Para construir a imagem, faça:

```
#!shell-session
docker build -t wso2senai/is-container:5.0.0 .
```

Exemplo de como executá-la (em porta não padrão):

```
#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/is-container:5.0.0
```