---
title: Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Resumen: Conozca cómo administrar la asignación de teclas de comandos de multifrecuencia de tono dual (DTMF) en Skype para Business Server 2015.'
ms.openlocfilehash: 0dca7143b59b7cf4ded0302f763053e71be3bb2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server-2015"></a>Administrar la asignación de teclas para comandos DTMF en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar la asignación de teclas de comandos de multifrecuencia de tono dual (DTMF) en Skype para Business Server 2015.
  
Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas en el teclado numérico del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico local a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) con el teclado numérico de su teléfono. 
  
Para administrar las claves utilizadas para los comandos DTMF, use el Skype para el Shell de administración de servidor empresariales con **Get-CsDialinConferencingDtmfConfiguration**, **Conjunto de CsDialinConferencingDtmfConfiguration**y ** CsDialinConferencingDtmfConfiguration nuevo** cmdlets.
  
Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Administrar la asignación de teclas de comandos DTMF

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol Cs-ServerAdministrator o CsAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para ver la configuración de DTMF usada para conferencias de acceso telefónico local, ejecute el siguiente comando en el símbolo del sistema:
    
  ```
  Get-CsDialinConferencingDtmfConfiguration
  ```

4. Para modificar la configuración de DTMF usada para conferencias de acceso telefónico local, ejecute el cmdlet siguiente y especifique la tecla que se necesita presionar para cada una de las opciones que desea cambiar:
    
  ```
  Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
[-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
[-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
[-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
[-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
  ```

5. (Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio.
    
En este ejemplo se cambia la tecla que se presiona para habilitar o deshabilitar anuncios y la tecla que se presiona para activar o desactivar el audio de todos los participantes. Como no se ha especificado el parámetro Identity, estos cambios se aplican a la configuración de DTMF global:
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Para obtener más información, consulte [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Conjunto de CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)y [CsDialInConferencingDtmfConfiguration de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

