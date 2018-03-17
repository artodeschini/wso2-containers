# WSO2 BPS *nightly version* Docker Container

Possui já instalado e configurado:

* BPS versão na `nightly version`, última versão construída a partir do repositório [product-bps](https://github.com/wso2/product-bps);

Para construir a imagem, faça:

```
#!shell-session
docker build -t wso2senai/bps-container:latest .
```

Exemplo de como executá-la (em portão não padrão):

```
#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/bps-container:latest
```