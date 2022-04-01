# NITS-LAN-Proxy
##### Proxy Address :  ``172.16.199.40``
##### Proxy Port    :  ``8080``

## Ubuntu
Head to settings and open network.

Set network proxy to `manual`, and configure the proxy as following

 HTTP Proxy: `172.16.199.40:8080`
<br>
 HTTPS Proxy: `172.16.199.40:8080`

To get CLI tools to use the proxy, we need to configure two more files.

Edit the `.bashrc` file in your home directory to export the proxy environment variables as :

  `export HTTP_PROXY=http://172.16.199.40:8080`
<br>
  `export HTTPS_PROXY=https://172.16.199.40:8080`

To get `apt` to work, we need to configure **/etc/apt/apt.conf**, if the file doesn't exist, create it.

Add these two lines in the apt.conf file:
  `Acquire::http::proxy "http://172.16.199.40:8080/"`
<br>
  `Acquire::https::proxy "https://172.16.199.40:8080/"`

**Note: Don't confuse `apt.conf.d` with `apt.conf`**

## Router
Add the network gateway IP in ignore list.





