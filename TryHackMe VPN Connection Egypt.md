# TryHackMe VPN Connection Egypt

## Introduction

Dear Egyptian Cybersecurity Students,

This repo is meant to solve the problem of TryHackMe VPN connection for you, to be able to use your machine to solve rooms instead of the 1-h HackBox.
Hope you all find this useful. Follow the steps below to solve the VPN connection problem.

Best Regards,

Cyberus Stud Team

## Solution - Linux (Debian)

### Installing cloudflare-warp

1. Navigate to [Cloudflare's Website](https://pkg.cloudflareclient.com/packages/cloudflare-warp) to download the client.
2. Choose your operating system, prefered (Debian Bullseye) for kali or parrot.
3. Click Download.
4. After downloading the pkg, run the following command on the download file to install the package:
```cmd
sudo dpkg -i "pkg filename"
```

### Using cloudflare-warp

1. Register the client.
```cmd
warp-cli register
```
2. Connect with the client.
```cmd
warp-cli connect
```
3. Run the following `curl` command and verify that `warp=on`.
```cmd
curl https://www.cloudflare.com/cdn-cgi/trace/
```

### Connecting to TryHackMe VPN

Now your machine is ready to connect to TryHackMe's VPN as long as the wrap is up.

1. On TryHackMe, navigate to `Access`.
2. Choose `EU-Regular-*` and click on `Download My Configuration File`.
3. Connect to the vpn using `openvpn` client.
```cmd
sudo openvpn "vpn filename"
```
4. Check your connection on TryHackMe.
5. Congratulations! your maching is now connected to TryHackMe's network.

## Problems You Might Face

### Connecting with SSH

Sometimes whenever you try to connect to a maching through `SSH` some problems might arise. So the easy solution to this is to turn off the wrap after connecting to the VPN.
```cmd
warp-cli disconnect
```

## Thanks
