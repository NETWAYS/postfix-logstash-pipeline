# postfix-logstash-pipeline

[![CI](https://github.com/netways/postfix-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg)](https://github.com/netways/postfix-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

**Please do not use this for production, yet. This is a work in progress and we are yet in the process of finding potential problems with the ruleset. So do not rely on issues to check whether the rules are suitable for you or not**

Pipeline to parse Postfix logs

## Input and output ##

This pipeline has no input nor output. `.gitignore` includes `input.conf` and `output.conf` so you can use these files for your own input and output configuration.

Here are examples using a local Redis.
```
input {
  redis {
    host => "localhost"
    data_type => "list"
    key => "postfix"
  }
}

output {
  redis {
    host => "localhost"
    data_type => "list"
    key => "forwarder"
  }
}
```
