---
title: 'Lync Server 2013: configurar la Federación con Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d690b21614ec416d82834761772cee05ee16f26e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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

La Federación permite que los usuarios de su implementación local se comuniquen con los usuarios de Office 365 de su organización. Para configurar la Federación, ejecute los siguientes cmdlets:

   ```
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar el inquilino de Skype empresarial online para un espacio de direcciones SIP compartido

Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico. Antes de intentar mover usuarios de Lync de local a Skype empresarial online, tendrá que configurar el inquilino de Office 365 para compartir el espacio de direcciones del Protocolo de inicio de sesión (SIP) compartido con la implementación local. Si no lo configura, es probable que se le presente el siguiente mensaje de error:

Move-CsUser: HostedMigration fault: Error=(510), Description=(El inquilino de este usuario no está habilitado para el espacio de dirección SIP compartido).

Para configurar un espacio de direcciones SIP compartido, establezca una sesión PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:

    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true

Para establecer una sesión PowerShell remota con Skype empresarial online, primero tiene que instalar el módulo Skype empresarial online para Windows PowerShell, que puede obtener aquí: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

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

Para obtener más información sobre cómo establecer una sesión remota de PowerShell con Skype empresarial online, consulte [conectarse a Skype empresarial online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Para obtener más información sobre el uso del módulo de PowerShell Skype empresarial online, consulte [usar Windows PowerShell para administrar Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Vea también


[Nuevo: CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

