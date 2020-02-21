---
title: 'Lync Server 2013: configurar la Federación con Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 957a0f338d0669d0c99570b541d6ddb4753c1145
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Configurar la Federación de Lync Server 2013 con Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-08-15_

Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype empresarial online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurar el servicio perimetral local para la Federación con Skype empresarial online

La Federación permite que los usuarios de la implementación local se comuniquen con los usuarios de Office 365 de su organización. Para configurar la Federación, ejecute los siguientes cmdlets:

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar el inquilino de Skype empresarial online para un espacio de direcciones SIP compartido

Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, similar a un número de teléfono o a una dirección de correo electrónico. Antes de intentar mover a los usuarios de Lync de forma local a Skype empresarial online, deberá configurar el inquilino de Office 365 para compartir el espacio de direcciones del Protocolo de inicio de sesión (SIP) compartido con su implementación local. Si no está configurado, es posible que vea el siguiente mensaje de error:

Move-CsUser: HostedMigration error: error = (510), descripción = (el inquilino del usuario no está habilitado para el espacio de direcciones SIP compartido).

Para configurar un espacio de direcciones SIP compartido, establezca una sesión de PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Para establecer una sesión de PowerShell remota con Skype empresarial online, primero debe instalar el módulo de Skype empresarial online para Windows PowerShell, que puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).

Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Para obtener más información acerca de cómo establecer una sesión de PowerShell remota con Skype empresarial online, consulte [conectarse a Skype empresarial online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Para obtener más información sobre el uso del módulo de PowerShell de Skype empresarial online, vea [using Windows PowerShell to Manage Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Consulta también


[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

