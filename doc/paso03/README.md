# Modelado Simple de Logs

Hasta el momento, hemos ingestado en elastic nuestros logs sin modelar, sin estructura. Es decir, dado un log con el formato:

```json
{"timestamp":1569939745276,"message":"2019-10-01T14:22:25.276Z customere-services.org est 693 ID363 - The IB alarm is down, hack the back-end driver so we can input the HDD hard drive!"}
```

o:

```
2019-10-01T14:23:10.180Z nationalviral.io molestias 8974 ID85 - Try to bypass the SSL driver, maybe it will generate the optical feed!
```

El documento que hemos acabado guardando en Elasticsearch tiene un campo `timestamp` con la fecha de ingesta, y un segundo campo `message` con el mensaje completo del log.

Sería interesante, y veremos cómo, separar el contenido de este campo `message`, de forma que podamos explotar valores como el `nombre del proceso`, el `nombre del host`, etc. Es decir, darle estructura a los datos que nos llegan.

Así podremos agrupar valores similares, visualizarlos, y explotar toda la potencia de nuestros logs. Nos permitirá contestar preguntas como ¿Cuáles son los nombre de host más habituales (`customere-services.org`, `nationalviral.io`?)? ¿Y los ids de proceso?

Para ello, necesitaremos conocer la **estructura** de nuestros logs, e indicársela a Elasticsearch.

En función de qué aventura has elegido, selecciona el siguiente paso:

1. Estoy ingestando datos con **[Filebeat](./filebeat.md)**
2. Estoy usando **[Logstash](./logstash.md)**
