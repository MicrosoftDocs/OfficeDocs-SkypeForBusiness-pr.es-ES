---
title: Configurar la federación con Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Resumen: Conozca cómo configurar interoperabilidad entre su implementación local y Skype para los negocios en línea.'
ms.openlocfilehash: 1a08fdb9ad9522e50bc412adcc9214fff3bbb924
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a>Configurar la federación con Skype Empresarial Online
 
**Resumen:** Aprenda a configurar interoperabilidad entre su implementación local y Skype para los negocios en línea.
  
Siga los pasos de esta sección para configurar la interoperabilidad entre su implementación local y Skype para los negocios en línea.
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurar el servicio de extremo local para la federación con Skype para los negocios en línea

La federación permite a los usuarios en la implementación local para comunicarse con usuarios de Office 365 en su organización. Para configurar la federación, ejecute los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurar el Skype para los negocios en línea arrendatario para un espacio de direcciones compartido de SIP

Una dirección de protocolo de inicio de sesión (SIP) es un identificador único para cada usuario de una red, parecido a un número de teléfono o a una dirección de correo electrónico. Antes de intentar mover usuarios desde local a Skype para los negocios en línea, necesitará configurar el inquilino Office 365 para compartir el espacio de direcciones de protocolo de inicio de sesión (SIP) compartida con su implementación local. Si no lo configura, es probable que se le presente el siguiente mensaje de error:
  
Move-CsUser: Error de HostedMigration: Error=(510), descripción = (inquilino de este usuario no está habilitado para el espacio de direcciones compartido sip).
  
Para configurar un espacio de direcciones compartido de SIP, establecer una sesión remota de PowerShell con Skype para los negocios en línea y, a continuación, ejecute el siguiente cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local. 
  
Para establecer una sesión remota de PowerShell con Skype para los negocios en línea, primero debe instalar el Skype para el módulo del conector de negocios en línea para Windows PowerShell, que se puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para los negocios en línea, vea [conectarse a Lync Online por utilizando Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
  
Para obtener más información acerca de cómo utilizar el Skype para el módulo de PowerShell de conector negocios en línea, consulte [Uso de Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  
## <a name="see-also"></a>Vea también

#### 

[Nueva CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

