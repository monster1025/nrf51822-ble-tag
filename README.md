# nrf51822-ble-tag
This repository contains firmware dump, app and description pdf for chineese BLE tag.

[![BLE Tag](https://github.com/monster1025/nrf51822-ble-tag/blob/master/img/NRF51822-2-3-3-Bluetooth-4-0.jpg)](https://aliexpress.ru/item/32826502025.html)


### Problem: When you choose invalid settings from BLE_Sample app, you can 'brick' your BLE beacon.
I have a broken one. I get dump firmware from a good one and write it to broken.

You need any SWD programmer for repair.

Primary program util is nrfjprog, download it here:
https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Command-Line-Tools

Read out code (make a backup):

```
nrfjprog --readcode backup_code.hex
nrfjprog --readqspi backup_qspi.hex 
nrfjprog --readram backup_ram.hex
```

Write working code (!!! Make sure you have full backup!):
```
nrfjprog --program good_code.hex --chiperase
```
