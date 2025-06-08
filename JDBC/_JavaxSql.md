The javax.sql package provides Advanced JDBC features like:

- Connection pooling (DataSource)
- RowSet interfaces for working with data in a disconnected way
- XADataSource for distributed transactions

| Feature     | DriverManager | DataSource                |
| ----------- | ------------- | ------------------------- |
| Type        | Basic JDBC    | Advanced (pooled, secure) |
| Use         | Small apps    | Enterprise apps           |
| Flexibility | Limited       | More control, scalability |
