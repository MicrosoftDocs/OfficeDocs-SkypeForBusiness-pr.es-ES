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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 8c2eee6d9a6631fa9ade4e3f1dc4b54b74ea4465
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Activar o desactivar los anuncios de entrada y salida para las reuniones

Cuando establece una conferencia con Audio en Office 365, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que los usuarios utilizarán para llamar a en un Skype para reuniones de negocios o Teams de Microsoft. 
  
El puente de conferencia responde a una llamada de un usuario que se llama a una reunión mediante un teléfono. El puente de conferencia responde el autor de la llamada con mensajes de voz de un operador automático de conferencia y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los autores de llamadas para registrar su nombre y configurar la seguridad de NIP. Un PIN se asignó a un Skype para profesionales o Microsoft Teams organizador de la reunión, y les permite iniciar una reunión si no pueden iniciar la reunión utilizando un Skype para aplicación empresarial o Teams de Microsoft. Sin embargo, se puede establecer para que no es necesario un NIP para iniciar una reunión.
  
## <a name="setting-meeting-join-options"></a>Configurar las opciones para unirse a una reunión

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **Configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Habilitar la entrada de la reunión y salir de notificaciones para activarse**. Esta opción está seleccionada de forma predeterminada. Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entra o sale de la reunión.
    
4. En **tipo de anuncio de entrada o salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
5. Habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.
    
6. Después de realizar los cambios, haga clic en **Aplicar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En la **experiencia de unirse a la reunión**, active o desactive **Habilitar la entrada de la reunión y salir de notificaciones para activarse**. Esta opción está seleccionada de forma predeterminada. Si se desactiva, los usuarios que ya se han unido a la reunión no recibirá una notificación cuando alguien entra o sale de la reunión.
    
3. En **tipo de anuncio de entrada o salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
4. Active o desactive **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**.
    
5. Después de realizar los cambios, haga clic en **Guardar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre solo usa el centro de administración de Office 365, como cuando desea realizar cambios en la configuración de muchos usuarios al mismo tiempo. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
