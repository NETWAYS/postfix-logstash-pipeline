# User fields #

This pipeline tries to keep as close to Elastic Common Schema (ECS) as possible.

You can create a list of all non-ecs fields by running the following command in the root directory of this project:

```
grep -Pho "\[postfix\]\[[^\[]*?\]" filter-* | sort -u | sed -e "s@\[postfix\]\[@@;s@\]@,@" | sed ':a;N;$!ba;s/\n/ /g' | sed -e "s/,$//"
```

(Thanks to @dgoetz and @crited who contributed a similar command to https://github.com/Icinga/icinga-logstash-pipeline )
