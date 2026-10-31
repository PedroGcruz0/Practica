# Practica

secpol.msc -> Directiva de bloqueo de cuentas: Umbral = 3 intentos, Duración = 30 min.

Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol -NoRestart && Set-SmbServerConfiguration -EnableSMB1Protocol $false

New-NetFirewallRule -DisplayName 'Restringir_RDP_TI' -Direction Inbound -Protocol TCP -LocalPort 3389 -RemoteAddress '192.168.1.0/24'

Rename-LocalUser -Name 'Administrator' -NewName 'Admin_Sec_USS' && Disable-LocalUser -Name 'Guest'
