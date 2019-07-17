---
title: Migrar a enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Obtenga más información sobre lo que se necesita para migrar a enrutamiento directo desde una perspectiva de configuración de Skype empresarial online y Teams.
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759011"
---
# <a name="migrate-to-direct-routing"></a>Migrar a enrutamiento directo

Este artículo describe qué se necesita para migrar al enrutamiento directo desde una perspectiva de configuración de Skype empresarial online y Microsoft Teams. Este artículo trata de la migración de lo siguiente: 
 
- Sistema telefónico de Office 365 con planes de llamadas (para equipos y Skype empresarial online) 
- Sistema telefónico de Office 365 con conectividad RTC local en Skype empresarial Server (para Skype empresarial online)  
- Sistema telefónico de Office 365 con conectividad RTC local con la edición Cloud Connector (para Skype empresarial online)

  
Además de estos pasos de configuración, también se necesita la configuración en el controlador de borde de sesión (SBC) para enrutar las llamadas a la nueva ruta. Que está fuera del ámbito de este documento. Para obtener más información, consulte la documentación del proveedor de SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Aprovisionamiento de usuario del estado final de varias opciones de conectividad RTC 

En la tabla siguiente se muestra el estado final de un usuario aprovisionado para las opciones de conectividad RTC seleccionadas con el sistema telefónico de Office 365. Solo se muestran los atributos relevantes para la voz.

|Atributos del objeto de usuario |Sistema telefónico con planes de llamadas|Sistema telefónico con conectividad RTC local a través de Skype empresarial Server|Sistema telefónico con conectividad RTC local a través de un conector de nube|Sistema telefónico con conectividad RTC local a través de enrutamiento directo|
|---|---|---|---|---|
|Cliente|Skype empresarial o Teams |Skype Empresarial |Skype Empresarial |Microsoft Teams|
|License|Skype empresarial online</br>Plan 2</br></br>MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)</br></br></br>Planes de llamadas</br>Microsoft Teams|Plan 2 de Skype empresarial online (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Plan 2 de Skype empresarial online (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Plan 2 de Skype empresarial online (MCOProfessional o MCOSTANDARD</br></br></br>Sistema telefónico (MCOEV)</br></br>Microsoft Teams|
OnPremLineURI |N/D|El número de teléfono debe sincronizarse desde el anuncio local. |El número de teléfono puede administrarse en Active Directory local o en Azure Active Directory.|El número de teléfono puede administrarse en Active Directory local o en Azure Active Directory. Sin embargo, si la organización tiene Skype empresarial local, el número debe sincronizarse desde Active Directory local.|
|LineURI|Número de teléfono de llamadas RTC|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Tiene un valor|Tiene un valor|Tiene un valor|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tiene un valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly o islas|$Null|$Null|Islas o TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient: Lee la nota a continuación.|Teams o SfB |SfB|SfB|Microsoft Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/D|N/D|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/D|N/D|True|
||||||

<sup>1</sup> Elegir el modo adecuado de la TeamsUpgradePolicy depende del escenario. Obtenga más información sobre la experiencia de voz en diferentes modos de [migración e instrucciones de interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Tal como se anunció anteriormente, TeamsInteropPolicy se retirará (se dirigirá al final del tercer trimestre) y su funcionalidad se consolidará en TeamsUpgradePolicy. La interoperabilidad y la migración se administrarán con "modo de coexistencia", según lo determina TeamsUpgradePolicy, que ya está disponible. La selección del modo de usuario regirá el enrutamiento de las llamadas entrantes y los chats y en qué cliente puede iniciar conversaciones y llamar o programar reuniones. Aunque TeamsInteropPolicy se retirará, aún debe estar establecido en paralelo con TeamsUpgradePolicy durante la PhaseOut.  

Como parte de este esfuerzo, Microsoft actualizó recientemente el "centro de administración de Microsoft Teams" (también conocido como portal moderno) para reflejar el nuevo modelo de administración en función de los modos de coexistencia. En el portal moderno, la configuración de TeamsUpgradePolicy ahora también establecerá automáticamente TeamsInteropPolicy en un valor coherente, por lo que TeamsInteropPolicy ya no se expone en la interfaz de usuario. Sin embargo, los administradores que usen PowerShell deben establecer juntos TeamsUpgradePolicy y TeamsInteropPolicy para garantizar el enrutamiento adecuado. Una vez completada la transición a TeamsUpgradePolicy, ya no será necesario establecer TeamsInteropPolicy.

Para obtener más información, consulte la [Guía de migración e interoperabilidad para las organizaciones que usan Teams junto con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrar desde planes de llamadas

Para obtener más información sobre cómo migrar desde planes de llamadas, consulte:

- [Configurar planes de llamadas](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice usuario](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Se recomienda quitar la información del plan de licencias previamente configurado de la siguiente manera:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migración de un sistema telefónico de Office 365 con conectividad RTC local en Skype empresarial Server

Para obtener más información sobre cómo migrar desde un sistema telefónico con conectividad RTC local en Skype empresarial Server, consulte lo siguiente:

- [Planeación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implementar](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Se recomienda quitar la información de enrutamiento de voz configurada anteriormente de la siguiente manera:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migración de un sistema telefónico de Office 365 con conectividad RTC local a través de la edición de la nube para Cloud 

Para obtener más información sobre cómo migrar desde un sistema telefónico con conectividad RTC local a través del conector de nube, consulte lo siguiente:

- [Planeación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implementar](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuración de usuario](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Se recomienda quitar la información de enrutamiento de voz configurada anteriormente de la siguiente manera:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>VÍNCULOS RELACIONADOS

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Nuevo: CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

