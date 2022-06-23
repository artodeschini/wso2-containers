# WSO2 BPS 3.5.0-SNAPSHOT Docker Container

Possui já instalado e configurado:

* BPS versão na `3.5.0-SNAPSHOT`, disponível [aqui](https://svn.wso2.org/repos/wso2/people/warunaj/releases/bps350/M6/wso2bps-3.5.0-SNAPSHOT.zip);

Para construir a imagem, faça:

```bash
docker build -t bps-container:3.5.0-SNAPSHOT .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 bps-container:3.5.0-SNAPSHOT
```