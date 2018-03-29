---
title: Crear directivas de ubicación en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Leer este tema para aprender a configurar mejorado las políticas de ubicación de servicio de emergencia (E9-1-1) en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a>Crear directivas de ubicación en Skype Empresarial Server 2015
 
Leer este tema para aprender a configurar mejorado las políticas de ubicación de servicio de emergencia (E9-1-1) en Skype para Telefonía IP empresarial de Business Server. 
  
Skype para Business Server utiliza una directiva de ubicación para habilitar Skype para clientes de negocios para E9-1-1 durante el registro del cliente. Una directiva de ubicación contiene la configuración que define cómo se implementará E9-1-1. Para obtener más información, vea [Planear las políticas de ubicación de Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).
  
Definir políticas de ubicación utilizando el Skype para el Panel de Control del negocio o mediante el cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .
  
> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencia para un cliente. Si desea configurar varios números de emergencia, debe seguir la información en el [Plan para varios números de emergencia en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) y [configurar varios números de emergencia en Skype para negocios 2015](configure-multiple-emergency-numbers.md). 
  
La directiva de ubicación global puede editarse y crear otras directivas de ubicación con etiqueta. Un cliente obtiene una directiva global si no se ubica en una subred que tenga asociada una directiva de ubicación o, bien, si el cliente no tiene asignada directamente una directiva de ubicación. Las directivas con etiquetas se asignan a subredes o usuarios.   
  
Para crear una directiva de ubicación, debe usar una cuenta que pertenezca al grupo RTCUniversalServerAdmins, o bien que tenga el rol administrativo CsVoiceAdministrator o derechos y permisos de administrador equivalentes.
  
Para obtener más información, vea [Planear las políticas de ubicación de Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md). Los cmdlets de este procedimiento usan una directiva de ubicación definida mediante los siguientes valores. Para obtener una descripción completa de los valores y parámetros de cmdlet, vea [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).
  
|**Elemento**|**Valor**|
|:-----|:-----|
|EnhancedEmergencyServicesEnabled  <br/> |**True** <br/> |
|LocationRequired  <br/> |**Disclaimer** <br/> |
|EnhancedEmergencyServiceDisclaimer  <br/> |La directiva de compañía le exige que indique una ubicación. Si no define una ubicación, los servicios de emergencia no podrán localizarle en caso de emergencia. Especifique una ubicación.  <br/> |
|UseLocationForE911Only  <br/> |**False** <br/> |
|PstnUsage  <br/> |**EmergencyUsage** <br/> |
|EmergencyDialString  <br/> |**911** <br/> |
|EmergencyDialMask  <br/> |**112** <br/> |
|NotificationUri  <br/> |**SIP:Security@litwareinc.com** <br/> |
|ConferenceUri  <br/> |**SIP:+14255550123@litwareinc.com** <br/> |
|ConferenceMode  <br/> |**twoway** <br/> |
|LocationRefreshInterval  <br/> |**2** <br/> |
   
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


