Hello everyone 
IPv6Spot is a captive gateway system using IPv6 on OpenWRT firewall, All rights reserved to the author: Abdulkader Alrezej , You can use the code with the author's name mentioned.
- File tree inside OpenWRT firewall:
- Main File Directory: /mnt/cerr Copy all files and folders to the directory: /mnt/cerr.
- File tree directory:
  -- db  >> Database encryption and backup files
  -- web_dist >> Web Dashboard Pages Files
  -- console >> Create virtual interfaces for IPv6Spot
  -- daa >> Main system database Sqlite3
  -- external_domains >> The addresses of the sites you want to block are stored using the IPv6Spot system.
  -- sn >> DNS server
  -- tba >> nftables rules file
  -- tv >> IPv6Spot system
  -- wb >> Back-End of the web control panel
  -- xt >> IPv6Spot Web Proxy  A Captive portal detection URLs 
  -- xtt >> IPv6Spot Web Proxy  B Respond to detection URLs 
  
