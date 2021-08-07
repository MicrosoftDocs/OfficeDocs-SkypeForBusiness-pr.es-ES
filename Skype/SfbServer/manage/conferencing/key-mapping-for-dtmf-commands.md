---
title: Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Summary: Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype Empresarial Server.'
ms.openlocfilehash: 106cd301826792ec494df4d490a6b953baf3badd1740d9cfd2de12e6de966d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276855"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar la asignación de teclas de comandos de tono dual multifrecuencia (DTMF) en Skype Empresarial Server.
  
Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) mediante el teclado de su teléfono. 
  
Para administrar las claves usadas para los comandos DTMF, use el Shell de administración de Skype Empresarial Server con los **cmdlets Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration** y **New-CsDialinConferencingDtmfConfiguration.**
  
Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Administrar la asignación de claves de comandos DTMF

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Para ver la configuración dtmf usada para conferencias de acceso telefónico local, ejecute el siguiente comando en el símbolo del sistema :
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Para modificar la configuración dtmf usada para las conferencias de acceso telefónico local, ejecute el siguiente cmdlet y especifique la tecla que se va a presionar para cada opción que desee cambiar:
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio.
    
En el siguiente ejemplo se intercambia la tecla que se presiona para habilitar o deshabilitar anuncios y la tecla que se presiona para silenciar y desactivar todos los participantes. Dado que no se especifica ninguna identidad, estos cambios se aplican a la configuración global de DTMF:
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Para obtener más información, vea [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)y [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
