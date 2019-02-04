# ST-Link Utility Automation
Python API to automate STMicroelectonics flash using ST-Link CLI Utility.

####Required Packages:
<li>pywin32
<li>pypiwin32

####Hardware used
ST-Link V2 that comes with STMicroelectronics Nucleo development boards. These ST-Links
also provides USB-to-Serial ports. 

###How to use 
There are only two public methods: 
  <li> findall()<br>
  This method returns all the ST-Link Probe number and corresponding COM port number.
  <li> flash(hex_path, probe_no)<br>
  This method takes the hex file path and the probe number (default = 0). It returns status
  ('successful' / 'failed') and the checksum of the hex/binary file. 
  
  <br>

####Example
  ```buildoutcfg
import stlink

if __name__ == '__main__':
    print(stlink.findall())
    status, checksum = stlink.flash('G:\\test.hex')
    print(status)
```

Output:
```buildoutcfg
[{'probe': '0', 'com': 'COM4'}]
successful
```