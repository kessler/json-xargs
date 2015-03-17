# json-xargs

## piping arrays
```
    $ echo [ "~/Downloads ~/Backup", "~/Music ~/Backup" ] | xargs -c "cp -r"
```
will execute
```
    cp -r ~/Downloads ~/Backup
    cp -r ~/Music ~/Backup
```
in parallel

## piping objects
```
    $ echo { "a": 1, "b": "foo" } | xargs -c "mytool"
```
will execute
```
    mytool --a=1 --b=foo
```

## piping arrays of objects
```
    $ echo [{ "a": 1, "b": "foo" }, { "a": 2, "b": "bar" }]  | xargs -c "mytool"
```
will execute
```
    mytool --a=1 --b=foo
    mytool --a=2 --b=bar
```
in parallel