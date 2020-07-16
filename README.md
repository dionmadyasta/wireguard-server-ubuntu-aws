

# Install Wireguard Server di AWS Instance dengan Ubuntu Server 18.04

1. Deploy Ubuntu Server 18.04 di AWS
2. Buat Security Group, ijinkan inbound traffic untuk SSH 22 dan Custom UDP 54321 untuk wireguard

## How use

### Installation
```
git clone https://github.com/dionmadyasta/wireguard-server-ubuntu-aws.git
cd wireguard_aws
sudo ./initial.sh
```

The `initial.sh` script removes the previous Wireguard installation (if any) using the `remove.sh` script. It then installs and configures the Wireguard service using the `install.sh` script. And then creates a client using the `add-client.sh` script.

### Add new customer
`add-client.sh` - Script to add a new VPN client. As a result of the execution, it creates a configuration file ($CLIENT_NAME.conf) on the path ./clients/$CLIENT_NAME/, displays a QR code with the configuration.

```
sudo ./add-client.sh
#OR
sudo ./add-client.sh $CLIENT_NAME
```

### Reset customers
`reset.sh` - script that removes information about clients. And stopping the VPN server Winguard
```
sudo ./reset.sh
```

### Delete Wireguard
```
sudo ./remove.sh
```
