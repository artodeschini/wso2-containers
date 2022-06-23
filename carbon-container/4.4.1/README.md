# WSO2 Carbon 4.4.1 Docker Container

Possui já instalado e configurado:

* carbon versão `4.4.1`;

Para construir a imagem, faça:

```bash
docker build -t carbon-container:4.4.1 .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 carbon-container:4.4.1
```