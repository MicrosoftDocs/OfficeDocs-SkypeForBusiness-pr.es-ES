---
title: Configurar Skype Empresarial híbrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumen: obtenga información sobre cómo configurar la interoperabilidad entre la implementación local y Skype Empresarial Online.'
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221454"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype Empresarial híbrido

Para configurar Skype Empresarial híbrido, haga lo siguiente:

- [Configure el servicio perimetral local para federar con Microsoft 365 u Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- Configure su entorno local para que confíe en [Microsoft 365 u Office 365 y](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)habilite el espacio de direcciones SIP compartido.
- [Habilite el espacio de direcciones SIP compartido en su organización de Microsoft 365 u Office 365.](#enable-shared-sip-address-space-in-your-organization)

Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre los entornos de Exchange local y Skype Empresarial Online. Para obtener más información, vea Administrar la autenticación de servidor a servidor en Skype Empresarial [Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y planear la integración de Skype Empresarial [y Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurar el servicio perimetral local para federar con Microsoft 365 u Office 365

La federación permite a los usuarios de la implementación local comunicarse con los usuarios de Microsoft 365 u Office 365 de su organización. Para configurar la federación, ejecute el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si el valor "-EnablePartnerDiscovery" se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de socios que no aparecen en la lista AllowedDomains. Si el valor se establece en $False, Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains. Este parámetro es necesario si se usa el enrutamiento del servicio DNS.

> [!NOTE]
> Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación local de Skype Empresarial y los usuarios de una organización de Skype Empresarial Online, consulte Configurar la compatibilidad de federación para un cliente de Skype Empresarial Online en [Skype Empresarial Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Microsoft 365 u Office 365

También debe configurar el entorno local para que confíe en Microsoft 365 u Office 365 y habilite el espacio de direcciones SIP compartido. Esto significa que Microsoft 365 u Office 365 pueden hospedar potencialmente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea.  Para ello, configure un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com, como se describe a continuación.

En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com. Si existe alguna, quítela mediante el siguiente comando:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

A continuación, cree un nuevo proveedor de hospedaje, use New-CsHostingProvider cmdlet como se muestra a continuación: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar el espacio de direcciones SIP compartido en la organización
  
Además del cambio realizado en la implementación local, deberá realizar el cambio correspondiente en su organización de Microsoft 365 u Office 365 para habilitar el espacio de direcciones SIP compartido con la implementación local.  

Para habilitar el espacio de direcciones SIP compartido en su organización, establezca una sesión remota de PowerShell con Skype Empresarial Online y, a continuación, ejecute el siguiente cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer "True" hasta que la conexión sea final y ningún usuario permanezca local. 
  
Para establecer una sesión remota de PowerShell con Teams o Skype Empresarial Online, primero debe instalar el módulo de conector de Skype Empresarial Online para Windows PowerShell, que puede obtener [aquí.](https://go.microsoft.com/fwlink/p/?LinkId=391911)
  
Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype Empresarial Online y cómo usar el módulo conector de Skype Empresarial Online, consulte Configurar el equipo para [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Vea también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
