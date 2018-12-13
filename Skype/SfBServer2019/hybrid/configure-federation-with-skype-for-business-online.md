---
title: Configuración de Skype para entornos híbridos de negocio
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype para profesionales en línea.'
ms.openlocfilehash: b71ea92b5f7ce275dc5d1b5d2b7ece5be3c77ffc
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244007"
---
# <a name="configure-skype-for-business-hybrid"></a>Configuración de Skype para entornos híbridos de negocio

Para configurar Skype para entornos híbridos de negocio, debe:

- [Configurar el entorno local para federar con Office 365.](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [Configurar su entorno local para que confíe en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365.](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365.](#configure-server-to-server-authentication-if-required)

Tenga en cuenta que si dispone de Exchange local, es posible que desea configurar OAuth entre la organización local de Exchange y Skype para entornos en línea de negocio. Para obtener más información, vea [Administrar la autenticación de servidor a servidor en Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y [Planear la integración de Skype para empresas y Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Configure su servicio de perimetral local para federar con Office 365

Federación permite a los usuarios en su implementación local para comunicarse con usuarios de Office 365 en su organización. Para configurar la federación, ejecute el siguiente cmdlet en el Skype para Shell de administración de servidor empresarial:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Office 365

También debe configurar el entorno local para que confíe en Office 365 y habilitar el espacio de direcciones SIP compartido con Office 365. Esto significa que Office 365 puede hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que su entorno local, y pueden ser mensajes enrutados entre los usuarios alojados en local y en línea.  Para ello, mediante la configuración de un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com tal y como se describe a continuación.

En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com. Si lo hay, a continuación, quitarlo mediante el siguiente comando:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider como se indica a continuación: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365
  
Además del cambio realizado en la implementación local, debe realizar el cambio correspondiente en el inquilino de Office 365 para el espacio de direcciones SIP compartido habilitado con la implementación local.  

Para habilitar el espacio de direcciones SIP compartido en el inquilino de Office 365, establecer una sesión remota de PowerShell con Skype para profesionales en línea y, a continuación, ejecute el siguiente cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer como "True" hasta que la transferencia a en línea sea final y no quede ningún usuario en local. 
  
Para establecer una sesión remota de PowerShell con los equipos o Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea y cómo usar el Skype para el módulo del conector en línea de negocio, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Vea también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

