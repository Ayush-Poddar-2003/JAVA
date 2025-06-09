# Javax Sql

The javax.sql package extends the JDBC API with features for enterprise-level applications:

| Interface                  | Use                                                          |
| -------------------------- | ------------------------------------------------------------ |
| `DataSource`               | Replacement for DriverManager. Better for connection pooling |
| `ConnectionPoolDataSource` | For managing pooled DB connections                           |
| `RowSet`                   | Disconnected, scrollable result sets                         |

---
### Why use DataSource?
- Better performance with connection pooling
- Easier to manage in enterprise apps (like in JNDI contexts)

