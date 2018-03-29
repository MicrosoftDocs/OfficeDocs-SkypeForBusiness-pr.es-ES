---
title: Administrar la configuración del grupo de respuesta de la aplicación en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Administrar la configuración de grupo de respuesta de nivel de aplicación, como música en espera y timbre, en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: c202ce60f23594389c7f49f0108f7d03cb1deef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business-2015"></a>Administrar la configuración del grupo de respuesta de la aplicación en Skype Empresarial 2015
 
Administrar la configuración de grupo de respuesta de nivel de aplicación, como música en espera y timbre, en Skype para Telefonía IP empresarial de Business Server.
  
Configuración de nivel de aplicación para la aplicación de grupo de respuesta incluye la configuración de música en espera de forma predeterminada, el archivo de audio de música en espera de forma predeterminada, el período de gracia de timbre de agente y la configuración del contexto de llamada. Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo. Para ver la configuración de nivel de aplicación, use el cmdlet **Get-CsRgsConfiguration** . Para modificar la configuración de nivel de aplicación, use el cmdlet **Set-CsRgsConfiguration** .
  
La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar la configuración de nivel de aplicación de grupo de respuesta

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. En la línea de comandos, ejecute:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    Por ejemplo:
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    Para especificar un archivo de audio para usar como música en espera predeterminada, debe importar primero el archivo de audio. Por ejemplo:
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>Vea también

#### 

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Conjunto de CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[CsRgsAudioFile de importación](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)

