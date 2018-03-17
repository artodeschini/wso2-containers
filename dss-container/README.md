# WSO2 DSS Docker Container

Possui já instalado e configurado:

* Criada a partir de `wso2senai/base-container`
* DSS versão `3.2.2`;
* *port offset* igual a `1`;
* exemplo de como executá-la:
```
#!shell-session
docker build -t wso2senai/dss-container .
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 wso2senai/dss-container
```