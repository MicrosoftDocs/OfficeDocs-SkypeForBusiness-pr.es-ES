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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030724"
---
# <a name="configure-skype-for-business-hybrid"></a>Configuración de Skype para entornos híbridos de negocio

Para configurar Skype para entornos híbridos de negocio, debe:

- [Configurar la federación](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [Configurar un espacio de direcciones de protocolo de inicio de sesión (SIP) compartida](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [Configurar la autenticación de servidor a servidor si es necesario](#configure-server-to-server-authentication-if-required)
  
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
  
Para establecer una sesión remota de PowerShell con Skype para profesionales en línea, primero debe instalar el Skype para módulo del conector empresarial en línea para Windows PowerShell, que se puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype para profesionales en línea y cómo usar el Skype para el módulo del conector en línea de negocio, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="configure-server-to-server-authentication-if-required"></a>Configurar la autenticación de servidor a servidor si es necesario

En función del tipo de entorno híbrido que está configurando, deberá configurar la autenticación de servidor a servidor.  Para obtener más información, vea [Administrar la autenticación de servidor a servidor en Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).


## <a name="see-also"></a>Vea también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

