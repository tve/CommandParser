# Super simple command-line parser for Arduino

Super simple commandline processor for Arduino environments. Features:

- super small and simple codebase, easy to modify
- provide minimal input editing (backspace)
- register commands, let commands parse args

## How it works

- register command word callbacks using `addCommand()`
- in the callback, use `getArg()` or `getRest()` to get next arg or rest of commandline for parsing
- register default callback using `setDefault()` to print help/error message
- for interactive input processing, use `CommandParser(HardwareSerial *serial)` constructor and call
  `loop()` in sketch's own `loop()`
- for batch processing (for example, command recieved via MQTT or HTTP) use `CommandParser()`
  constructor and `parseLine()`

## Examples

The best simple example can be found in
https://github.com/tve/esp32-secure-base/blob/master/src/ESPSecureBase.cpp
