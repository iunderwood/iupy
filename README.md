# iupy
Ian Underwood Python Kit (IUPY)

## About
This package is a set of Python functions that I have built out and found useful in my travels as a network engineer.  This is the base package for all iupy additional packages to follow.

This functions in this package are meant to be standalone packages and have no other package dependencies beyond a base Python installation.  These functions are designed to be light on requirements.

This package has been built and tested against Python 3.9, and should work down to 3.7 but I can't guarantee that.

## Function Summary

### misc.py

iupy.text_header : Returns a text header returning the time, user, and system a given output was generated on.  Additional options allow for identifying a source, as well as another user if specified.  A footer may also be defined.

iupy.merge_dict : Returns a combined dictionary given two dictionary inputs.

### myconfig.py

iupy.get_file_handle_ro : Returns a file handle given a name, or None if the file cannot be found or is inaccessible.  Exceptions are logged to DEBUG.

iupy.get_my_config : Moves through a series of directories looking for a configuration file needed by a script.  This returns a data dictionary containing the data, the filename used, and the file's timestamp.  Useful for baking portable CLI utilities and automated scripts.

### network.py

#### Host Information

iupy.get_my_ip : Returns a string, the source IP given a remote IP address or destination.  Returns None if there is a SocketError which prevents the source from being determined.  If no destination is specified, the function assumes well-known DNS server 4.2.2.1

#### ACL and Bitmask Tools

iupy.v4_bits_to_mask : Returns a string,  a netmask based upon the number of bits in relation to 0.0.0.0/bits.  Returns None if the mask is out of range.

ippy.v4_mask_to_bits : Returns a string, as the largest number of consecutive bits given an IP address.  This is far more forgiving than the ipaddress library, which may be useful to some.

iupy.v4_wildcard : This function returns a compliant wildcard for a given IP address.  This is similar to, but different than a host mask as a wildcard does not need to have a series of consecutive bits in order to be valid.

iupy.aclv4_hostmask : Takes an IPv4 host or host/mask and returns a Cisco-compatible string for use in ACL generation.

iupy.routev4_hostmask : Takes an IPv4 host or host/mask and returns a cisco-compatible string for use in generating static route statements.

#### Session Announcement Protocol

iupy.sap_segment : This function generates the segment portion of an RFC-2974 Session Announcement Protocol packet.  The segment still needs to but put on the wire with a UDP socket.  The keywords cover the fields the segment requires.  Returns None if any of the keywords are invalid or incomplete.