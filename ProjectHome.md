![http://pyagilent54622d.googlecode.com/svn/trunk/doc/scope.png](http://pyagilent54622d.googlecode.com/svn/trunk/doc/scope.png)

A python module that realizes the RS-232 interface of the Agilent 54622D Mixed Signal Digital Storage Oscilloscope in a clean, pythonic fashion that is easy and convenient to use.

Here's an example:

```
import agilent
scope = agilent.Scope(port="COM1", baudRate=57600)

for channel in (scope.a1, scope.a2):
   print "Channel %s: min=%f max=%f avg=%f" % (channel.label, channel.min, channel.max, channel.average)

scope.d0.label = 'SDA'
scope.d1.label = 'SCL'

t, sda = scope.d0.get_data()
t, scl = scope.d1.get_data()

scope.screen("saved_screenshot.png")
```