# tr

Replace (translate) characters.

Replace `a` with `b`:
```sh
tr a b <<EOF
a
EOF
```
```
b
```

Replace `a` with `c` and `b` with `d`:
```sh
tr ab cd <<EOF
ab
EOF
```
```
cd
```

Replace `a` and `b` with `c`:
```sh
tr ab c <<EOF
ab
EOF
```
```
cc
```

Replace `a` with `d`, and `b` and `c` with `e`:
```sh
tr abc de <<EOF
abc
EOF
```
```
dee
```
