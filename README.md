<h1 align="center">
  Vulnerable-AD
  <br>
</h1>

Create a vulnerable active directory that's allowing you to test most of active directory attacks in local lab

### Main Features
- Randomize Attacks
- Full Coverage of the mentioned attacks
- you need run the script in DC with Active Directory installed 
- Some of attacks require client workstation
  
### Supported Attacks
- Abusing ACLs/ACEs
- Kerberoasting
- AS-REP Roasting
- Abuse DnsAdmins
- Password in Object Description
- User Objects With Default password (Changeme123!)
- Password Spraying
- DCSync
- Silver Ticket
- Golden Ticket 
- Pass-the-Hash
- Pass-the-Ticket
- SMB Signing Disabled

### Example
```powershell
# if you didn't install Active Directory yet , you can try 
Install-ADDSForest -CreateDnsDelegation:$false -DatabasePath "C:\\Windows\\NTDS" -DomainMode "7" -DomainName "cs.org" -DomainNetbiosName "cs" -ForestMode "7" -InstallDns:$true -LogPath "C:\\Windows\\NTDS" -NoRebootOnCompletion:$false -SysvolPath "C:\\Windows\\SYSVOL" -Force:$true
# if you already installed Active Directory, just run the script !
IEX((new-object net.webclient).downloadstring("https://raw.githubusercontent.com/wazehell/vulnerable-AD/master/vulnad.ps1"));
Invoke-VulnAD -UsersLimit 100 -DomainName "cs.org"
```

### TODO
- Play with workstations !
- Click close issue button on github
