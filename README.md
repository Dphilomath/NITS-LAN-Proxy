# NITS LAN Proxy
```
Proxy Address :  172.16.199.40
Proxy Port    :  8080
```

## Ubuntu

Head to settings and open network.
Set network proxy to `manual`, and configure the proxy as following
```
HTTP Proxy: 172.16.199.40:8080
HTTPS Proxy: 172.16.199.40:8080
```

<img width="50%" src="https://user-images.githubusercontent.com/23384886/161261232-607e482f-9e9d-43e7-9470-8cd7c7acf28f.png"/>


To get CLI tools to use the proxy, we need to configure two more files.

#### File 1 : `.bashrc` file in your home directory (hidden file)

Edit the file and export these proxy environment variables
```
export HTTP_PROXY=http://172.16.199.40:8080
export HTTPS_PROXY=http://172.16.199.40:8080
 ```
 
 <img width="50%" src="https://user-images.githubusercontent.com/23384886/161261536-725a9678-9f02-4eb7-966d-c1ea96c4e87f.png"/>

#### File 2 : `/etc/apt/apt.conf` 

If the file doesn't exist, create it and add these two lines in the apt.conf file:
```
Acquire::http::proxy "http://172.16.199.40:8080/"
Acquire::https::proxy "http://172.16.199.40:8080/"
```
*Note: Don't confuse `apt.conf.d` with `apt.conf`*

## Router
Add the network gateway IP in ignore list.
