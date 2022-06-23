# WSO2 GREG 4.6.0 Docker Container

Possui já instalado e configurado:

* GREG versão na `4.6.0`;

Para construir a imagem, faça:

```bash
docker build -t greg-container:4.6.0 .
```

Exemplo de como executá-la (em porta não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 greg-container:4.6.0
```