# WSO2 BPS *nightly version* Docker Container

Possui já instalado e configurado:

* BPS versão na `nightly version`, última versão construída a partir do repositório [product-bps](https://github.com/wso2/product-bps);

Para construir a imagem, faça:

```bash
docker build -t bps-container:latest .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 bps-container:latest
```