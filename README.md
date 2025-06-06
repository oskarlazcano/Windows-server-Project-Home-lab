# Windows-server-Project-Home-lab

### 1. Install DHCP and DNS Roles

Using Server Manager or PowerShell:

```powershell
Install-WindowsFeature -Name DHCP -IncludeManagementTools
Install-WindowsFeature -Name DNS -IncludeManagementTools

### 3. Configure DNS

#### Forward Lookup Zone:
1. Open **DNS Manager**
2. Right-click **Forward Lookup Zones → New Zone**
3. Select **Primary Zone**, zone name: `contoso.local`
4. Allow secure dynamic updates

#### Add Host Records:
- `dc1.contoso.local → 192.168.1.10`
- `client1.contoso.local → 192.168.1.101` (optional static or reserved)

#### Reverse Lookup Zone:
1. Right-click **Reverse Lookup Zones → New Zone**
2. Zone Type: **Primary**
3. Network ID: `192.168.1`
4. Create **PTR records** for existing hosts
