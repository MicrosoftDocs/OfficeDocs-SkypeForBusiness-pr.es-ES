---
title: Configurar la federación con Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.'
ms.openlocfilehash: 24a3d95c1da90abd083835a9838e246d25c8a954
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504449"
---
# <a name="configure-federation-with-skype-for-business-online"></a>Configurar la federación con Skype Empresarial Online
 
**Resumen:** Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.
  
Siga los pasos descritos en esta sección para configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurar el servicio de borde de local para la federación con Skype para profesionales en línea

Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización. Para configurar la federación, ejecute los siguientes cmdlets en el Skype para Shell de administración de servidor empresarial:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar su Skype para inquilino empresarial en línea para un espacio de direcciones SIP compartido

Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico. Antes de intentar mover usuarios de local a Skype para profesionales en línea, debe configurar el inquilino de Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartidos con la implementación local. Si no lo configura, es probable que se le presente el siguiente mensaje de error:
  
Move-CsUser: Tolerancia HostedMigration: Error=(510), descripción = (inquilino de este usuario no está habilitado para el espacio de direcciones sip compartido).
  
Para configurar un espacio de direcciones SIP compartido, establecer una sesión remota de PowerShell con Skype para profesionales en línea y, a continuación, ejecute el siguiente cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local. 
  
Para establecer una sesión remota de PowerShell con Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:
  
```
Import-Module SkypeOnlineConnector
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

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea, consulte [Connecting to Lync Online por Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
  
Para obtener más información acerca del uso de la Skype para el módulo de PowerShell de conector en línea de negocio, vea [Using Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  
## <a name="see-also"></a>Vea también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)