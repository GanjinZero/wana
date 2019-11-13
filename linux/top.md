# 只监控python
```
top -p `pgrep python | tr "\\n" "," | sed 's/,$//'`
```
