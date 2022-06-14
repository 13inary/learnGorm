##  map创建记录
支持的map: `map[string]interface{}` , `[]map[string]interface{}{}` 

###   插入单条记录
```go
db.Model(&User{}).Create(map[string]interface{}{
  "Name": "jinzhu", "Age": 18,
})
```

###   插入多条记录
```go
// batch insert from `[]map[string]interface{}{}`
db.Model(&User{}).Create([]map[string]interface{}{
  {"Name": "jinzhu_1", "Age": 18},
  {"Name": "jinzhu_2", "Age": 20},
})
```

