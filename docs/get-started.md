# Get Started

Pick the path that matches your stack. All examples assume a reachable
CUBRID broker (default port `33000`).

## Raw DB-API (pycubrid)

```bash
pip install pycubrid
```

```python
import pycubrid

conn = pycubrid.connect(
    host="localhost",
    port=33000,
    user="dba",
    password="",
    database="testdb",
)
cur = conn.cursor()
cur.execute("SELECT 1")
print(cur.fetchone())
cur.close()
conn.close()
```

Full reference: [pycubrid documentation](https://cubrid-lab.github.io/pycubrid/)

## SQLAlchemy 2.0

```bash
pip install sqlalchemy-cubrid
```

```python
from sqlalchemy import create_engine, text

engine = create_engine(
    "cubrid+pycubrid://dba:@localhost:33000/testdb",
    pool_pre_ping=True,  # +588% throughput under connection churn
)

with engine.connect() as conn:
    print(conn.execute(text("SELECT VERSION()")).scalar_one())
```

Full reference: [sqlalchemy-cubrid documentation](https://cubrid-lab.github.io/sqlalchemy-cubrid/)

## Copy a working example (cookbook)

```bash
git clone https://github.com/cubrid-lab/cubrid-cookbook-python.git
cd cubrid-cookbook-python/fundamentals/pycubrid
# each example is self-contained and runnable
```

Browse by topic — fundamentals, SQLAlchemy, FastAPI, Django, Streamlit,
Celery, ETL, AI agents — in the
[cookbook documentation](https://cubrid-lab.github.io/cubrid-cookbook-python/).

## Let an AI agent query CUBRID (MCP server)

```bash
uvx cubrid-mcp-server
```

Add to any MCP client (Claude Desktop, VS Code, …):

```json
{
  "mcpServers": {
    "cubrid": {
      "command": "uvx",
      "args": ["cubrid-mcp-server"],
      "env": {
        "CUBRID_HOST": "localhost",
        "CUBRID_PORT": "33000",
        "CUBRID_USER": "dba",
        "CUBRID_PASSWORD": "",
        "CUBRID_DATABASE": "testdb"
      }
    }
  }
}
```

Then ask in natural language: *"Show me the top 5 departments by document
count."* The server enforces a read-only whitelist by default — SELECT,
JOIN, and CTE queries pass; UPDATE/DELETE/DROP and multi-statement injections
are blocked.

Full reference: [cubrid-mcp-server documentation](https://cubrid-lab.github.io/cubrid-mcp-server/)
