---
title: Activar o desactivar los anuncios de entrada y salida para las reuniones
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: a9c3788db6b5742b4f2b41961c3843b4939c315b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Activar o desactivar los anuncios de entrada y salida para las reuniones

Cuando configura la audioconferencia en Office 365, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que utilizarán las personas que llaman a un Skype para reuniones de negocios o Teams de Microsoft. 
  
El puente de conferencia responde a una llamada de un usuario que está marcando a una reunión mediante un teléfono. El puente de conferencia responde al llamador con indicaciones de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los llamadores para registrar su nombre y configurar la seguridad de NIP. Un PIN se asigna a un Skype para el organizador de la reunión de negocios o Teams de Microsoft, y les permite iniciar una reunión si no pueden comenzar la reunión mediante un Skype para la aplicación de negocios o Teams de Microsoft. Sin embargo, se puede establecer para que no sea necesario un PIN para iniciar una reunión.
  
## <a name="setting-meeting-join-options"></a>Configurar las opciones para unirse a una reunión

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**

1. En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Habilitar la entrada de la reunión y salir de notificaciones para activarse**. Esta opción está seleccionada de forma predeterminada. Si lo desactiva, los usuarios que ya han participado en la reunión no le notificará cuando alguien entra o sale de la reunión.
    
4. En **tipo de anuncio de entrada/salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
5. Habilitar o deshabilitar **los llamadores Ask para registrar su nombre antes de unirse a la reunión**.
    
6. Después de realizar los cambios, haga clic en **Aplicar**.

Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En **experimentar la combinación de la reunión**, active o desactive **Permitir la entrada de la reunión y salir notificaciones al activarse**. Esta opción está seleccionada de forma predeterminada. Si lo desactiva, los usuarios que ya han participado en la reunión no le notificará cuando alguien entra o sale de la reunión.
    
3. En **tipo de anuncio de entrada/salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
4. Active o desactive **los llamadores Ask para registrar su nombre antes de unirse a la reunión**.
    
5. Después de realizar los cambios, haga clic en **Guardar**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
