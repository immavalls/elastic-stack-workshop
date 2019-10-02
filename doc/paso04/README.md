# ¿Por dónde seguir?

- Añade [APM](https://www.elastic.co/es/blog/monitoring-applications-with-elasticsearch-and-elastic-apm) al stack, para la trazabilidad en aplicaciones.
- Modela los documentos usando [Elastic Common Schema - ECS](https://www.elastic.co/es/blog/introducing-the-elastic-common-**schema**).
- Configura [Index Lifecycle Management](https://www.elastic.co/guide/en/elasticsearch/reference/7.3/getting-started-index-lifecycle-management.html) para gestionar el ciclo de vida de los índcies en elasticsearch.
- Prepárate para escalar tu cluster elasticsearch implementando una [arquitectura hot/warm/cold](https://www.elastic.co/es/blog/implementing-hot-warm-cold-in-elasticsearch-with-index-lifecycle-management).
- Securiza tus configuración usando [keystores](https://nicklang.com/posts/learning-to-love-the-keystore) para guardar tus secretos.
- Guarda histórico de tus métricas mediante [rollup](https://www.elastic.co/guide/en/elasticsearch/reference/7.3/xpack-rollup.html) jobs.
- Y para cualquier duda, nuestros foros en https://discuss.elastic.co!

## Finalizamos

Y para terminar, podemos eliminar todo lo creado hasta el momento y liberar recursos ejecutando los siguientes comandos.

Parar la generación de logs:

1. JSON/Filebeat: ejecutar `docker stop flog_json`
2. Plain/Logstash: ejecutar `docker stop flog_plain`

```shell
rm ./test/*.log
docker-compose down -v
```

> `-v` para eliminar el volumen de datos de elasticsearch
