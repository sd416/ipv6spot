Hello everyone
IPv6Spot is a captive gateway system using IPv6 on OpenWRT firewall, All rights reserved to the author: Abdulkader Alrezej , You can use the code with the author's name mentioned.

- Main File Directory: /mnt/cerr Copy all files and folders to the directory: /mnt/cerr.
- File tree directory:
		db  >> Database encryption and backup files
		web_dist >> Web Dashboard Pages Files
		console >> Create virtual interfaces for IPv6Spot
		daa >> Main system database Sqlite3
		external_domains >> The addresses of the sites you want to block are stored using the IPv6Spot system.
		sn >> DNS server
		tba >> nftables rules file
		tv >> IPv6Spot system
		wb >> Back-End of the web control panel
		xt >> IPv6Spot Web Proxy  A Captive portal detection URLs 
		xtt >> IPv6Spot Web Proxy  B Respond to detection URLs 
# 1
- OpenWRT version used in the system OpenWRT 22.03.0 	x86/64 / Kernel Version	5.10.138
- Operating requirements:
  	NAT64 for a IPv6-only network (Jool) >> https://openwrt.org/docs/guide-user/network/ipv6/nat64
  	python3-lzma	3.10.13-2
  	python3-multiprocessing	3.10.13-2
  	python3-ncurses	3.10.13-2
	python3-openssl	3.10.13-2
	python3-pillow	9.5.0-2
	python3-pip	23.0.1-1
	python3-pkg-resources
	python3-ply	3.11-2
	python3-psutil	5.9.0-2
	python3-pycparser	2.21-2
	python3-pydoc	3.10.13-2
	python3-readline	3.10.13-2
	python3-setuptools	65.5.0-1
	python3-sqlite3	3.10.13-2
	python3-unittest	3.10.13-2
	python3-urllib	3.10.13-2
	python3-uuid	3.10.13-2
	python3-xml python3-xml	3.10.13-2
	python3	3.10.13-2
	python3-asyncio	3.10.13-2
	python3-base	3.10.13-2
	python3-bidict	0.21.2-2
	python3-cffi	1.16.0-1
	python3-cgi	3.10.13-2
	python3-cgitb	3.10.13-2
	python3-codecs	3.10.13-2
	python3-ctypes	3.10.13-2
	python3-dbm	3.10.13-2
	python3-decimal	3.10.13-2
	python3-dev	3.10.13-2
	python3-distutils	3.10.13-2
	python3-email	3.10.13-2
	python3-lib2to3	3.10.13-2
	python3-light	3.10.13-2
	python3-logging	3.10.13-2
	tc-full
	tc-mod-iptables
	sqlite3-cli	3410200-1
	libsqlite3-0	3410200-1
	ip6tables
	nftables
	xtables-nft
	kmod-ip6tables
	ip-full
	iputils-arping
	nmap
				kmod-veth
- must be disabled Dnsmasq, Also give root permission to the following files: sn tv wb xt xtt >> chmod +x *.py
- 
- Also nftable should be directed to the new nftable rules site at: /etc/init.d/nftables And replace this line " nft -f /etc/nftables.conf " with this line nft -f /mnt/cerr/tba
- 
- Run services when OpenWrt boots:

			procd_open_instance
			procd_set_param command /mnt/cerr/xt
			procd_set_param respawn
			procd_close_instance

			procd_open_instance
			procd_set_param command /mnt/cerr/xtt
			procd_set_param respawn
			procd_close_instance

			procd_open_instance
			procd_set_param command /mnt/cerr/tv
			procd_set_param respawn
			procd_close_instance

			procd_open_instance
			procd_set_param command /mnt/cerr/sn
			procd_set_param respawn
			procd_close_instance

			procd_open_instance
			procd_set_param command /mnt/cerr/wb
			procd_set_param respawn
			procd_close_instance
