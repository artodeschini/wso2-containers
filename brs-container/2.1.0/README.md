# WSO2 BRS 2.1.0 Docker Container

Possui já instalado e configurado:

* BRS versão `2.1.0`;

Para construir a imagem, faça:

```bash
docker build -t brs-container:2.1.0 .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 brs-container:2.1.0
```