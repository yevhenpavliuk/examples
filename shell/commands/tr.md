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

Replace all lowercase letters of English alphabet with the corresponding uppercase letters:
```sh
tr a-z A-Z <<EOF
abmnyz
EOF
```
```
ABMNYZ
```

Replace all uppercase letters of English alphabet with the corresponding lowercase letters:
```sh
tr A-Z a-z <<EOF
ABMNYZ
EOF
```
```
abmnyz
```

Replace lowercase letters from `a` to `m` with the corresponding uppercase letters and lowercase letters from `n` to `z` with `M`:
```sh
tr a-z A-M <<EOF
abcdfghjklmnpqrstvwxyz
EOF
```
```
ABCDFGHJKLMMMMMMMMMMMM
```

Replace all lowercase letters with the corresponding uppercase letters:
```sh
tr [:lower:] [:upper:] <<EOF
аяaz
EOF
```
```
АЯAZ
```
