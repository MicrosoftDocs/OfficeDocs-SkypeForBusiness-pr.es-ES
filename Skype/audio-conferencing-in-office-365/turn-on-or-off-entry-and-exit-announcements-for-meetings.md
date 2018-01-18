---
title: Activar o desactivar los avisos de entrada y salida para las reuniones
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Obtenga información sobre cómo activar la entrada y salida anuncios o desactivar un Skype para reuniones de negocios en línea usando el Skype para el centro de administración de negocios. "
ms.openlocfilehash: 2298450d28ebb09acb87820b1f8a01cb9196708e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Activar o desactivar los avisos de entrada y salida para las reuniones

Cuando configura la audioconferencia en Office 365, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que utilizarán las personas que llaman a un Skype para reuniones de negocios o Teams de Microsoft. 
  
El puente de conferencia responde a una llamada de un usuario que está marcando a una reunión mediante un teléfono. El puente de conferencia responde al llamador con indicaciones de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los llamadores para registrar su nombre y configurar la seguridad de NIP. Un PIN se asigna a un Skype para el organizador de la reunión de negocios o Teams de Microsoft, y les permite iniciar una reunión si no pueden comenzar la reunión mediante un Skype para la aplicación de negocios o Teams de Microsoft. Sin embargo, se puede establecer para que no sea necesario un PIN para iniciar una reunión.
  
## <a name="setting-meeting-join-options"></a>Configuración de opciones de combinación de reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En **experimentar la combinación de la reunión**, active o desactive **Permitir la entrada de la reunión y salir notificaciones al activarse**. Esto está seleccionada por defecto. Si lo desactiva, los usuarios que ya han participado en la reunión no le notificará cuando alguien entra o sale de la reunión.
    
5. En **tipo de anuncio de entrada/salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
6. Active o desactive **los llamadores Ask para registrar su nombre antes de unirse a la reunión**.
    
7. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar esta tarea, puede utilizar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Preguntas frecuentes de audio conferencia](audio-conferencing-common-questions.md)

