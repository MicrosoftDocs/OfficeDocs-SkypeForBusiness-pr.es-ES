---
title: Administración de la configuración del grupo de respuesta a nivel de aplicación en Skype Empresarial
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Administrar la configuración del grupo de respuesta a nivel de aplicación, como la música en espera y la configuración de llamada, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 05ff86de40efe4d75b9d7fcb54b50615ae7245a8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394312"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Administración de la configuración del grupo de respuesta a nivel de aplicación en Skype Empresarial
 
Administrar la configuración del grupo de respuesta a nivel de aplicación, como la música en espera y la configuración de llamada, en Skype Empresarial Server Telefonía IP empresarial.
  
La configuración de nivel de aplicación para la aplicación de grupo de respuesta incluye la configuración predeterminada de música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de llamada del agente y la configuración del contexto de llamada. Solo puede definir un conjunto de opciones de configuración de nivel de aplicación por grupo. Para ver la configuración de nivel de aplicación, use el cmdlet **Get-CsRgsConfiguration**. Para modificar la configuración de nivel de aplicación, use el cmdlet **Set-CsRgsConfiguration**.
  
La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar la configuración de nivel de aplicación del grupo de respuesta

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
2. Inicie el Shell Skype Empresarial Server administración: haga clic en **Inicio, todos** los **programas,** **Skype Empresarial 2015** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
3. En la línea de comandos, ejecute:
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Por ejemplo:
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Para especificar un archivo de audio para usar como música en espera predeterminada, debe importar primero el archivo de audio. Por ejemplo:
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Vea también

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)