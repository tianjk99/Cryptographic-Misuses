BUG_Author: 
Kelsey Tian

Affected version: 
MeshCentral

Vendor: 
https://github.com/Ylianst/MeshCentral/tree/master

Software: 
https://github.com/Ylianst/MeshCentral/tree/master

Vulnerability File:
1. mpsserver.js, line 48;
   mpsserver.js, line 51;
   agents\modules_meshcmd\amt-redir-duk.js, line 47;
   rdp\core\layer.js, line 153;
   rdp\core\layer.js, line 190;
   swarmserver.js, line 126;
   
2. mpsserver.js, line 51;

3. rdp\protocol\pdu\sec.js, line 461;
   rdp\protocol\nla.js, line 304;
   rdp\protocol\nla.js, line 284;

Description:
1. In the application's network request, the rejectUnauthorized attribute is set to false. This property is used to verify the server's certificate in HTTPS connections. Setting rejectUnauthorized to false can cause applications to bypass certificate

2. Use insecure TLS versions (such as SSLv3, TLSv1.0, and TLSv1.1) in your application. These TLS versions have known security vulnerabilities and weaknesses, exposing applications to potential security risks.

3. Use an insecure HMAC algorithm: HMAC-MD5, which is widely considered to be a less secure algorithm and is not recommended for continued use in a secure environment because it is susceptible to exhaustive searches and brute force attacks. Therefore, in practical applications, more secure algorithms such as HMAC-SHA1 should be used first.
