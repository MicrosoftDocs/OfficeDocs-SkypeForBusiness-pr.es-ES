---
title: Cambiar la configuración de un puente de Audioconferencias.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Cambie la configuración del puente de audioconferencia, incluidas las notificaciones de entrada y salida, reproducir nombres o números de teléfono, tonos y pedir a los autores de llamadas que graben su nombre.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918712"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de Audioconferencias.

Al configurar Audioconferencia en Microsoft 365 u Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o varios números de teléfono. Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión. El número de teléfono se incluye en la parte inferior de la invitación a la reunión de Skype Empresarial o Microsoft Teams.
  
El puente de conferencia responde una llamada y le pide al autor de la llamada avisos de voz con un operador automático de la reunión y, a continuación, según su configuración, puede reproducir notificaciones, pedir a los autores de las llamadas que graben sus nombres y controlar la configuración del PIN. Los NÚMEROS PIN se entregan a los organizadores de la reunión para permitirles iniciar una reunión cuando no estén usando una aplicación de Skype Empresarial o de Microsoft Teams.

  > [!IMPORTANT]
  > Solo es necesario un PIN para el organizador de la reunión cuando un usuario de la aplicación skype empresarial o de Microsoft Teams todavía no ha iniciado la reunión. Si todos los usuarios marcan para un acceso a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya **a puentes de**  >  **conferencias de reuniones.** 

2. En la parte superior de la página **Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el **panel Configuración del** puente, seleccione: 
   - **Notificaciones de entrada y salida de la reunión** Si lo desactiva, los usuarios que ya se han unido a la reunión no serán notificados cuando alguien se una o abandone la reunión.
    
     Al activar las notificaciones **de entrada y salida de una** reunión, puede seleccionar estas opciones:
    
   - **Nombres o números de teléfono** Cuando los usuarios llamen a una reunión, se reproducirá su número de teléfono cuando se unan a esta.
    
   - **Tonos** Cuando los usuarios llamen a una reunión, se reproducirá un tono de audio cuando se unan a ella.
      
   - **Pedir a los autores de la llamada que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a las personas que llamen que registren su nombre antes de unirse a una reunión.

4. Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista de longitud **del PIN.**

5. Para especificar si desea enviar correo electrónico a sus usuarios, habilite o deshabilite el envío automático de correos electrónicos a los usuarios si cambia la configuración **de las audioconferencias.**
    Vea los correos electrónicos enviados automáticamente a los usuarios cuando cambia la configuración de [Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md) en Microsoft Teams o los correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype Empresarial [Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.
 
6. Haga clic en **Guardar**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)
    
- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar Audioconferencia para Skype Empresarial Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
