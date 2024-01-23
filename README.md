Make sure you have already setup `zmk-config` correctly
# setup zmk on local machine
```
chomd +x zmk-local-env-setup
./zmk-local-env-setup
```

# build zmk firmware on local machine
```
cd $HOME/zmk/app
west build -d build/left -b nice_nano_v2 -- -DSHIELD=corne_left  -DZMK_CONFIG="/home/so/zmk_config"
west build -d build/left -b nice_nano_v2 -- -DSHIELD=corne_right -DZMK_CONFIG="/home/so/zmk_config"
```
