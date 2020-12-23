# Clickhouse Bundle

Just a clickhouse client provider for applauncher 

Installation
------------
```bash
pip install clickhouse_bundle  
```
Then add to your main.py
```python
import clickhouse_bundle

bundle_list = [
    clickhouse_bundle.ClickhouseBundle(),
]
```

Configuration
-------------
Currently just the connection uri, for example
```yml
clickhouse:
  connection_uri: 'clickhouse://localhost:9000/default'
```

Usage
-----
Just inject and use it as a regular clichouse client
```python
import inject
from clickhouse_driver import Client

client = inject.instance(Client)
query = f"SELECT name FROM fruits limit %(limit)s"
params = {
    "limit": 10
}

result = client.execute(query, params)
```
More information about clickhouse sql syntax here https://clickhouse.tech/docs/es/sql-reference/syntax/
