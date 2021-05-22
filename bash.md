# Bash Cheatsheet
Some useful bash scripts and snippets.

# find and replace text in multiple files

```
grep -RiIl 'search' | xargs sed -i 's/search/replace/g'
```

