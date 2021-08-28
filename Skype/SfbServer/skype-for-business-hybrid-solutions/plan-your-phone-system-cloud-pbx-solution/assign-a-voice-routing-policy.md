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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Summary: Read this topic to learn how to assign a voice policy for users using Sistema telefónico with on-premises PSTN connectivity.'
ms.openlocfilehash: a3524c77cf27dc4fd9ab3a4f74211fc9040aad75
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582544"
---
# <a name="assign-a-voice-routing-policy"></a>Asignar una directiva de enrutado de voz
 
> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad RTC entre el entorno local mediante Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).

**Resumen:** Lea este tema para obtener información sobre cómo asignar una directiva de voz para los usuarios que usan Sistema telefónico con conectividad RTC local. 
  
Una vez que un usuario está en Skype Empresarial Online y Sistema telefónico con conectividad RTC local, se aplicarán dos directivas de voz a ellos. Una es una directiva de enrutamiento de voz local que se asignará localmente. Esta directiva puede ser global o específica del usuario y define qué registros de uso de RTC están asociados con el usuario. En este tema se explica cómo asignar esta directiva.
  
La otra directiva de voz define qué características de llamada están disponibles para el usuario; Microsoft define esta directiva de voz y es idéntica para todos los Sistema telefónico con usuarios de conectividad RTC locales. Se asigna automáticamente a Sistema telefónico usuarios.
  
||**Usuario local**|**Sistema telefónico con el usuario de conectividad RTC local**|
|:-----|:-----|:-----|
|Características de llamada definidas en  <br/> |Directiva de voz  <br/> |Directiva de voz predefinida, asignada automáticamente cuando el usuario tiene licencia para Sistema telefónico.  <br/> |
|Registros de uso de RTC asociados con  <br/> |Directiva de voz  <br/> |Directiva de enrutamiento de voz, asignada mientras el usuario aún está interno.  <br/> |
   
Realice los siguientes pasos con la implementación local, mientras que el usuario aún está en la implementación local.
  
## <a name="using-a-global-voice-routing-policy"></a>Uso de una directiva de enrutamiento de voz global

Antes de usar una directiva de enrutamiento de voz global para su Sistema telefónico con usuarios de conectividad RTC locales, debe agregar registros de uso de RTC a la directiva.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Para asignar registros de uso de RTC a la directiva de enrutamiento de voz global

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Agregue los registros de uso de RTC a la directiva:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Por ejemplo:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Creación de una nueva directiva de enrutamiento de voz

### <a name="to-create-a-new-voice-routing-policy"></a>Para crear una nueva directiva de enrutamiento de voz

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Crear una nueva directiva de enrutamiento de voz:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Por ejemplo:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

En este ejemplo se crea una nueva directiva de enrutamiento de voz denominada HybridVoice, que tiene asociados dos usos de RTC.
  
## <a name="assigning-a-voice-routing-policy"></a>Asignar una directiva de enrutamiento de voz

Independientemente de si usa la directiva de enrutamiento de voz global o las específicas del usuario, siga estos pasos para asignar la directiva a un usuario.
  
### <a name="to-assign-the-voice-routing-policy"></a>Para asignar la directiva de enrutamiento de voz

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Asignar una directiva de voz existente a un usuario:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Por ejemplo:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

En este ejemplo, el usuario con el nombre para mostrar Bob Kelly se asigna a la directiva de voz creada anteriormente con el nombre HybridVoice.
  
Para obtener más información acerca de las directivas de enrutamiento de voz, vea Create [or modify a voice policy y configure PSTN usage records in Skype Empresarial 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)y [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
