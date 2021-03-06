## Deployment

Support python 3.

```bash
pip install imetis
```

## Usage

### Create a Metis client

```python
import imetis

client = imetis.MetisClient(metisUrl='https://your.metis.com')
# It is an invalid url, please use your true url.
# If you don't know your metis url, please contact to your metis administrator.
```

### Authenticate

Use your own Metis account to authenticate.

```python
client.authenticate(username='xiaoming.wang@mailbox.com', password='yourPassword')
```

### Search tickets by keyword

Search tickets with a keyword. You can specify how many results you need (default 10).

```python
result = client.ticket_search('hdfs', num=5)

print(result)
```

### Search tickets by TQL (Advanced)

Search tickets with a TQL (a kind of query language) statement. You can specify how many results you need (default 10).

```python
result = client.ticket_search_by_tql('(TICKET_TITLE token match "hdfs upgrade")', num=20)

print(result)
```

### Search JIRA cases by keyword

Search JIRA cases with a keyword. You can specify how many results you need (default 10).

```python
result = client.jira_search('hdfs', num=5)

print(result)
```

### Search WIKI cases by keyword

Search WIKI cases with a keyword. You can specify how many results you need (default 10).

```python
result = client.wiki_search('hdfs', num=5)

print(result)
```

### Search AIOPS cases by keyword

Search AIOPS cases with a keyword. You can specify how many results you need (default 10).

```python
result = client.aiops_search('hdfs', num=5)

print(result)
```

### Search IntKB cases by keyword

Search IntKB cases with a keyword. You can specify how many results you need (default 10).

```python
result = client.intkb_search('hdfs', num=5)

print(result)
```

### Check your own tickets

Check your own tickets. The result will be sent to your email.

```python
client.personal_ticket_check()
```

### Analysis top hot issues

Auto analysis hot issues by component and month.

```python
print(client.analysis_hot_issues("Inceptor", '5'))
```
