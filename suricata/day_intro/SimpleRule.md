# Writing Rule

> Do not write rules, buy from professionals !

see https://redmine.openinfosecfoundation.org/projects/suricata/wiki/Suricata_Rules

```
alert tcp any any -> any 443 (msg:"SURICATA Port 443 but not SSL/TLS"; app-layer-protocol:!tls; threshold: type limit, track by_src, seconds 180, count 1; classtype:bad-unknown;  sid:990001;)
```

A rule consists of the following:
* action
* header
* rule-options

## Action


* alert - This is the action we want to perform on the rule

* pass - This can be compared to “ACCEPT” in iptables, in that if the packet matches this rule it’ll be accepted through.
* drop - The packet doesn’t get processed any further down the chain and the sender isn’t notified. This is akin to the “DROP” target in iptables, where it will silently remove the packet from the network stack.
* reject - This acts the same as drop but will also notify the sender that the packet has been removed from the stack.

## header

* First keyword: protocol with protocol recognition
* Second part: IP params includin variable

## Rule options

* content matching
* meta data
* threshold configuration

## Write some simple signature

* Write rules on query to a specific website http_hostname
* Check some text in the content of the response 
* Write a rules checking TLS fingerprint of a HTTPS website
* Alert on all PNG files seen on HTTP and SMTP
