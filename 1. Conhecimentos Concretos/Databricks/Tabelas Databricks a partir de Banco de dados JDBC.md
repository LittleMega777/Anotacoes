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