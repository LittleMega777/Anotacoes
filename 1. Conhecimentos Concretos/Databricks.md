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