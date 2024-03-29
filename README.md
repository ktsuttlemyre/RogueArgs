

```
#!/bin/bash

include () {
  d=/tmp/RogueCache/; mkdir -p $d; find $d -type f -mtime ${ROGUECACHE_TTL:-+1} -delete; f=${1##/*/}; ( ! [ -f $d$f ] && curl -s $1 > $d$f ) && env . $d$f
}
. include https://raw.githubusercontent.com/ktsuttlemyre/RogueOS/master/argp.sh;
```
