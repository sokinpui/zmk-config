Make sure you have already setup `zmk-config` correctly
# setup zmk on local machine
```
chomd +x zmk-local-env-setup
./zmk-local-env-setup
```

# build zmk firmware on local machine
```
f () {
rm build
west build -b nice_nano_v2 -- -DSHIELD=corne_left  -DZMK_CONFIG="/home/so/zmk-config/config"
mv ~/zmk/app/build/zephyr/zmk.uf2 ~/zmk-config/built-firmware/left.uf2
rm build
west build -b nice_nano_v2 -- -DSHIELD=corne_right -DZMK_CONFIG="/home/so/zmk-config/config"
mv ~/zmk/app/build/zephyr/zmk.uf2 ~/zmk-config/built-firmware/right.uf2
}
```
then run
```
f
```

# how to build both corne-mx and corne-choc?
It is a simple work around, first build choc-mx with `zmk-build-firmware corne` command, then rename the firmware built, then rename the keyboard to "corne-choc"
run the command `zmk-build-firmware corne` again to build for corne-choc. Don't forget to rename the keyboard to corne, since mx will be used more often.

---

Update on Fri Feb  2 09:22:44 PM HKT 2024
command `zmk-build-firmware` has changed so that it can build different firmware correctly
