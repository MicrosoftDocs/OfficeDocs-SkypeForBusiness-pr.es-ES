---
title: Asignar una directiva de enrutamiento de voz
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumen: Leer este tema para obtener información sobre cómo asignar una directiva de voz para usuarios que utilizan el sistema de teléfono en Office 365 con conectividad de RTC local.'
ms.openlocfilehash: bcc4102157a3689208c45d7430a7954ce9a1e3f9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-voice-routing-policy"></a>Asignar una directiva de enrutamiento de voz
 
**Resumen:** Lea este tema para aprender a asignar una directiva de voz para usuarios que utilizan el sistema de teléfono en Office 365 con conectividad de RTC local.
  
Una vez que un usuario está en Skype para los negocios en línea y utilizar el sistema telefónico en Office 365 con conectividad de RTC local, se les aplicará dos directivas de voz. Uno es una directiva de enrutamiento de voz locales que asignará en locales. Esta directiva puede ser global o específica del usuario y define qué registros de uso PSTN están asociados con el usuario. En este tema se explica cómo asignar esta directiva.
  
La otra directiva de voz define qué características de llamada están disponibles para el usuario; Esta directiva de voz está definida por Microsoft y es idéntica para todo el sistema de teléfono en Office 365 con usuarios de conectividad PSTN locales. Se asigna automáticamente al sistema de teléfono de los usuarios de Office 365.
  
||**Usuario local**|**Sistema de teléfono en Office 365 con usuario de conectividad RTC local**|
|:-----|:-----|:-----|
|Características de llamadas definidas en  <br/> |Directiva de voz  <br/> |Predefinidos directiva de voz, asignada de forma automática cuando el usuario tiene licencia para su sistema telefónico en Office 365.  <br/> |
|Registros de uso de RTC asociados con  <br/> |Directiva de voz  <br/> |Directiva de enrutamiento de voz, asignada cuando el usuario aún está hospedado de forma local.  <br/> |
   
Realice los pasos siguientes con la implementación local, mientras el usuario todavía está alojado en la implementación local.
  
## <a name="using-a-global-voice-routing-policy"></a>Usar una directiva de enrutamiento de voz global

Antes de utilizar una directiva de enrutamiento de voz global para su sistema telefónico en Office 365 con usuarios de conectividad RTC local, debe agregar registros de uso PSTN a la directiva.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para asignar registros de uso de RTC a la directiva de enrutamiento de voz global

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Agregue los registros de uso PSTN a la directiva:
    
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
  
Para obtener más detalles acerca de las directivas de enrutamiento de voz, consulte [crear o modificar una directiva de voz y configurar registros de uso PSTN en Skype para negocios 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [CsVoiceRoutingPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [CsVoicePolicy de la concesión](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

