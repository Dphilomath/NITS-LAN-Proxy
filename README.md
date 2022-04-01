# NITS-LAN-Proxy
A friendly guide to configuring proxy server on your systems

## Ubuntu
Head to settings and open network.

Set `Network Proxy` to `manual`, and configure the proxy as

*HTTP Proxy: `172.16.199.40:8080`*
<br>
*HTTPS Proxy: `172.16.199.40:8080`*

If you are using a router, add the network gateway ip in ignore list.

To get CLI tools to use the proxy, we need to configure two more files.

Edit the .bashrc file in your home directory to export the proxy environment vars:

_export HTTP_PROXY=http://172.16.199.40:8080_ \
_export HTTPS_PROXY=https://172.16.199.40:8080_

To get apt to work, we need to configure **/etc/apt/apt.conf**, if the file doesn't exist, create it.
Add these two lines in the apt.conf file:
_Acquire::http::proxy "http://172.16.199.40:8080/";_ \
_Acquire::https::proxy "https://172.16.199.40:8080/";_

**Note: Don't confuse apt.conf.d with apt.conf**





