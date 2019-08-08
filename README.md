# ESP32 Cam Library


## Overview

Support for Ai Thinker Cam Module with Mongoose OS

## MONGOOSE ESPCAM LIB STATUS 

Camera.c:1168

  GPIO Install ISR service fails with code 105  => ESP_ERR_NOT_FOUND No free interrupt found with the specified flags
  https://docs.espressif.com/projects/esp-idf/en/latest/api-reference/peripherals/gpio.html#_CPPv424gpio_install_isr_servicei
    
## MOS CONSOLE
    [Aug  5 13:24:14.384] ?[0;31mE (1104) camera: gpio_install_isr_service failed (105)?[0m
    [Aug  5 13:24:14.385] ?[0;31mE (1114) camera: Camera init failed with error 0x105?[0m
    
## Function
    err = gpio_install_isr_service(ESP_INTR_FLAG_LEVEL1 | ESP_INTR_FLAG_IRAM);
    if (err != ESP_OK)
    {
      ESP_LOGE(TAG, "gpio_install_isr_service failed (%x)", err);
      goto fail;
    }
