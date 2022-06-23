# WSO2 ESB 4.8.1 Docker Container

Possui já instalado e configurado:

* ESB versão `4.8.1`;

Para construir a imagem, faça:

```bash
docker build -t esb-container:4.8.1 .
```

Exemplo de como executá-la (em portão não padrão):

'''bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 esb-container:4.8.1
```