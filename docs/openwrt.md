# D-Link Router IPv6 Specification v3.01
---
**Revision History**

| Version  | Date          |  <div style="width:3rem">Author</div>   | Modification                                        |
| -------- | ------------- | --------- | ------------------------------------------------------------------------------------ |
| v3.01b01    | 2021/06/18    | Joe Huang | Support D-Link Router Spec v3.01 on OpenWrt-v21.02.0-rc1|
| v3.01b02    | 2021/08/19    | Joe Huang | Support Stable and Opaque IIDs with SLAAC (RFC7217)|

## v3.01b02
---
**Description**

1. netifd and odhcp6c Support RFC7217
2. Enable libopenssl cryptyo for SHA1

**Revision**

	22c20981b297c67219eca4a71bea06add204f444

**Changed files**

	modified:   .config
	modified:   package/network/config/netifd/Makefile
	new file:   package/network/config/netifd/patches/001-rfc7217.patch
	modified:   package/network/ipv6/odhcp6c/Makefile
	modified:   package/network/ipv6/odhcp6c/files/dhcpv6.sh
	new file:   package/network/ipv6/odhcp6c/patches/002-rfc7217.patch

## v3.01b01
---
**Description**

1. Support RFC6092 (REC1-19, 21-23, 24, 31, 33, 36, 37, 49, 50)
2. Support RFC7084 L-14
3. Support RFC8585
4. Support D-Link IPv4aaS & IPv6 Autodetection
5. Extend odhcpd for dhcpv6_start/dhcpv6_end/dhcpv6_reserved
6. Modify odhcpd provide PD to follow D-Link method (According to PD length rather than prefix length)
7. Support 6RD hub and spoke mode
8. Support S46 Priority (RFC8026)

**Revision**

	148354fb4490bd343bf0c9efb2e282fb3860da40

**Changed files**

	modified:   .config
	modified:   package/network/config/firewall/Makefile
	modified:   package/network/config/firewall/files/firewall.config
	new file:   package/network/config/firewall/files/firewall.dynamic
	new file:   package/network/config/firewall/files/firewall.security
	modified:   package/network/config/firewall/files/firewall.user
	modified:   package/network/ipv6/6rd/files/6rd.sh
	new file:   package/network/ipv6/autowan/Makefile
	new file:   package/network/ipv6/autowan/files/auto4.sh
	new file:   package/network/ipv6/autowan/files/auto6.sh
	modified:   package/network/ipv6/odhcp6c/files/dhcpv6.script
	new file:   package/network/ipv6/odhcp6c/patches/001-S46-priority.patch
	new file:   package/network/services/odhcpd/patches/003-dhcpv6-start-end-and-pd-split.patch
	new file:   package/network/utils/iptables/patches/900-extension-CTFILTER.patch
	new file:   target/linux/mediatek/files-5.4/include/linux/netfilter_ipv6/ip6t_CTFILTER.h
	new file:   target/linux/mediatek/files-5.4/net/ipv6/netfilter/ip6t_CTFILTER.c
	modified:   target/linux/mediatek/mt7622/config-5.4
	new file:   target/linux/mediatek/patches-5.4/9001-RFC7084-L-14.patch
	new file:   target/linux/mediatek/patches-5.4/9002-CTFILTER.patch
