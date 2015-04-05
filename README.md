Overview
--------
This is a small utility function to parse the output of nm-tool.

I wrote it to use in scripts I want to run only if my wired Ethernet is
connected to a certain network.

Enjoy!


Functions
---------

    get_dict()
        Runs 'nm-tool' and then parses its output. Returns the result dict
        from 'parse()' if successful, otherwise returns None.
    
    parse(output)
        Parses the complete output of nm-tool, and returns a dictionary with
        the results. The properties of each interface will appear in the dict
        under the interface name. Global properties will appear under a '_' key.

Example
-------
    Running the module will print the dictionary returned by `get_dict()`.

    $ python -m nm_tool
    {'_': {'state': 'connected (global)'},
     'eth0': {
          'carrier': 'off',
          'carrier_detect': 'yes',
          'default': 'no',
          'driver': 'r8169',
          'hw_address': '80:FD:2C:01:02:05',
          'name': None,
          'speed': '1000 Mb/s',
          'state': 'unavailable',
          'type': 'Wired'},
     'wlan0': {
           'address': '172.16.0.160',
           'default': 'yes',
           'dns': '172.16.0.1',
           'driver': 'iwlwifi',
           'gateway': '172.16.0.1',
           'hw_address': '41:52:C5:55:82:30',
           'name': 'AwesomeNet',
           'prefix': '24 (255.255.255.0)',
           'scan_results': {'Burrito': 'Infra, 1C:B0:5F:8C:6D:45, Freq 2427 MHz, Rate 54 Mb/s, Strength 29 WPA WPA2',
                            'AwesomeNet': 'Infra, C7:02:18:28:22:5B, Freq 2437 MHz, Rate 54 Mb/s, Strength 30 WPA2',
                            'Cheese': 'Infra, D8:71:4C:49:A4:21, Freq 2422 MHz, Rate 54 Mb/s, Strength 35 WPA WPA2',
                            'Tofu': 'Infra, 5D:53:AC:7B:12:94, Freq 2412 MHz, Rate 54 Mb/s, Strength 49'},
           'speed': '65 Mb/s',
           'state': 'connected',
           'type': '802.11 WiFi',
           'wep_encryption': 'yes',
           'wpa2_encryption': 'yes',
           'wpa_encryption': 'yes'}}

