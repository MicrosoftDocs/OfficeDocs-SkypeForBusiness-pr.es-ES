---
title: Crear directivas de ubicación en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lea este tema para aprender a configurar las directivas de ubicación de servicio de emergencia (E9-1-1) de Skype mejorado en Business Server Enterprise Voice.
ms.openlocfilehash: 2e3c25586c09e8cb517f781ec9e9dc33c58d81da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223532"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Crear directivas de ubicación en Skype para Business Server

Lea este tema para aprender a configurar las directivas de ubicación de servicio de emergencia (E9-1-1) de Skype mejorado en Business Server Enterprise Voice. 

Skype para Business Server usa una directiva de ubicación para habilitar Skype para clientes empresariales para E9-1-1 durante el registro de cliente. Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1. Para obtener más información, vea [Planear las directivas de ubicación para Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).

Definir las directivas de ubicación mediante el Skype para el Panel de Control o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .

> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencias para un cliente. Si desea configurar varios números de emergencias, debe seguir la información de [planeación para varios números de emergencias en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) y [configurar varios números de emergencias en Skype para la empresa](configure-multiple-emergency-numbers.md). 

La directiva de ubicación global puede editarse y crear otras directivas de ubicación con etiqueta. Un cliente obtiene una directiva global si no se ubica en una subred que tenga asociada una directiva de ubicación o, bien, si el cliente no tiene asignada directamente una directiva de ubicación. Las directivas con etiquetas se asignan a subredes o usuarios.   

Para crear una directiva de ubicación, debe usar una cuenta que pertenezca al grupo RTCUniversalServerAdmins, o bien que tenga el rol administrativo CsVoiceAdministrator o derechos y permisos de administrador equivalentes.

Para obtener más información, vea [Planear las directivas de ubicación para Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Los cmdlets de este procedimiento usan una directiva de ubicación definida mediante los siguientes valores. Para obtener una descripción completa de los parámetros de cmdlet y los valores, vea [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).


| **Elemento**                               | **Valor**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **Disclaimer** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | La directiva de compañía le exige que indique una ubicación. Si no define una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia. Especifique una ubicación.  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>Para crear directivas de ubicación

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.

    > [!NOTE]
    > CsLocationPolicy no funcionará correctamente si el valor de **PstnUsage** no está ya presente en la lista global de PstnUsages.

2. También puede ejecutar el cmdlet siguiente para editar la directiva de ubicación global:

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. Ejecute el cmdlet siguiente para crear una directiva de ubicación con etiqueta.

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. Ejecute el cmdlet siguiente para aplicar la directiva de ubicación con etiqueta que se ha creado en el paso 3 en una directiva de usuario.

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
