# DNS Toolkit module documentation

DNS Toolkit is a ProcessWire module that gives easy access to DNS checking functions, including Spamhaus checker.

To use its functions, use either `$dns->function()` or `wire("dns")->function()`.

DNS Toolkit requires PHP’s Intl  extension as it converts international domain names to ascii, which would otherwise give errors. 

## Available functions

### $dns->isValidHost($host, $type)

Checks if a domain IP has a DNS record for a record type. Can be fed an email address to check if its domain is valid.

#### Parameters

string $host : Any string, but should be a host name, IP or email to get valid results.
string $type : Valid values are MX (default), A, NS, SOA, PTR, CNAME, AAAA, A6, SRV, NAPTR, TXT, ANY.

#### Returns

True if the host is valid, false if not.

### $dns->isSpam($string)

Checks if a domain or IP is in the Spamhaus database. Make sure your server can resolve the host, some DNS like the Google Public DNS server might not resolve to Spamhaus, giving erroneous results.

#### Parameters

string $string : Can take any string, but preferably an URL, an email address, a host or IP. The host in those don't need to be valid, the function will take care of making sure it is.

#### Returns

True if the host is Spamhaus listed.
False if it's not.
Null if the host is invalid.

## Versions

1.0.0 - Initial commit

## License

The MIT License (MIT)

Copyright (c) 2014 Pierre-Luc Auclair

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.