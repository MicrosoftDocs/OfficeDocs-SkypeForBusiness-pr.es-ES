---
title: Administración de la configuración de grupo de respuesta de nivel de aplicación en Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Administración de la configuración de grupo de respuesta de nivel de aplicación, como la configuración de música en espera y timbre, en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 99a3d6bc82cffd39608d2da0be013d4fbb8389e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767113"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>Administración de la configuración de grupo de respuesta de nivel de aplicación en Skype empresarial
 
Administración de la configuración de grupo de respuesta de nivel de aplicación, como la configuración de música en espera y timbre, en Skype empresarial Server Enterprise Voice.
  
La configuración de nivel de aplicación para la aplicación de grupo de respuesta incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia de timbre de agente y la configuración de contexto de llamada. Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo. Para ver la configuración de la aplicación, use el cmdlet **Get-CsRgsConfiguration**. Para modificar la configuración de la aplicación, use el cmdlet **Set-CsRgsConfiguration**.
  
La música en espera predeterminada se reproduce cuando se pone una llamada en espera solo si no se definió ninguna música en espera personalizada. El contexto de llamada está disponible solo para las colas asignadas a flujos de trabajo interactivos. Si se habilitó el contexto de llamada, un agente puede ver información como tiempo de espera del autor de la llamada, o preguntas y respuestas del flujo de trabajo, cuando se recibe la llamada.
  
### <a name="to-modify-response-group-application-level-settings"></a>Para modificar la configuración del nivel de aplicación de un grupo de respuesta

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
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

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Importar-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
