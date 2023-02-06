# Rex Kerberos Protocol

## Useful resources

- [MS-KILE - Microsoft's Kerberos Extensions](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-kile/2a32282e-dd48-4ad9-a542-609804b02cc9)
- [Microsoft's Principal Name Canonicalization, with Realms and EncKDCRepPart changes to include encrypted-pa-data](https://datatracker.ietf.org/doc/html/rfc6806.html)
- [Newer Kerberos V5 spec](https://datatracker.ietf.org/doc/html/rfc4120)
- [Older Kerberos V5 spec - contains useful implementation details](https://datatracker.ietf.org/doc/html/rfc1510)
- [The RC4-HMAC Kerberos Encryption Types Used by Microsoft Windows](https://datatracker.ietf.org/doc/rfc4757/)
- [IANA - Kerberos Parameters](https://www.iana.org/assignments/kerberos-parameters/kerberos-parameters.xhtml)
- [Kerberos Version 5 GSS-API Mechanism](https://datatracker.ietf.org/doc/html/rfc1964)
- [Using Kerberos with a service, such as SMB](https://docs.microsoft.com/en-us/openspecs/windows_protocols/ms-authsod/a85e4e1c-58c1-4753-b42f-903deb663430)

## API Gotchas

The API fields `cname` and `client_name`, as well as `sname` and `server_name` are not interchangeable.
The `cname` and `sname` values are objects to be encoded into a Kerberos packet, but can be generated by specifying
simpler `client_name` or `server_name` strings.

## Development

### Decrypting encrypted Kerberos blobs

The Kerberos protocol makes use of encrypted values which will show as an opaque blob of hex characters in Wireshark.
Look at the module documentation in `modules/auxiliary/admin/kerberos/keytab.md` for ways to decrypt wireshark traffic using keytab files.