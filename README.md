# DBConnectorN
## 使い方
transactionスコープ内で例外が発生したらロールバックします(多分)
```kotlin
import jp.asteria.dbconnector.Database
import jp.asteria.dbconnector.Database.transaction

transaction {
    val type = Database.type // enumを取得できる 今のところは SQLITE,MYSQL の2種類

    val connection = Database.getConnection() ?:throw SQLException() // java.sql.Connection
    // あとはいつも通りPreparedStatementとか
}

```
