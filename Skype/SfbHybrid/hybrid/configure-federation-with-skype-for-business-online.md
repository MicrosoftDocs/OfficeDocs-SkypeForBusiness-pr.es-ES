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
description: 'Resumen: Obtenga información sobre cómo configurar la interoperabilidad entre su implementación local y Skype empresarial online.'
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221454"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype Empresarial híbrido

Para configurar Skype Empresarial híbrido, haga lo siguiente:

- [Configure el servicio perimetral local para federar con Microsoft 365 u Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).
- [Configure el entorno local para confiar en Microsoft 365 u Office 365 y habilitar el espacio de direcciones SIP compartido](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).
- [Habilite el espacio de direcciones SIP compartido en su organización de Microsoft 365 u Office 365](#enable-shared-sip-address-space-in-your-organization).

Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre su entorno local de Exchange y los entornos de Skype empresarial online. Para obtener más información, vea [Manage Server-to-Server Authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y [plan to Integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurar el servicio perimetral local para federar con Microsoft 365 u Office 365

La Federación permite que los usuarios de su implementación local se comuniquen con los usuarios de Microsoft 365 o Office 365 en su organización. Para configurar la Federación, ejecute el siguiente cmdlet en el shell de administración de Skype empresarial Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si el valor "-EnablePartnerDiscovery" se establece en $True, Skype empresarial Server usará los registros DNS para intentar detectar dominios asociados que no aparezcan en la lista AllowedDomains. Si el valor se establece en $False, Skype empresarial Server solo se federe con los dominios que se encuentran en la lista AllowedDomains. Este parámetro es necesario si se usa el enrutamiento del servicio DNS.

> [!NOTE]
> Para obtener más información acerca de cómo habilitar la Federación entre los usuarios de su implementación local de Skype empresarial y los usuarios de una organización de Skype empresarial online, consulte [Configuring Federation Support for a Skype for Business online Customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Microsoft 365 u Office 365

También debe configurar el entorno local para confiar en Microsoft 365 u Office 365 y habilitar el espacio de direcciones SIP compartido. Esto significa que Microsoft 365 u Office 365 pueden alojar cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados de forma local y en línea.  Para ello, configure un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com tal y como se describe a continuación.

En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn = sipfed. online. Lync. com. Si la hay, quítela mediante el siguiente comando:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider de la siguiente manera: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar el espacio de direcciones SIP compartido en la organización
  
Además del cambio realizado en la implementación local, tendrá que hacer el cambio correspondiente en su organización de Microsoft 365 u Office 365 para habilitar el espacio de direcciones SIP compartido con su implementación local.  

Para habilitar el espacio de direcciones SIP compartido en su organización, establezca una sesión de PowerShell remota con Skype empresarial online y, a continuación, ejecute el siguiente cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer "true" hasta que el movimiento a en línea sea final y ningún usuario permanece local. 
  
Para establecer una sesión de PowerShell remota con Microsoft Teams o Skype empresarial online, primero debe instalar el módulo de conector de Skype empresarial online para Windows PowerShell, que puede obtener [aquí](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Después de instalar el módulo, puede establecer una sesión remota con los siguientes cmdlets:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Para obtener más información sobre cómo establecer una sesión de PowerShell remota con Skype empresarial online y cómo usar el módulo conector de Skype empresarial online, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Vea también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
