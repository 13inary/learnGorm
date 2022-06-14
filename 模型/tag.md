##  tag
tag 是可选的
tag 名大小写不敏感，建议使用 camelCase 风格

|------------------------|------------------------------------------------------------|
| 标签名                 | 说明                                                       |
|------------------------|------------------------------------------------------------|
| column                 | 指定 db 列名                                               |
|------------------------|------------------------------------------------------------|
| type                   | 列数据类型，推荐使用兼容性好的通用类型，                   |
|                        | 例如：所有数据库都支持 bool、int、uint、float、            |
|                        | string、time、bytes 并且可以和其他标签一起使用，           |
|                        | 例如：not null、size, autoIncrement…                       |
|                        | 像 varbinary(8) 这样指定数据库数据类型也是支持的。         |
|                        | 在使用指定数据库数据类型时，它需要是完整的数据库数据类型， |
|                        | 如：MEDIUMINT UNSIGNED not NULL AUTO_INCREMENT             |
|------------------------|------------------------------------------------------------|
| serializer             | specifies serializer for                                   |
|                        | how to serialize and deserialize data into db,             |
|                        | e.g: serializer:json/gob/unixtime                          |
|------------------------|------------------------------------------------------------|
| size                   | specifies column data size/length, e.g: size:256           |
|------------------------|------------------------------------------------------------|
| primaryKey             | specifies column as primary key                            |
|------------------------|------------------------------------------------------------|
| unique                 | specifies column as unique                                 |
|------------------------|------------------------------------------------------------|
| default                | specifies column default value                             |
|------------------------|------------------------------------------------------------|
| precision              | specifies column precision                                 |
|------------------------|------------------------------------------------------------|
| scale                  | specifies column scale                                     |
|------------------------|------------------------------------------------------------|
| not null               | specifies column as NOT NULL                               |
|------------------------|------------------------------------------------------------|
| autoIncrement          | specifies column auto incrementable                        |
|------------------------|------------------------------------------------------------|
| autoIncrementIncrement | auto increment step,                                       |
|                        | controls the interval between successive column values     |
|------------------------|------------------------------------------------------------|
| embedded               | embed the field                                            |
|------------------------|------------------------------------------------------------|
| embeddedPrefix         | column name prefix for embedded fields                     |
|------------------------|------------------------------------------------------------|
| autoCreateTime         | track current time when creating,                          |
|                        | for int fields, it will track unix seconds,                |
|                        | use value nano/milli to track unix nano/milli seconds,     |
|                        | e.g: autoCreateTime:nano                                   |
|------------------------|------------------------------------------------------------|
| autoUpdateTime         | track current time when creating/updating,                 |
|                        | for int fields, it will track unix seconds,                |
|                        | use value nano/milli to track unix nano/milli seconds,     |
|                        | e.g: autoUpdateTime:milli                                  |
|------------------------|------------------------------------------------------------|
| index                  | create index with options,                                 |
|                        | use same name for multiple fields creates                  |
|                        | composite indexes, refer Indexes for details               |
|------------------------|------------------------------------------------------------|
| uniqueIndex            | same as index, but create uniqued index                    |
|------------------------|------------------------------------------------------------|
| check                  | creates check constraint,                                  |
|                        | eg: check:age > 13, refer Constraints                      |
|------------------------|------------------------------------------------------------|
| <-                     | set field’s write permission,                              |
|                        | <-:create create-only field,                               |
|                        | <-:update update-only field,                               |
|                        | <-:false no write permission,                              |
|                        | <- create and update permission                            |
|------------------------|------------------------------------------------------------|
| ->                     | set field’s read permission, ->:false no read permission   |
|------------------------|------------------------------------------------------------|
| -                      | ignore this field, - no read/write permission,             |
|                        | -:migration no migrate permission,                         |
|                        | -:all no read/write/migrate permission                     |
|------------------------|------------------------------------------------------------|
| comment                | add comment for field when migration                       |
|------------------------|------------------------------------------------------------|
