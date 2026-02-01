# SQLite-database-connection-to-a-database-that-resides-in-the-memory.
import sqlite3
try:
sqlite_Connection = sqlite3.connect(&#39;temp.db&#39;)
conn = sqlite3.connect(&#39;:memory:&#39;)
print(&quot;\nMemory database created and connected to SQLite.&quot;)
sqlite_select_Query = &quot;select sqlite_version();&quot;

conn.execute(sqlite_select_Query)
print(&quot;\nSQLite Database Version is: &quot;, sqlite3.version)
conn.close()
except sqlite3.Error as error:
print(&quot;\nError while connecting to sqlite&quot;, error)
finally:
if (sqlite_Connection):
sqlite_Connection.close()
print(&quot;\nThe SQLite connection is closed.&quot;)
