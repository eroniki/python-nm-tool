Overview
========
This is a small utility function to parse the output of nm-tool.

I wrote it to use in scripts I want to run only if my wired Ethernet is
connected to a certain network.

Enjoy!


Functions
==========

    get_dict()
        Runs 'nm-tool' and then parses its output. Returns the result dict
        from 'parse()' if successful, otherwise returns None.
    
    parse(output)
        Parses the complete output of nm-tool, and returns a dictionary with
        the results. The properties of each interface will appear in the dict
        under the interface name. Global properties will appear under a '_' key.

