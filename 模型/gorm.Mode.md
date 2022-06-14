##  gorm.Mode
里面的字段可以嵌入 我们的结构体中
```go
type Mode struct {
	ID			uint			`gorm:"primaryKey"`
	CreateAt 	time.Time		
	UpdateAt 	time.Time	
	DeleteAt	gorm.DeletedAt	`gorm:"index"`
}
```

###   创建/更新时间
```go
type User struct {
	// 默认自动修改
	CreatedAt time.Time // 在创建时，如果该字段值为零值，则使用当前时间填充
	UpdatedAt int       // 在创建时该字段值为零值或者在更新时，使用当前时间戳秒数填充

	// 自定义自动修改，使用autoUpdateTime/autoCreateTime标签
	Updated   int64 `gorm:"autoUpdateTime:nano"` // 使用时间戳填纳秒数充更新时间
	Updated   int64 `gorm:"autoUpdateTime:milli"` // 使用时间戳毫秒数填充更新时间
	Created   int64 `gorm:"autoCreateTime"`      // 使用时间戳秒数填充创建时间
}
```


###   嵌入结构体
####    嵌入gorm.Mode
```go
type User struct {
  gorm.Model

  Name string
}

// 等效于
type User struct {
  ID        uint           `gorm:"primaryKey"`
  CreatedAt time.Time
  UpdatedAt time.Time
  DeletedAt gorm.DeletedAt `gorm:"index"`

  Name string
}
```
####    嵌入正常结构体
```go
type Author struct {
    Name  string
    Email string
}
type Blog struct {
  ID      int
  Author  Author `gorm:"embedded"`
  Upvotes int32
}

// 等效于
type Blog struct {
  ID    int64
  Name  string
  Email string
  Upvotes  int32
}
```

####    嵌入时改变字段名字
```go
type Blog struct {
  ID      int
  Author  Author `gorm:"embedded;embeddedPrefix:author_"`
  Upvotes int32
}

// 等效于
type Blog struct {
	ID          int64
	AuthorName  string
	AuthorEmail string
	Upvotes     int32
}
```


