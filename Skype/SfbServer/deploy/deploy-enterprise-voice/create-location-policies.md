---
title: Crear directivas de ubicación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lea este tema para obtener información sobre cómo configurar directivas de ubicación de servicio de emergencia mejorado (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 4230d6ac1a820cb9612d58b21a2e5b6ae36d8f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822550"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Crear directivas de ubicación en Skype Empresarial Server

Lea este tema para obtener información sobre cómo configurar directivas de ubicación de servicio de emergencia mejorado (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial. 

Skype Empresarial Server usa una directiva de ubicación para habilitar clientes de Skype Empresarial para E9-1-1 durante el registro de clientes. Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1. Para obtener más información, vea [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

Las directivas de ubicación se definen con el Panel de control de Skype Empresarial o con el cmdlet [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)

> [!NOTE]
> Skype Empresarial Server ahora admite la configuración de varios números de emergencia para un cliente. Si desea configurar varios números de emergencia, debe seguir la información de [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and Configure multiple emergency numbers in Skype for [Business](configure-multiple-emergency-numbers.md). 

Puede editar la directiva de ubicación global y crear nuevas directivas de ubicación etiquetadas. Un cliente obtiene una directiva global cuando no se encuentra dentro de una subred con una directiva de ubicación asociada o cuando no se ha asignado directamente una directiva de ubicación al cliente. Las directivas etiquetadas se asignan a subredes o usuarios. 

Para crear una directiva de ubicación, debe usar una cuenta que sea miembro del grupo RTCUniversalServerAdmins, que sea miembro del rol administrativo CsVoiceAdministrator o que tenga permisos y derechos de administrador equivalentes.

Para obtener más información, vea [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Los cmdlets de este procedimiento usan una directiva de ubicación definida con los siguientes valores. Para obtener una descripción completa de los parámetros y valores del cmdlet, [consulte New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Elemento**                               | **Valor**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Aviso de declinación de responsabilidades** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | La directiva de la empresa requiere que establezcas una ubicación. Si no establece una ubicación, los servicios de emergencia no podrán localizarlo en una emergencia. Establezca una ubicación.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Para crear directivas de ubicación

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**

    > [!NOTE]
    > CsLocationPolicy producirá un error si la configuración de **PstnUsage** no está todavía en la lista global de PstnUsages.

2. Opcionalmente, ejecute el siguiente cmdlet para editar la directiva de ubicación global:

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Ejecute lo siguiente para crear una directiva de ubicación etiquetada.

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Ejecute el siguiente cmdlet para aplicar la directiva de ubicación etiquetada creada en el paso 3 a una directiva de usuario.

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
