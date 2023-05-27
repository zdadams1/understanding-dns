<p align="center">

</p>

<h1>Understanding DNS</h1>

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)


A-Record Exercise
  Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
  Connect/log into Client-1 as an admin (mydomain\jane_admin)
  From Client-1 try to ping “mainframe” notice that it fails
  Nslookup “mainframe” notice that it fails (no DNS record)
  Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address
  Go back to Client-1 and try to ping it. Observe that it works

Local DNS Cache Exercise
  Go back to DC-1 and change mainframe’s record address to 8.8.8.8
  Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
  Observe the local dns cache (ipconfig /displaydns)
  Flush the DNS cache (ipconfig /flushdns). Observe that the cache is empty
  Attempt to ping “mainframe” again. Observe the address of the new record is showing up

CNAME Record Exercise
  Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”
  Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record
  On Client-1, nslookup “search”, observe the results of the CNAME record
