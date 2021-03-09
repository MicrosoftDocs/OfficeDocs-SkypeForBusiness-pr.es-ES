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
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569222"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype Empresarial híbrido

Para configurar Skype Empresarial híbrido, haga lo siguiente:

- [Configure el servicio perimetral local para federar con Microsoft 365 u Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).
- Configure el entorno local para que confíe [en Microsoft 365 u Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)y habilite el espacio de direcciones SIP compartido.
- [Habilitar el espacio de direcciones SIP compartido en su organización de Microsoft 365 u Office 365](#enable-shared-sip-address-space-in-your-organization).

Tenga en cuenta que si tiene Exchange local, es posible que desee configurar OAuth entre los entornos locales de Exchange y Skype Empresarial Online. Para obtener más información, vea  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) y Plan to integrate Skype for Business and [Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurar el servicio perimetral local para federar con Microsoft 365 u Office 365

La federación permite a los usuarios de la implementación local comunicarse con usuarios de Microsoft 365 u Office 365 de la organización. Para configurar la federación, ejecute el siguiente cmdlet en el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si el valor '-EnablePartnerDiscovery' se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de asociado que no aparecen en la lista AllowedDomains. Si el valor se establece en $False, Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains. Este parámetro es necesario si se usa el enrutamiento del servicio DNS.

> [!NOTE]
> Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación local de Skype Empresarial y los usuarios de una organización de Skype Empresarial Online, vea [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Microsoft 365 u Office 365

También debe configurar el entorno local para que confíe en Microsoft 365 u Office 365 y habilite el espacio de direcciones SIP compartido. Esto significa que Microsoft 365 u Office 365 pueden hospedar posiblemente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea.  Para ello, configure un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com como se describe a continuación.

En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com. Si existe, quítela mediante el siguiente comando:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

A continuación, cree un nuevo proveedor de hospedaje, use el cmdlet New-CsHostingProvider de la siguiente manera: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar el espacio de direcciones SIP compartido en la organización
  
Además del cambio que realizó en la implementación local, deberá realizar el cambio correspondiente en su organización de Microsoft 365 u Office 365 para habilitar el espacio de direcciones SIP compartido con la implementación local.  

Para habilitar el espacio de direcciones SIP compartido en su organización, establezca una sesión remota de PowerShell con Skype Empresarial Online y, a continuación, ejecute el siguiente cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer "True" hasta que el traslado a línea sea definitivo y ningún usuario permanezca local. 
  
Para establecer una sesión remota de PowerShell con Teams o Skype Empresarial Online, primero debe instalar el módulo [de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
  
Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Skype Empresarial Online y cómo usar el módulo Skype Empresarial Online Connector, vea Configurar el equipo para [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Consulte también

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
