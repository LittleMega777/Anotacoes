**Frases que eu pensei hoje de bobeira**
"Ganho muito vendo de onde eu sai e pouco vendo onde eu quero chegar" - [[Mega]]

**[[01. Databricks]]**

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

**Pro SQL Warehouse**

O Pro SQL Warehouse tem como característica suportar a conectividade personalizada, incluindo arquiteturas hibridas (cloud - onprem) que podem precisar de uma conexão privada.

**Criando uma tabela no Databricks usando dados de um PostgreSQL**

```
CREATE TABLE employees
	USING org.apache_spark_sql_jdbc
	OPTIONS (
		url "jdbc:postgresql:dbserver",
		dbtable "employees"
	)
```

A biblioteca do JDBC permite o Spark SQL extrair dados de qualquer banco de dados que suporte JDBC. Exemplos **mysq**l, **postgres**, **SQLite** e etc.

**Arquitetura do Databricks Lakehouse**

- A localização completa dos dados do cliente, ficam no data plane (na conta de nuvem do cliente)

**Worker Memory Optimized**

Join's Spark especialmente feitos com datasets de grande escala ou com condições complexas de join, podem ser altamente 'memory-intensive' (utilizando muita memoria).

Esse worker garante que operações em memoria podem ser completadas sem sobrecarregar o disco melhorando a performance.


**[[01. Inglês]]**

**hop** = pulo/salto










