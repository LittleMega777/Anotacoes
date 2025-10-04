**Como criar um streaming DataFrame a partir de um tópico Kafka**

```
eventsStream = (spark.readStream
					.format("kafka")
					.option("kafka.bootstrap.servers", "host:port")
					.option("subscribe", "events_topic")
					.option("startingOffsets", "latest")
					.load()
					)
```

Como acima a forma mais correta é usar o readStream com format "kafka" e usando .option() para as especificar as configurações necessárias:
- **kafka.bootstrap.servers** - identifica o cluster Kafka.
- **subscribe** - define o alvo do tópico Kafka.
- **startingOffsets** - controla o ponto de inicio de consumo.
