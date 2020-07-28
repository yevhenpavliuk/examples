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

---

Cipher and decipher a line with a simple substitution:
```sh
line='Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
echo $line

alphanumerics=A-Za-z0-9
randomized_alphanumerics=KLHRn2C6ZolVU7t0TbXNYc4yOuBkIdDxm91qQwJzisvpS3G5rfjEMWeFa8AhgP

ciphered_line=`tr $alphanumerics $randomized_alphanumerics <<<$line`
echo $ciphered_line

deciphered_line=`tr $randomized_alphanumerics $alphanumerics <<<$ciphered_line`
echo $deciphered_line
```
```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
VipDJ 1sSGJ diwip S13 BJD3, IizSDI3D3Gp Bd1s1SI1zm Dw13, SDd di D1GSJid 3DJsip 1zI1d1dGz3 G3 wBkipD D3 diwipD JBmzB Bw1vGB. Y3 Dz1J Bd J1z1J 5Dz1BJ, vG1S ziS3pGd DfDpI13B31iz GwwBJIi wBkip1S z1S1 G3 Bw1vG1s Df DB IiJJidi IizSDvGB3. RG1S BG3D 1pGpD diwip 1z pDspD9DzdDp13 1z 5iwGs3B3D 5Dw13 DSSD I1wwGJ diwipD DG xGm1B3 zGwwB sBp1B3Gp. nfIDs3DGp S1z3 iIIBDIB3 IGs1dB3B3 ziz spi1dDz3, SGz3 1z IGwsB vG1 ixx1I1B dDSDpGz3 Jiww13 Bz1J 1d DS3 wBkipGJ.
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```
