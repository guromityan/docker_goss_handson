# 詳細は Qiita へ
https://qiita.com/guromityan/items/12614e6775b5787d3d9e


# 起動

```shell
$ docker-compose build
$ docker-compose up -d
```


# テスト実行

```shell
$  docker-compose exec ansible-server /bin/bash
root@38b380ec3969:~# cd work/
root@38b380ec3969:~/work# ansible-playbook -i inventory.yml site.yml
```

```shell
ok: [test-target] => {
    "msg": {
        "changed": true,
        "cmd": [
            "./goss",
            "validate",
            "--format",
            "documentation"
---
        "stdout_lines": [
            "File: /root/test.txt: exists: matches expectation: [true]",
            "File: /root/test.txt: contains: matches expectation: [this is test.]",
            "Port: tcp:80: listening: matches expectation: [true]",
            "Port: tcp:80: ip: matches expectation: [[\"0.0.0.0\"]]",
            "Port: tcp6:80: listening: matches expectation: [true]",
            "Port: tcp6:80: ip: matches expectation: [[\"::\"]]",
            "Process: nginx: running: matches expectation: [true]",
            "Service: nginx: enabled: matches expectation: [true]",
            "Service: nginx: running: matches expectation: [false]",
            "",
            "",
            "Total Duration: 0.006s",
            "Count: 9, Failed: 0, Skipped: 0"
        ]
    }
}
```
