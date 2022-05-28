# Marlin 3D Printer Firmware
## 2022-05-28  <br><br>
## Version 2.0.9.3-AJS3

###	enabled ADVANCED_PAUSE_FEATURE, line 2428 configuration_adv.h
>		#define ADVANCED_PAUSE_FEATURE
>		#if ENABLED(ADVANCED_PAUSE_FEATURE)
>		#define PAUSE_PARK_RETRACT_FEEDRATE         50 
>		#define PAUSE_PARK_RETRACT_LENGTH            5 
>		#define FILAMENT_CHANGE_UNLOAD_FEEDRATE    200 
>		#define FILAMENT_CHANGE_UNLOAD_ACCEL        25 
>		#define FILAMENT_CHANGE_UNLOAD_LENGTH      700 
>		#define FILAMENT_CHANGE_SLOW_LOAD_FEEDRATE   6 
>		#define FILAMENT_CHANGE_SLOW_LOAD_LENGTH     0 
>		#define FILAMENT_CHANGE_FAST_LOAD_FEEDRATE   6 
>		#define FILAMENT_CHANGE_FAST_LOAD_ACCEL     25 
>		#define FILAMENT_CHANGE_FAST_LOAD_LENGTH     5 
>		//#define ADVANCED_PAUSE_CONTINUOUS_PURGE      
>		#define ADVANCED_PAUSE_PURGE_FEEDRATE        3 
>		#define ADVANCED_PAUSE_PURGE_LENGTH         10 
>		#define ADVANCED_PAUSE_RESUME_PRIME          0 
>		#define ADVANCED_PAUSE_FANS_PAUSE              
>		#define FILAMENT_UNLOAD_PURGE_RETRACT       13 
>		#define FILAMENT_UNLOAD_PURGE_DELAY       5000 
>		#define FILAMENT_UNLOAD_PURGE_LENGTH         8 
>		#define FILAMENT_UNLOAD_PURGE_FEEDRATE      25 
>		#define PAUSE_PARK_NOZZLE_TIMEOUT           45 
>		#define FILAMENT_CHANGE_ALERT_BEEPS         10 
>		#define PAUSE_PARK_NO_STEPPER_TIMEOUT          
>		//#define FILAMENT_CHANGE_RESUME_ON_INSERT     
>		//#define PAUSE_REHEAT_FAST_RESUME             
>		#define PARK_HEAD_ON_PAUSE 
>		//#define HOME_BEFORE_FILAMENT_CHANGE          
>		#define FILAMENT_LOAD_UNLOAD_GCODES
>		//#define FILAMENT_UNLOAD_ALL_EXTRUDERS        
>		#endif

###			YOU SHOULD CHANGE THE ABOVE SETTINGS TO FIT YOUR PRINTER!

configuration.h, line 1892,
### enable NOZZLE_PARK_FEATURE
>		#define NOZZLE_PARK_FEATURE
>		
>		#if ENABLED(NOZZLE_PARK_FEATURE)
>		// Specify a park position as { X, Y, Z_raise }
>		#define NOZZLE_PARK_POINT { (X_MIN_POS + 5), (Y_MIN_POS + 5), 20 }
>		//#define NOZZLE_PARK_X_ONLY
>		//#define NOZZLE_PARK_Y_ONLY
>		#define NOZZLE_PARK_Z_RAISE_MIN   5
>		#define NOZZLE_PARK_XY_FEEDRATE 150
>		#define NOZZLE_PARK_Z_FEEDRATE    5 
>		#endif




### Individuals will want to change the following in configuration.h
>	#define STRING_CONFIG_H_AUTHOR "(Alan)" // Who made the changes.
>	#define CUSTOM_MACHINE_NAME "Alan's Ender-3 Pro 4.2.2"
>	#define NOZZLE_PARK_POINT { (X_MIN_POS + 5), (Y_MIN_POS + 5), 20 }
>		// this defines where to park the hotend when changing filament
>		// I have it as X= minimum-position + 5 (so 5 for most printers)
>		// 				Y= minimum-position + 5 (so 5 for most printers)
>		//				Z =20 (raise the Z axis by 20)
>

## Older Version - Just ABL - no M600 command changes
### Uncommented line 1329 Configuration_adv.h, to get ready for LED installation
>  #define LED_CONTROL_MENU

### Add Autotune PID Menu:  
   configuration.h
>      removed comments line 593-594
>         #define PID_EDIT_MENU         // Add PID editing to the "Advanced Settings" menu. (~700 bytes of PROGMEM)
>
>         #define PID_AUTOTUNE_MENU     // Add PID auto-tuning to the "Advanced Settings" menu. (~250 bytes of PROGMEM)
>
>      Leave Line 595 commented if you have 1 hot end
>         //#define PID_PARAMS_PER_HOTEND // Uses separate PID parameters for each extruder (useful for mismatched extruders)

not done (todo)
> Remove _Maple Environment
Removed # removed     ini/stm32f1-maple.ini from platformio.ini in extra_configs
                           