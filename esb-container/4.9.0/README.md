# WSO2 ESB 4.9.0 Docker Container

Possui já instalado e configurado:

* ESB versão `4.9.0`;

Para construir a imagem, faça:

#!shell-session
docker build -t wso2senai/esb-container:4.9.0 .
```

Exemplo de como executá-la (em portão não padrão):

#!shell-session
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/esb-container:4.9.0
```