---
title: "Known issues"
draft: false
menu:
  docs:
    title:
    parent: "PineTab2/Development"
    identifier: "PineTab2/Development/Known_issues"
    weight:
---

## Wi-Fi and Bluetooth

* The [BES2600 Wi-Fi driver](https://gitlab.com/TuxThePenguin0/bes2600) needs major cleanup and bugfixing (at the moment it often causes system crashes). This is a priority, but for now, you can USB tether a phone or use a supported WI-FI dongle. There are at least two code releases available, with two respective/non-interchangeable firmware versions. Kernel 6.9.2-danctnix1-1-pinetab2 has a somewhat working WiFi driver.
* The BES2600 Bluetooth driver needs to be implemented.
* Hardware bugs - the power and reset circuitry is not properly implemented in the circuitry, so hard reset of the chip (in the theoretical case it freezes) is impossible without power cycling the whole board.

## Camera

* The camera drivers needs to be ported ([gc02m2](https://github.com/rockchip-linux/kernel/blob/develop-4.19/drivers/media/i2c/gc02m2.c), [ov5648](https://elixir.bootlin.com/linux/latest/source/drivers/media/i2c/ov5648.c)), Rockchip CSI/ISP driver needs to be extended to handle 2 lanes.

## Suspend

* Suspend does not currently work reliably due to a driver issue. It is therefore disabled in the factory image. Caveat Emptor if you chose to unmask the feature prior to it being fixed.
