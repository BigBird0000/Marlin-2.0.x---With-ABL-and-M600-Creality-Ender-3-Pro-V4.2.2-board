# Marlin 3D Printer Firmware
todo
Uncommented line 1329 Configuration_adv.h, to get ready for LED installation
  #define LED_CONTROL_MENU

 Add Autotune PID Menu:
   configuration.h
      removed comments line 593-594
         #define PID_EDIT_MENU         // Add PID editing to the "Advanced Settings" menu. (~700 bytes of PROGMEM)

         #define PID_AUTOTUNE_MENU     // Add PID auto-tuning to the "Advanced Settings" menu. (~250 bytes of PROGMEM)

      Leave Line 595 commented if you have 1 hot end
         //#define PID_PARAMS_PER_HOTEND // Uses separate PID parameters for each extruder (useful for mismatched extruders)


not done
Removed # removed     ini/stm32f1-maple.ini from platformio.ini in extra_configs
                           