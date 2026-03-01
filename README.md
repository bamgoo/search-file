# search-file

`search` 的文件驱动，基于 `Bleve`，适合小项目或本地环境。

驱动名：`file`

## 特点

1. 无外部服务，单机可运行。
2. 支持全文检索、字段过滤、排序、分页、分面、高亮（按 Bleve 能力）。
3. 配置简单。

## 使用

```go
import _ "github.com/infrago/search-file"
```

```toml
[search]
driver = "file"
prefix = "demo"

[search.setting]
path = "store/search"
```

## 配置项

- `search.setting.path`：索引目录，默认 `store/search`
- `search.prefix`：索引名前缀（可选）

## 说明

1. 每个索引对应一个本地 bleve 目录文件。
2. 推荐用于开发、小型服务或边缘节点。
3. 中大型集群建议切换到 `meilisearch/opensearch/elasticsearch`。
