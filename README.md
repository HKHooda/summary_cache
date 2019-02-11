Summary Cache: 
Objective: Show how a probabilistic data structure like bloom filter can reduce network bandwidth usage. We set up a “distributed proxy” environment where each proxy will maintain some cache. Each proxy will maintain a summary of all other proxies in the form of bloom filters. 

Dependencies:
1. pip2.7 install requests 
2. pip2.7 install mmh3
3. pip2.7 install bitarray

Steps to run and test the code:
1. Git clone the code on all the proxy server. 
2. List all the participating host’s ip address in proxy_list.txt including localhost.
3. Place all the caches in cache folder. Here the folder’s name will be the website’s name 
4. Run proxy1.py on the main proxy server that is directly connected to client.
   $ python  proxy1.py
5. Run proxy2.py on all the secondary proxy servers.
   $ python proxy2.py
6. Run initialize and update daemon script on all the proxy servers.
   $ python initializeAndUpdateDaemon.py [time interval in s] [false positive probability] 
     Ex: $ python initializeAndUpdateDaemon.py 300 0.01
7. You can test using any web browser like chrome. Remember to set proxy to proxy1’s ip

