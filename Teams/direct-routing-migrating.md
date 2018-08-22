---
title: Migración a enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Obtenga información sobre lo que necesita para migrar a enrutamiento directo desde un Skype para profesionales en línea y perspectiva de la configuración de los equipos.
ms.openlocfilehash: 859ab19162f8cf16cc419f7f871fc0059e4566d6
ms.sourcegitcommit: 1cfbf3d7cdd8b40db47aa92625aa73b63d6e86e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "22546600"
---
# <a name="migrating-to-direct-routing"></a>Migración a enrutamiento directo

Este artículo describe lo que se necesita para migrar a enrutamiento directo desde un Skype para profesionales en línea y Microsoft Teams perspectiva de la configuración. En este artículo se trata la migración entre las siguientes opciones: 
 
- Planes de sistema de teléfono de Office 365 con llamada (para los equipos y Skype para la empresa en línea) 
- Sistema de teléfono de Office 365 con conectividad de RTC local en Skype para Business Server (para Skype para la empresa en línea)  
- Sistema de teléfono de Office 365 con conectividad de RTC local mediante el uso de la edición de conector en la nube (por Skype para profesionales en línea)

  
Además de estos pasos de configuración, configuración también es necesario en el controlador de borde de sesión (SBC) para enrutar las llamadas a la nueva ruta. Que está fuera del ámbito de este documento. Para obtener más información, vea la documentación del proveedor SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Estado final de distintas opciones de conectividad de RTC de aprovisionamiento de usuarios 

En la siguiente tabla se muestra el estado final para un usuario aprovisionado para las opciones de conectividad RTC seleccionadas con el sistema telefónico de Office 365. Se muestran sólo los atributos relevantes para voz.

|Atributos de objeto de usuario |Sistema telefónico con Planes de llamada|Phone sistema con local conectividad RTC a través de Skype para Business Server|Sistema de teléfono con local conectividad RTC a través del conector en la nube|Sistema de teléfono con local conectividad RTC a través de enrutamiento directo|
|---|---|---|---|---|
|Cliente|Skype para profesionales o equipos |Skype Empresarial |Skype Empresarial |Microsoft Teams|
|Licencias|Profesionales de Skype en línea</br>Plan 2</br></br>MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)</br></br></br>Planes de llamadas</br>Microsoft Teams|Plan en línea de negocio de Skype 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Plan en línea de negocio de Skype 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefónico (MCOEV)|Plan en línea de negocio de Skype 2 (MCOProfessional o MCOSTANDARD</br></br></br>Sistema telefónico (MCOEV)</br></br>Microsoft Teams|
OnPremLineURI |N/D|El número de teléfono debe ser sincronizado desde el local AD. |El número de teléfono se puede administrar en Active Directory local o en Active Directory de Azure.|El número de teléfono se puede administrar en Active Directory local o en Active Directory de Azure. Sin embargo, si la organización tiene Skype local para la empresa, el número debe ser sincronizado desde Active Directory local.|
|LineURI|Número de teléfono de llamada de RTC|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|Establecer automáticamente desde el parámetro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|Hostedvoicemailpolicy, que |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Tiene un valor|Tiene un valor|Tiene un valor|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tiene un valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly o Islas|$Null|$Null|Islas o TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient: lea la nota a continuación.|Los equipos o SfB |SfB|SfB|Microsoft Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|Verdadero|N/D|N/D|Verdadero|
|TeamsCallingPolicy</br>AllowGroupCalling|Verdadero|N/D|N/D|Verdadero|
||||||

<sup>1</sup> Elegir el modo de derecho de la TeamsUpgradePolicy depende del escenario. Lea acerca de la experiencia de voz en diferentes modos de [migración e interoperabilidad instrucciones para las organizaciones con equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Como se ha anunciado anteriormente, TeamsInteropPolicy se deben retirarse (dirigido para el fin de T3) y su funcionalidad se consolidan en TeamsUpgradePolicy. Interoperabilidad y migración se administrarán utilizando "modo de coexistencia" según lo determinado por TeamsUpgradePolicy, que ahora está disponible. Selección del modo de usuario tendrán prioridad ambos enrutamiento de charlas y las llamadas entrantes y en el cliente que el usuario puede iniciar charlas y las llamadas o programar reuniones. Mientras se deben retirarse TeamsInteropPolicy, aún debe establecerse en paralelo con TeamsUpgradePolicy durante el phaseout.  

Como parte de este esfuerzo, Microsoft ha actualizado recientemente el "Microsoft equipos & Skype para profesionales centro de administración" (también conocido como Portal moderno) para reflejar el nuevo modelo de administración en función de los modos de coexistencia. En Portal moderno, configurar TeamsUpgradePolicy realizarán ahora automáticamente también establezca TeamsInteropPolicy en valor coherente, por lo que TeamsInteropPolicy ya no se expone en la interfaz de usuario. Sin embargo, los administradores con PowerShell aún deben establecer TeamsUpgradePolicy tanto TeamsInteropPolicy juntos para garantizar el enrutamiento correcto. Una vez finalizada la transición a TeamsUpgradePolicy, ya no será necesario establecer también TeamsInteropPolicy.

Para obtener más información, consulte [migración e interoperabilidad instrucciones para las organizaciones que utilizan los equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrar de planes de llamada

Para obtener más información sobre la migración de los planes de llamada, vea:

- [Configurar Planes de llamada](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice usuario](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/en-us/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Se recomienda que quite información del plan de licencias previouslycconfigured como se indica a continuación:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrar desde el sistema telefónico de Office 365 con conectividad de RTC local en Skype para Business Server

Para obtener más información acerca de la migración desde el sistema telefónico con conectividad de RTC local en Skype para Business Server, consulte lo siguiente:

- [Planeación](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implementación de](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Se recomienda que quite voz configurado previamente información de enrutamiento de la siguiente manera:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migración desde el sistema telefónico de Office 365 con conectividad de RTC local a través de la nube conector Edition 

Para obtener más información acerca de la migración desde el sistema telefónico con conectividad de RTC local a través del conector en la nube, consulte lo siguiente:

- [Planeación](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implementación de](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuración de usuario](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Se recomienda que quite voz configurado previamente información de enrutamiento de la siguiente manera:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>VÍNCULOS RELACIONADOS

[Guía de interoperabilidad y migración para las organizaciones que utilizan los equipos junto con Skype para la empresa](migration-interop-guidance-for-teams-with-skype.md)

[GRANT CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Nueva CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

