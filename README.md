# WSO2 Docker Containers

Este repositório contém *containers* e *composes* Docker dos componentes de Midleware WSO2.

## Organização dos containers

O repositório está organizado da seguinte forma:

+ [`base-container`][base-container]: é o *container* que contém as configurações básicas para todos (ou uma parte) dos *containers* a serem construídos e pode ser incluído como container de DB em qualquer *compose*
+ [`esb-container`][esb-container]: *container* para o [WSO2 Enterprise Service Bus][wso2-esb-site]
+ [`dss-container`][dss-container]: *container* para o [WSO2 Data Services Server][wso2-dss-site]
+ [`carbon-container`][carbon-container]: *container* para o [WSO2 Carbon][wso2-carbon-site]
+ [`as-container`][as-container]: *container* para o [WSO2 Application Server][wso2-as-site]
+ [`is-container`][is-container]: *container* para o [WSO2 Identity Server][wso2-is-site]
+ [`apim-container`][apim-container]: *container* para o [WSO2 API Manager][wso2-apim-site]
+ [`bam-container`][bam-container]: *container* para o [WSO2 Business Activity Monitor][wso2-bam-site]
+ [`greg-container`][greg-container]: *container* para o [WSO2 Governance Registry][wso2-greg-site]
+ [`bps-container`][bps-container]: *container* para o [WSO2 Business Process Server][wso2-bps-site]
+ [`brs-container`][brs-container]: *container* para o [WSO2 Business Rules Server][wso2-brs-site]
+ **`TODO`** - [`private-paas-compose`][private-paas-compose]: *compose* para a [WSO2 Private PaaS][wso2-private-paas-site]

## Como usar

Como não está em um repositório Docker precisaremos registrar os containers no servidor local para que possamos, por exemplo, referenciar a imagem base (`FROM base-container`) nas demais imagens. Para isto, no diretório `/wso2-docker-containers/base-container` execute:

```bash
docker build -t base-container .
```

Isto irá construir a imagem base `base-container`, contendo um servidor PostgreSQL.

Para mais informação, verifique a [documentação oficial do Docker][docker-docs] e os [exemplos de container][docker-library]

## Como usar offSet dos containers wso2

Tendo criado a imagens do container

```bash
docker run -d -p 9444:9444 -e WSO2_PORT=9444 -e WSO2_PORT_OFFSET=1 {wso2container_selecionado}
```

[docker-docs]: https://docs.docker.com/
[docker-library]: https://github.com/docker-library
[base-container]: /base-container/README.md
[esb-container]:/esb-container
[wso2-esb-site]: http://wso2.com/products/enterprise-service-bus/
[dss-container]:/dss-container/README.md
[wso2-dss-site]: http://wso2.com/products/data-services-server/
[carbon-container]:/carbon-container/README.md
[wso2-carbon-site]: http://wso2.com/products/carbon/
[as-container]:/as-container/README.md
[wso2-as-site]: http://wso2.com/products/application-server/
[is-container]:/is-container/README.md
[wso2-is-site]: http://wso2.com/products/identity-server/
[apim-container]:/am-container/README.md
[wso2-apim-site]: http://wso2.com/api-management/
[bam-container]:/bam-container/README.md
[wso2-bam-site]: http://wso2.com/products/business-activity-monitor/
[greg-container]:/greg-container/README.md
[wso2-greg-site]: http://wso2.com/products/governance-registry/
[bps-container]:/bps-container/README.md
[wso2-bps-site]: http://wso2.com/products/business-process-server/
[brs-container]:/brs-container/README.md
[wso2-brs-site]: http://wso2.com/products/business-rules-server/
[private-paas-compose]:/private-paas-compose/README.md
[wso2-private-paas-site]: http://wso2.com/cloud/private-paas/