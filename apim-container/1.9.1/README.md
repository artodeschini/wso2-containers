# WSO2 APIM Docker Container

Possui já instalado e configurado:

* AS versão na `1.9.1`;

Para construir a imagem, faça:

```bash
docker build -t apim-container:1.9.1 .
```

Exemplo de como executá-la (em portão não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 apim-container:1.9.1
```