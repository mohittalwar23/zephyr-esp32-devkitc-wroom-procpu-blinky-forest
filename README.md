
# zephyr-esp32-devkitc-wroom-procpu-blinky-forest

We distinguish three basic types of Zephyr application based on where <app> is located:


| Application type    | Location |
| --------- | ------- |
| repository     |      zephyr repository   |
| workspace          |    west workspace where Zephyr is installed     |
| freestanding | other locations|


A Zephyr application located outside of a Zephyr workspace is referred to as a Zephyr freestanding application. In the following example, app is a Zephyr freestanding application.

This example runs blinky on ESP32-DevKitC-WROOM using freestanding Zephyr Rtos approach.

Make sure zephyr is already installed with espressif toolchain and other dependencies:  [here](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) 

## How to Run

####  1. Clone the Repository in your system

```bash
  git clone https://github.com/mohittalwar23/zephyr-esp32-devkitc-wroom-procpu-blinky-forest
```

####  2. The Structure of your directory should look like this

```bash
  app
  -> src/main.c
  -> prj.conf
  -> CMakeLists.txt
  -> overlay file 
```    
####  3. Follow this initialisation carefully


```bash
  cd app
```    

```bash
  source ~/zephyrproject/zephyr/zephyr-env.sh 
  export ZEPHYR_BASE=~/home/mohit/zephyrproject/zephyr
``` 

** This path will change according to location of your zephyr folder

```bash
  west init -l /home/mohit/zephyrproject/zephyr
``` 
```bash
  west update
``` 
** This might change if you are using a different esp32 board

```bash
  west build -b esp32_wroom_devkitc/esp32/procpu
``` 

```bash
  west flash
``` 

## References

- https://docs.zephyrproject.org/latest/develop/application/index.html
- https://www.reddit.com/r/Zephyr_RTOS/comments/s19bsb/confusion_about_creating_an_app/
- https://docs.zephyrproject.org/latest/develop/west/workspaces.html#topologies-supported
- https://danielmangum.com/posts/risc-v-bytes-zephyr-on-esp32/
- https://interrupt.memfault.com/blog/practical_zephyr_west
