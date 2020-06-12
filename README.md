# gophidgets
A Golang wrapper to the Phidgets C library

## Example
```go
t := phidgets.PhidgetTemperatureSensor{}
t.Create()
t.SetIsRemote(true)
t.SetDeviceSerialNumber(11111)
t.SetHubPort(0)
err = t.OpenWaitForAttachment(2000)
if err != nil {
    panic(err)
}
//Loop forever
for {
    fmt.Println("Temperature is", t.GetValue()*9.0/5.0+32)
}
```