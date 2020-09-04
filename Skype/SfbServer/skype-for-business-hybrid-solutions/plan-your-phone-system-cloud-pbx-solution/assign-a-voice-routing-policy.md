---
title: Asignar una directiva de enrutado de voz
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Resumen: Lea este tema para obtener información sobre cómo asignar una directiva de voz a los usuarios que usan sistema telefónico con conectividad con RTC local.'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359326"
---
# <a name="assign-a-voice-routing-policy"></a>Asignar una directiva de enrutado de voz
 
> [!Important]
> Skype empresarial online se retirará el 31 de julio de 2021 después del cual el servicio ya no será accesible.  Además, la conectividad con RTC entre su entorno local, ya sea a través de Skype empresarial Server o Cloud Connector Edition y Skype empresarial online, ya no será compatible.  Obtenga información sobre cómo conectar su red de telefonía local a Microsoft Teams con [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz a los usuarios que usan el sistema telefónico con conectividad con RTC local. 
  
Una vez que un usuario se encuentra en Skype empresarial online y usa el sistema telefónico con conectividad con RTC local, se le aplicarán dos directivas de voz. Una es una directiva de enrutamiento de voz local que asignará de forma local. Esta Directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario. En este tema se explica cómo asignar esta Directiva.
  
La otra directiva de voz define qué características de llamada están disponibles para el usuario; esta directiva de voz está definida por Microsoft y es idéntica para todos los sistemas telefónicos con los usuarios de conectividad RTC local. Se asigna automáticamente a los usuarios del sistema telefónico.
  
||**Usuario local**|**Sistema telefónico con usuario de conectividad con RTC local**|
|:-----|:-----|:-----|
|Llamar a características definidas en  <br/> |Directiva de voz  <br/> |Directiva de voz predefinida, asignada automáticamente cuando el usuario tiene una licencia de sistema telefónico.  <br/> |
|Registros de uso de RTC asociados con  <br/> |Directiva de voz  <br/> |Directiva de enrutamiento de voz, asignada mientras el usuario sigue hospedado de forma local.  <br/> |
   
Los pasos siguientes se realizan mediante la implementación local, mientras que el usuario sigue hospedado en la implementación local.
  
## <a name="using-a-global-voice-routing-policy"></a>Uso de una directiva de enrutamiento de voz global

Antes de usar una directiva de enrutamiento de voz global para el sistema telefónico con los usuarios de conectividad RTC local, debe agregar los registros de uso de RTC a la Directiva.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para asignar registros de uso de RTC a la Directiva de enrutamiento de voz global

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
3. Agregue los registros de uso de RTC a la Directiva:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Por ejemplo:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Creación de una nueva Directiva de enrutamiento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Para crear una nueva Directiva de enrutamiento de voz

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
3. Cree una nueva Directiva de enrutamiento de voz:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Por ejemplo:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

En este ejemplo, se crea una nueva Directiva de enrutamiento de voz denominada HybridVoice, que tiene asociados dos usos de RTC.
  
## <a name="assigning-a-voice-routing-policy"></a>Asignar una directiva de enrutamiento de voz

Independientemente de si usa la Directiva de enrutamiento de voz global o las específicas del usuario, use los pasos siguientes para asignar la Directiva a un usuario.
  
### <a name="to-assign-the-voice-routing-policy"></a>Para asignar la Directiva de enrutamiento de voz

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial 2015**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
3. Asignar una directiva de voz existente a un usuario:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna a la Directiva de voz creada anteriormente con el nombre HybridVoice.
  
Para obtener más información acerca de las directivas de enrutamiento de voz, consulte [crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype empresarial 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

