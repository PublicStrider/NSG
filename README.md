# NSG Tinkering With Wireshark and Other Tools
This is a brief writeup on setting observing traffic.

Connect into DC-1 as your domain admin account (mydomain.com\justin_admin) Connect/log into Client-1 as an admin (mydomain\justin_admin). From Client-1,  ping “mainframe” and notice that it fails Nslookup “mainframe”, also notice that it fails (no DNS record). Now Create a DNS A-record on DC-1 for “mainframe” and point to DC-1’s Private IP address, and then go back to Client-1 and then ping it. Check to see if that works.

Now lets check back on the DC-1 and change mainframe’s record address to 8.8.8.8 , and then go back to Client-1 and ping the “mainframe” again. See if it still pings the old address, Check the local dns cache (ipconfig /displaydns), now flush the DNS cache (ipconfig /flushdns). Verify that the cache is empty and look to ping the “mainframe” again. The address of the new record should now show.



Now back at DC-1, create a CNAME record that points the host “search” to “www.google.com” . Check on Client-1 and attempt to ping “search”, see the results of the CNAME record On Client-1, and nslookup “search”, verify the results of the CNAME record.

