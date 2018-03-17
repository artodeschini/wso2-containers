# WSO2 BPS 3.2.0 Docker Container

Possui já instalado e configurado:

* BPS versão na `3.2.0`;

Para construir a imagem, faça:

```
#!shell-session
docker build -t wso2senai/bps-container:3.2.0 .
```

Exemplo de como executá-la (em portão não padrão):

```
#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/bps-container:3.2.0
```