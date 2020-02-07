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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Descubra qué necesita para migrar al enrutamiento directo en la configuración de Skype Empresarial Online y Teams.
ms.openlocfilehash: 85b53bf33cd8f9015ea9294876a06da3532ad085
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836060"
---
# <a name="migrate-to-direct-routing"></a>Migrar a enrutamiento directo

Este artículo describe qué necesita para migrar al enrutamiento directo en la configuración de Skype Empresarial Online y Microsoft Teams. Este artículo aborda la migración desde...: 
 
- Sistema telefónico de Office 365 con planes de llamada (para Teams y Skype Empresarial Online) 
- Sistema telefónico de Office 365 con una conectividad RTC local en Skype Empresarial Server (para Skype Empresarial Online)  
- Sistema telefónico de Office 365 con una conectividad RTC local con la Edición de conector de nube (para Skype Empresarial Online)

  
Además de estos pasos de configuración, también debe configurar el controlador de borde de sesión (SBC) para redirigir las llamadas a la nueva ruta. Sin embargo, esto se escapa al ámbito de este documento. Si desea más información sobre este tema, consulte la documentación de su proveedor SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Estado final del aprovisionamiento de usuarios para varias opciones de conectividad RTC 

En la tabla siguiente se muestra el estado final de un usuario aprovisionado para las opciones de conectividad RTC seleccionadas con el Sistema telefónico Office 365. Solo se muestran los atributos relevantes para los servicios de voz.

|Atributos de objeto de usuario |Sistema telefónico con Planes de llamada|Sistema telefónico con una conectividad RTC local en Skype Empresarial Server|Sistema telefónico con conectividad con RTC local mediante conector de nube|Sistema telefónico con conectividad RTC local mediante enrutamiento directo|
|---|---|---|---|---|
|Cliente|Compatibilidad con Skype Empresarial |Skype Empresarial |Skype Empresarial |Teams|
|Licencias|Skype Empresarial Online</br>Plan 2</br></br>MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)</br></br></br>Planes de llamadas</br>Teams|Skype empresarial online (plan 2) (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Skype empresarial online (plan 2) (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Skype empresarial online (plan 2) (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)</br></br>Teams|
OnPremLineURI |N/D|El número de teléfono debe estar sincronizado desde el AD local. |El número de teléfono se puede administrar en un entorno local de Active Directory o en Azure Active Directory.|El número de teléfono se puede administrar en un entorno local de Active Directory o en Azure Active Directory. Sin embargo, si la organización tiene Skype Empresarial local, el número se debe sincronizar desde Active Directory local.|
|LineURI|Número de teléfono de llamada RTC|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Tiene un valor|Tiene un valor|Tiene un valor|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tiene un valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/D|N/D|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/D|N/D|True|
||||||

<sup>1</sup>Elegir el modo adecuado de TeamsUpgradePolicy depende del contexto. Lea cómo cambia la experiencia de voz en los diferentes modos en [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md).

En este sentido, Microsoft actualizó recientemente el «Centro de administración de Microsoft Teams» (también conocido como Portal Moderno) para reflejar el nuevo modelo de administración según los modos de coexistencia. En Portal Moderno, la configuración de TeamsUpgradePolicy ahora también establecerá automáticamente TeamsInteropPolicy en un valor uniforme, por lo que TeamsInteropPolicy ya no aparecerá en la interfaz de usuario. Sin embargo, los administradores que usen PowerShell deben establecer conjuntamente TeamsUpgradePolicy y TeamsInteropPolicy para asegurar el enrutamiento adecuado. Una vez completada la transición a TeamsUpgradePolicy, dejará de ser necesario establecer TeamsInteropPolicy.

Para más información, consulte [Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrar desde los Planes de llamadas

Para obtener más información sobre cómo migrar desde los Planes de llamadas, vea:

- [Configurar planes de llamadas](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice User](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Se recomienda quitar la información configurada anteriormente en el plan de licencias de la siguiente manera:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrar desde el Sistema telefónico de Office 365 con una conectividad RTC local en Skype Empresarial Server

Para más información sobre cómo migrar desde el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server, vea lo siguiente:

- [Planificación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implementación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Se recomienda quitar la información configurada anteriormente en el enrutamiento de voz de la siguiente manera:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> Si se configura un CsVoiceRoutingPolicy global, se recomienda quitar los usos de RTC asociados a esta directiva global. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrar desde el Sistema telefónico de Office 365 con una conectividad RTC local mediante la edición de conector en la nube 

Para más información sobre cómo migrar desde el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server, vea lo siguiente:

- [Planificación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implementación](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuración de usuario](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Se recomienda quitar la información configurada anteriormente en el enrutamiento de voz de la siguiente manera:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>VÍNCULOS RELACIONADOS

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

