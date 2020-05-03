# tr

Replace or delete characters.

---

Replace all the occurrences of `a` with `b`:
```sh
tr a b <<EOF
aa
EOF
```
```
bb
```

---

Delete `a`:
```sh
tr -d a <<EOF
aab
EOF
```
```
b
```

---

Replace everything except `a` with `b`:
```sh
tr -C a b <<EOF
abc
EOF
```
The third `b` is for the line feed. There's no line feed is in the output:
```
abbb
```

---

Delete everything except `a` and `b`:
```sh
tr -dC ab <<EOF
abcba
EOF
```
The line feed at the end is deleted, too:
```
abba
```

---

Replace `a` with `c` and `b` with `d`:
```sh
tr ab cd <<EOF
abba
EOF
```
```
cddc
```

---

Replace `a` and `b` with `c`:
```sh
tr ab c <<EOF
ab
EOF
```
```
cc
```

---

Replace `a` with `d`, and `b` and `c` with `e`:
```sh
tr abc de <<EOF
abc
EOF
```
```
dee
```

---

Replace all lowercase letters of English alphabet with the corresponding uppercase letters:
```sh
tr a-z A-Z <<EOF
abmnyz
EOF
```
```
ABMNYZ
```

---

Replace all uppercase letters of English alphabet with the corresponding lowercase letters:
```sh
tr A-Z a-z <<EOF
ABMNYZ
EOF
```
```
abmnyz
```

---

Replace lowercase letters from `a` to `m` with the corresponding uppercase letters and lowercase letters from `n` to `z` with `M`:
```sh
tr a-z A-M <<EOF
abcdfghjklmnpqrstvwxyz
EOF
```
```
ABCDFGHJKLMMMMMMMMMMMM
```

---

Replace all lowercase letters with the corresponding uppercase letters:
```sh
tr [:lower:] [:upper:] <<EOF
аяaz
EOF
```
```
АЯAZ
```
