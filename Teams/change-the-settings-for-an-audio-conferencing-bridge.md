---
title: Cambiar la configuración de un puente de Audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: 'Obtenga los pasos que necesarios para cambiar la configuración de un puente de conferencia que se usa para solicitar los autores de llamadas y recopilar los nombres y los PIN para los organizadores de reuniones cuando no utilizan Skype para las aplicaciones empresariales o Teams de Microsoft. '
ms.openlocfilehash: 21db05e2b4e5ae4688db86af29fbf7c919293e57
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23785705"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de Audioconferencia

Cuando establece una conferencia con Audio en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Estos números de teléfono se utilizan cuando los autores de llamadas llama a una reunión. El número de teléfono se incluye en la parte inferior de la Skype para la invitación a la reunión de negocio o Teams de Microsoft.
  
El puente de conferencia responde a una llamada y solicita el autor de la llamada con mensajes de voz con un automático de reunión attendant y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pida a los autores de llamadas para registrar su nombre y controlar la configuración de PIN. PIN se conceden a los organizadores de reuniones para permitirles para iniciar una reunión cuando están no esté utilizando un Skype para aplicación empresarial o Teams de Microsoft.

  > [!IMPORTANT]
  > Un PIN sólo es necesaria para el organizador de la reunión cuando un Skype para usuario de aplicación empresarial o Teams de Microsoft ya no ha comenzado la reunión. Si todos los usuarios se llaman a la reunión, el PIN se requiere para el organizador de la reunión iniciar la reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso del equipos de Microsoft y Skype para centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **puentes de conferencia**. 

2. En la parte superior de la página de **puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , seleccione: 
  - **Entrada de la reunión y salir de las notificaciones** Si desactiva esta opción, no se le notificará a los usuarios que ya se han unido a la reunión cuando alguien entra o sale de la reunión.
    
    Al activar **las notificaciones de entrada y salida de la reunión**, puede seleccionar estas opciones:
    
  - **Los nombres o números de teléfono** Cuando los usuarios conectan a una reunión, su número de teléfono se reproducirá cuando se unan a él.
    
  - **Tonos** Cuando los usuarios conectan a una reunión, un tono de audio se reproducirá cuando se unan a él.
      
  - **Autores de llamadas ASK para registrar su nombre antes de unirse a la reunión** Si desactiva esta opción, los autores de llamadas no se le pida para registrar su nombre antes de unirse a una reunión.

4. Para establecer la longitud PIN para las reuniones, seleccione el número de dígitos que desee para el PIN en la lista de **longitud PIN** .

5. Para especificar si desea enviar correo electrónico a los usuarios, habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.
    Para obtener más información, vea [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio en los equipos de Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) o [los correos electrónicos enviados a los usuarios al cambia su configuración en Skype para profesionales en línea](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
 
6. Haga clic en **Guardar**. 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png)  Usar el Centro de administración de Skype Empresarial

 **Configurar la experiencia de reunión cuando los autores de llamadas, unirse a una reunión**
    
1. En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo vaya a la **conferencia de Audio** > **configuración de puente de Microsoft**.
    
2. En la página de **configuración de puente de Microsoft** , en la **experiencia de unirse a la reunión**, seleccione:
    
  - **Habilitar la entrada de la reunión y salir de las notificaciones para ser activado** Está seleccionada de manera predeterminada. Si desactiva la casilla de verificación, no se le notificará a los usuarios que ya se han unido a la reunión cuando alguien entra o sale de la reunión.
    
  - Cuando se selecciona **Habilitar la entrada de la reunión y salir de las notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de anuncio de entrada o salida** :
    
   - **Los nombres o números de teléfono** Cuando los usuarios conectan a una reunión, su número de teléfono se reproducirá cuando se unan a él.
    
   - **Tonos** Cuando los usuarios conectan a una reunión, un tono de audio se reproducirá cuando se unan a él.
  
   - **Autores de llamadas ASK para registrar su nombre antes de unirse a la reunión** Está seleccionada de manera predeterminada. Si desactiva la casilla de verificación, los autores de llamadas no se le pida para registrar su nombre antes de unirse a una reunión.
    
3. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
**Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.
    
4. En la página **configuración de puente de Microsoft** , en **seguridad**, escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.
    
    > [!IMPORTANT]
    > The PIN must be between 4 and 12 digits. 
  
**Seleccione si desea enviar correo electrónico a los usuarios**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.
    
4. En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si se cambia su información de marcado**y, a continuación, haga clic en **Guardar**.
    
    Para obtener más información, vea [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio en los equipos de Microsoft](emails-sent-to-users-when-their-settings-change-in-teams.md) o [los correos electrónicos enviados a los usuarios al cambia su configuración en Skype para profesionales en línea](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) .
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Configurar Audioconferencia](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
