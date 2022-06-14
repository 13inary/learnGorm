##  SQLite
###   创建本地数据库
```go
import (
	"gorm.io/driver/sqlite" // Sqlite driver based on GGO
	// "github.com/glebarez/sqlite" // Pure go SQLite driver, checkout https://github.com/glebarez/sqlite for details
	"gorm.io/gorm"
)

// github.com/mattn/go-sqlite3
db, err := gorm.Open(sqlite.Open("gorm.db"), &gorm.Config{})
```

###   创建内存临时数据库
使用 `file::memory:?cache=shared` 替代文件路径


###   配置
配置`&gorm.Config{}` 
