# WSO2 BAM 2.5.0 Docker Container

Possui já instalado e configurado:

* BAM versão na `2.5.0`;

Para construir a imagem, faça:

```bash
docker build -t bam-container:2.5.0 .
```

Exemplo de como executá-la (em porta não padrão):

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 bam-container:2.5.0
```