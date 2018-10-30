---
title: 'Lync Server 2013: Configurar la federación con Lync Online'
TOCTitle: Configurar la federación con Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48276243
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la federación con Lync Online de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype Empresarial Online.

## Configure su servicio perimetral para federación con Skype Empresarial Online

La federación permite a los usuarios de su implementación local comunicarse con usuarios de Office 365 de su organización. Para configurar la federación, ejecute los cmdlets siguientes:

```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting
```
```
New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## Configure su inquilino de Skype Empresarial Online para un espacio de dirección SIP compartido

Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico. Antes de poder mover usuarios de Lync de su implementación local a Skype Empresarial Online, tendrá que configurar su inquilino de Office 365 para usar un espacio de dirección protocolo de inicio de sesión (SIP) compartido con la implementación local. Si no lo configura, es probable que se le presente el siguiente mensaje de error:

Move-CsUser: HostedMigration fault: Error=(510), Description=(El inquilino de este usuario no está habilitado para el espacio de dirección SIP compartido.)

Para configurar el espacio de dirección SIP compartido, establezca una sesión PowerShell remota con Skype Empresarial Online y, a continuación, ejecute el siguiente cmdlet:

```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

Para establecer una sesión PowerShell remota con Skype Empresarial Online, tendrá que instalar primero el módulo Skype Empresarial Online para Windows PowerShell, que puede obtener en: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:

```
Import-Module LyncOnlineConnector
```
```
$cred = Get-Credential
```
```
$CSSession = New-CsOnlineSession -Credential $cred
```
```
Import-PSSession $CSSession -AllowClobber
```
Si desea más información sobre cómo establecer una sesión PowerShell remota con Skype Empresarial Online, consulte [Conectar con Lync Online mediante Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Si desea más información sobre el uso del módulo de PowerShell Skype Empresarial Online, consulte [Administrar Lync Online con Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

## Vea también

#### Otros recursos

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

