# Install Grafana on a Wago Device.
Be aware of the device partition sizes and space required for the installation and future apps/add-ons etc.
This example is based on 750-9301 (Compact Controller 100) with firmware 21, and requires some basic knowledge of Wago controllers.

## Setup
If the controller network card is not DHCP (default), this must be set to have an online connection to internet.

## Download Grafana
Latest version of Grafana is found on homepage [here.](https://grafana.com/grafana/download?pg=get&plcmt=selfmanaged-box1-cta1&platform=arm) <br/>
In this example we use Grafana v8.5.2.

Log in as root and make/select a folder:
```
cd /home
mkdir grafana
cd grafana
```
Get the Grafana tarball: 
```
wget https://dl.grafana.com/enterprise/release/grafana-enterprise-8.5.2.linux-armv7.tar.gz
```

## Unpack and install Grafana

Unpack Grafana in e.g. /home/grafana directory:
```
tar -xvf grafana-enterprise-8.5.2.linux-armv7.tar.gz
```
If you want, clean up unwanted files:
```
rm grafana-enterprise-8.5.2.linux-armv7.tar.gz
```
Set the environment variable ~/.profile to installation path:
```
# Grafana
export PATH=/home/grafana/grafana-8.5.2/bin:$PATH
```
Refresh:
```
. ~/.profile
```
## Test
```
grafana-cli -v
grafana-server -v
```
Quick and dirty start:
```
cd /home/grafana/grafana-8.5.2/bin
grafana-server start
```



