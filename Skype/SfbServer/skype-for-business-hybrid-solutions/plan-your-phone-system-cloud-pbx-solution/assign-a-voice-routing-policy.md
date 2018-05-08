---
title: Asignar una directiva de enrutamiento de voz
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumen: Lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan el sistema telefónico en Office 365 con conectividad de RTC local.'
ms.openlocfilehash: fc11fabeb7f6a8bacc0f3a6dd48d6ed24edd3403
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="assign-a-voice-routing-policy"></a>Asignar una directiva de enrutamiento de voz
 
**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan el sistema telefónico en Office 365 con conectividad de RTC local.
  
Una vez que un usuario esté en Skype para profesionales en línea y usar el sistema telefónico en Office 365 con conectividad de RTC local, dos directivas de voz se aplicarán a ellos. Uno es una directiva de enrutamiento de voz local que se va a asignar en local. Esta directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario. En este tema se explica cómo asignar esta directiva.
  
La otra directiva de voz define qué características de llamada están disponibles para el usuario; Esta directiva de voz está definida por Microsoft y es idéntica para todos los sistema telefónico en Office 365 con usuarios de conectividad RTC local. Se asigna automáticamente al sistema de teléfono en los usuarios de Office 365.
  
||**Usuario local**|**Sistema telefónico en Office 365 con el usuario de conectividad RTC local**|
|:-----|:-----|:-----|
|Características de llamadas definidas en  <br/> |Directiva de voz  <br/> |Definido previa a la directiva de voz, asignada automáticamente cuando el usuario tiene licencia para el sistema telefónico en Office 365.  <br/> |
|Registros de uso de RTC asociados con  <br/> |Directiva de voz  <br/> |Directiva de enrutamiento de voz, asignada cuando el usuario aún está hospedado de forma local.  <br/> |
   
Realice los pasos siguientes con la implementación local, mientras que el usuario aún está hospedado en la implementación local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usar una directiva de enrutamiento de voz global

Antes de utilizar una directiva de enrutamiento de voz global para el sistema telefónico en Office 365 con los usuarios de conectividad de RTC local, debe agregar registros de uso de RTC a la directiva.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para asignar registros de uso de RTC a la directiva de enrutamiento de voz global

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Agregar los registros de uso de RTC a la directiva:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 

  ```

    Por ejemplo:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 

  ```

## <a name="creating-a-new-voice-routing-policy"></a>Crear una directiva de enrutamiento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Para crear una directiva de enrutamiento de voz

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Crea una directiva de enrutamiento de voz:
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    Por ejemplo:
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

En este ejemplo se crea una directiva de enrutamiento de voz llamada HybridVoice, que tiene asociados dos usos de RTC.
  
## <a name="assigning-a-voice-routing-policy"></a>Asignar una directiva de enrutamiento de voz

Siga estos pasos para asignar la directiva a un usuario, independientemente de si usa la directiva de enrutamiento de voz global o directivas específicas de usuario.
  
### <a name="to-assign-the-voice-routing-policy"></a>Para asignar la directiva de enrutamiento de voz

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Asignar una directiva de voz existente a un usuario:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    Por ejemplo:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

En este ejemplo, se asigna el usuario con el nombre para mostrar Guillermo Rodarte a la directiva de voz creada anteriormente con el nombre HybridVoice.
  
Para obtener más información acerca de las directivas de enrutamiento de voz, vea [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para profesionales de 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

