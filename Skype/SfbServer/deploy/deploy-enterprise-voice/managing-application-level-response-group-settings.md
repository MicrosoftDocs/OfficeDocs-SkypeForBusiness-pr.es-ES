---
title: Administración de la configuración de grupo de respuesta de nivel de la aplicación en Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Administración de la configuración de grupo de respuesta de nivel de la aplicación, como la configuración de música en espera y devolución de llamada, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 41daedd21c5d7ea6f210594c66e3f20906ad90a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892338"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Administración de la configuración de grupo de respuesta de nivel de la aplicación en Skype para la empresa
 
Administración de la configuración de grupo de respuesta de nivel de la aplicación, como la configuración de música en espera y devolución de llamada, en Skype para Business Server Enterprise Voice.
  
Configuración de nivel de la aplicación para la aplicación de grupo de respuesta incluye la configuración de música en espera predeterminada, el archivo de audio de música en espera de forma predeterminada, el período de gracia de devolución de llamada de agente y la configuración del contexto de llamada. Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo. Para ver la configuración de la aplicación, use el cmdlet **Get-CsRgsConfiguration**. Para modificar la configuración de la aplicación, use el cmdlet **Set-CsRgsConfiguration**.
  
La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar la configuración de nivel de la aplicación de grupo de respuesta

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

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
