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
f1.keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Siga los pasos que necesita para cambiar la configuración de un puente de conferencia que se usa para avisar a las personas que llaman y recopilar nombres y PIN de los organizadores de reuniones cuando no usan las aplicaciones de Skype empresarial o Microsoft Teams. '
ms.openlocfilehash: 0e5a93ec86ac0582fcfd35435bce47e746a35f44
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695505"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de Audioconferencias.

Al configurar las conferencias de audio en Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o más números de teléfono. Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión. El número de teléfono se incluye en la parte inferior de la invitación a una reunión de Skype empresarial o de Microsoft Teams.
  
El puente de conferencia responde a una llamada y le pide a la persona que llama con un operador automático de la reunión y, a continuación, en función de la configuración, puede reproducir notificaciones, pedir a los participantes que graben su nombre y controlar la configuración del PIN. Los PIN se otorgan a los organizadores de reuniones para que puedan iniciar una reunión cuando no estén usando una aplicación de Skype empresarial o Microsoft Teams.

  > [!IMPORTANT]
  > Un PIN solo es necesario para el organizador de la reunión cuando un usuario de la aplicación de Skype empresarial o de Microsoft Teams ya no ha iniciado la reunión. Si todos los usuarios llaman a la reunión, el PIN es necesario para que el organizador de la reunión la inicie. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a**puentes de conferencia**de **reuniones** > . 

2. En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**. 

3. En el panel **configuración de puente** , seleccione: 
   - **Notificaciones de entrada y salida de reunión** Si desactiva esta opción, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre o salga de la reunión.
    
     Al activar las **notificaciones de entrada y salida**de la reunión, puede seleccionar estas opciones:
    
   - **Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, su número de teléfono se reproducirá cuando se una a una.
    
   - **Tonos** Cuando los usuarios llaman a una reunión, se reproduce un tono de audio al unirse a la misma.
      
   - **Pedir a las personas que llamen para que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a las personas que llamen su nombre antes de unirse a una reunión.

4. Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista **longitud del PIN** .

5. Para especificar si se debe enviar correo electrónico a los usuarios, habilitar o deshabilitar el **envío automático de correos electrónicos a los usuarios si cambia la configuración**de las conferencias de audio.
    Ver [los correos electrónicos enviados de forma automática a los usuarios cuando cambia la configuración de la audioconferencia en Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o [correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.
 
6. Haga clic en **Guardar **. 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![Un icono que muestra el logotipo de Skype empresarial](media/sfb-logo-30x30.png)  Using the Skype for Business admin center

 **Configurar la experiencia de reunión cuando las personas que llaman se unen a una reunión**
    
1. En el **centro de administración de Skype empresarial**, en el navegación de la izquierda, **vaya a** > **configuración de puente de Microsoft**.
    
2. En la página **configuración del puente de Microsoft** , en experiencia de unirse a la **reunión**, seleccione:
    
   - **Habilitar las notificaciones de entrada y salida de reunión para que se activen** Esta opción está seleccionada de forma predeterminada. Si desactiva la casilla, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre o salga de la reunión.
    
   - Si selecciona **permitir que las notificaciones de entrada y salida de la reunión estén activadas**, puede seleccionar estas opciones en la lista de **tipo de anuncio de entrada/salida** :
    
   - **Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, su número de teléfono se reproducirá cuando se una a una.
    
   - **Tonos** Cuando los usuarios llaman a una reunión, se reproduce un tono de audio al unirse a la misma.
  
   - **Pedir a las personas que llamen para que graben su nombre antes de unirse a la reunión** Esta opción está seleccionada de forma predeterminada. Si desactiva la casilla, no se pedirá a las personas que llamen su nombre antes de unirse a una reunión.
    
3. Después de realizar los cambios, haga clic en **Guardar**.
    
Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro** > de administración de Microsoft 365**Skype empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. En la **página Configuración del puente de Microsoft** , en **seguridad**, escriba la cantidad de dígitos que desee para el PIN en la lista **longitud del PIN** y, a continuación, haga clic en **Guardar**.
    
    > [!IMPORTANT]
    > The PIN must be between 4 and 12 digits. 
  
**Seleccione si desea enviar correo electrónico a los usuarios**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro** > de administración de Microsoft 365**Skype empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. En la página **configuración del puente de Microsoft** , Active o desactive **enviar automáticamente correos electrónicos a los usuarios si cambia la información de acceso telefónico**y, a continuación, haga clic en **Guardar**.
    
    Ver [los correos electrónicos enviados de forma automática a los usuarios cuando cambia la configuración de la audioconferencia en Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o [correos electrónicos enviados a los usuarios cuando cambia su configuración en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obtener más información.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar audioconferencias para Skype empresarial online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
