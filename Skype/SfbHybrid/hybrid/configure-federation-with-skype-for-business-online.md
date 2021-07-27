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
description: 'Summary: Learn how to configure interoperability between your on-premises deployment and Teams.'
ms.openlocfilehash: a0e33c781e307785456698b20738dec2db02b8b4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510561"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurar Skype Empresarial híbrido

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Para configurar Skype Empresarial híbrido, haga lo siguiente:

- [Configure el servicio perimetral local para federar con Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).
- [Configure el entorno local para que confíe en Teams y habilite el espacio de direcciones SIP compartido.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Habilite el espacio de direcciones SIP compartido en su Teams organización](#enable-shared-sip-address-space-in-your-organization).

Si ha Exchange local, es posible que desee configurar OAuth entre los entornos Exchange local y Skype Empresarial Online. Para obtener más información, vea [Manage server-to-server authentication in Skype Empresarial Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate Skype Empresarial and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Configurar el servicio perimetral local para federar con Teams

La federación permite a los usuarios de la implementación local comunicarse con Teams y Skype Empresarial usuarios en línea de la organización. Para configurar la federación, ejecute el siguiente cmdlet en el Shell Skype Empresarial Server administración:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si el valor '-EnablePartnerDiscovery' se establece en $True, Skype Empresarial Server usará registros DNS para intentar detectar dominios de asociado que no aparecen en la lista AllowedDomains. Si el valor se establece en $False , Skype Empresarial Server solo se federará con los dominios que se encuentran en la lista AllowedDomains. Este parámetro es necesario si se usa el enrutamiento del servicio DNS.

> [!NOTE]
> Para obtener más información sobre cómo habilitar la federación entre los usuarios de la implementación de Skype Empresarial local y los usuarios de una organización de Microsoft 365, vea [Configuring federation support for a Microsoft 365 customer in Skype Empresarial Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Configurar el entorno local para habilitar el espacio de direcciones SIP compartido con Teams

También debe configurar el entorno local para que confíe en Teams y habilite el espacio de direcciones SIP compartido. Esta configuración significa Teams puede hospedar posiblemente cuentas de usuario para el mismo conjunto de dominios SIP que el entorno local, y los mensajes se pueden enrutar entre usuarios hospedados localmente y en línea. Debe configurar un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com como se describe a continuación.

En primer lugar, compruebe si ya tiene un proveedor de hospedaje con ProxyFqdn=sipfed.online.lync.com. Si existe una, quítela mediante el siguiente comando en el Shell Skype Empresarial Server administración:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

A continuación, cree un nuevo proveedor de hospedaje mediante el cmdlet New-CsHostingProvider siguiente: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Habilitar el espacio de direcciones SIP compartido en la organización
  
Además del cambio realizado en la implementación local, deberá realizar el cambio correspondiente en la organización de Teams para habilitar el espacio de direcciones SIP compartido con la implementación local.  

Para habilitar el espacio de direcciones SIP compartido en la organización, establezca una sesión remota de PowerShell con Teams y, a continuación, ejecute el siguiente cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> El atributo SharedSipAddressSpace debe permanecer "True" hasta que el traslado a línea sea definitivo y ningún usuario permanezca local. 
  
Para establecer una sesión remota de PowerShell con Teams (o Skype Empresarial Online), primero debe instalar el módulo Teams [PowerShell](/microsoftteams/teams-powershell-install). El Teams PowerShell reemplaza al módulo Skype busines Online Connector, que se ha retirado.
  
Después de instalar el módulo, puede establecer una sesión remota con los cmdlets siguientes:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Para obtener más información acerca de cómo establecer una sesión remota de PowerShell con Teams y cómo usar el módulo de PowerShell de Teams, vea Configurar el equipo para [Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  


## <a name="see-also"></a>Vea también

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
