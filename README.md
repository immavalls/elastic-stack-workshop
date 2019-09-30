# Elastic Stack Workshop

Este repositorio es el fuente para el workshop del Elastic Stack en el que se va a ejecutar el stack mediante Docker Compose.

Este workshop se basa en la versión 7.3.2. el stack. Configurada en el fichero [.env](.env).

## Pre-requisitos

- Docker y Docker Compose.
  - Usuarios de Windows y Mac users tendrán Compose instalado automáticamente con Docker para [Windows](https://docs.docker.com/docker-for-windows/install/)/[Mac](https://docs.docker.com/docker-for-mac/install/).
  - Los usuarios de Linux puede leer las [instrucciones de instalación](https://docs.docker.com/compose/install/#install-compose) o pueden instalar vía `pip`:
  
    ```shell
    pip install docker-compose
    ```

- Un mínimo de 4GiB de RAM para contenedores. Los usuarios de Mac y Windows deben configurar su máquina virtual Docker para disponer de ese mínimo.

![Docker VM memory settings](doc/img/docker-vm-memory-settings.png)

- Debido a que que por defecto la [memoria virtual](https://www.elastic.co/guide/en/elasticsearch/reference/7.3/vm-max-map-count.html) no es suficiente, los usuarios de Linux deben ejecutar el siguiente comando como `root`:

```
sysctl -w vm.max_map_count=262144
```

## Contenido del workshop

En este workshop se demostrarán las capacidades básicas del Stack Elastic para ingesta de logs y métricas. Los pasos a seguir son los siguientes:

1. [Introducción al Stack Elastic](./doc/paso01/README.md)
 - En este apartado, se arrancará un stack elastic con un cluster de un nodo de Elasticsearch, una instancia de Kibana, y varios beats: Metricbeat y Heartbeat.
 - Veremos como utilizar Kibana para visualizar las métricas (Discover y InfraUI), así como el uso de Uptime.
2. [Ingesta de logs](./doc/paso02/README.md)
 - Usaremos Filebeat o Logstash para la ingesta de logs en Elasticsearch y los visualizaremos con LogsUI.
3. [Modelado simple de logs](./doc/paso03/README.md)
 - Reingestaremos estos logs, esta vez modelando los campos. Crearemos nuestro primer dashboard para visualizar la información agregada.
4. [¿Por dónde seguir?](./doc/paso04/README.md)
 - Daremos algunos consejos sobre los siguientes pasos.