# adblock-with-dnsmasq
A simple system for Pi-Hole like functionality using a local machine as a DNS Server.

## setup
* Install homebrew
* sudo get ds

## Testing
Test whether normal sites resolve properly with `dig google.com`. Should get something like
	```answersection
	;; ANSWER SECTION:
	google.com.		243	IN	A	172.217.6.14
	```
Test whether ad-serving domains are blocked with `dig 0-day.us`. If the answer is 0.0.0.0, that means your blocking was successful!
	```answersection
	;; ANSWER SECTION:
	0-day.us.		0	IN	A	0.0.0.0
	```
_(optional)_ Test if your custom mapping resolves properly with `dig server.dev`. Should get something like
	```answersection
	;; ANSWER SECTION:
	server.dev.		0	IN	A	192.168.0.115
	
	```