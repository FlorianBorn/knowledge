# How to: Connect to Server (or Device Farm)
```
adb connect <server-url>:<server-port>
# e.g. adb connect my-server:5555 (without protocol (e.g. http))
```

# How to: List available devices
```
# you must be connected to a device server at this point
adb devices
```