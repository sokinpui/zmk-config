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

