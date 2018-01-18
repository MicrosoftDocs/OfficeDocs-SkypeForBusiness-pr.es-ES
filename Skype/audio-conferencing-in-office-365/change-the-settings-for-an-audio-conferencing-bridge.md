---
title: "Cambiar la configuración de un puente de conferencia de Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "Obtenga los pasos que necesarios para cambiar la configuración de un puente de acceso telefónico de la conferencia de Microsoft que se utiliza para solicitar a los llamadores y recopilar nombres y clavijas para los organizadores de la reunión cuando no utilizan Skype para clientes empresariales. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de conferencia de Audio

Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Estos números de teléfono se utilizan cuando los llamadores llama a una reunión. El número de teléfono se incluye en la parte inferior de la Skype para invitar a la reunión de negocios o Teams de Microsoft.
  
El puente de conferencia contesta una llamada y solicita al llamador con indicaciones de voz utilizando un auto reunión operador y a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pregunte a los llamadores para registrar su nombre y controlar la configuración de pines. Pines se otorgan a los organizadores de reuniones para permitirles iniciar una reunión cuando están no esté utilizando un Skype para la aplicación de negocios o Teams de Microsoft.

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de conferencia de audio

 **Configurar la experiencia de reunión cuando los llamadores unirse a una reunión**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En la página **configuración de puente de Microsoft** , en la **experiencia de unión de la reunión**, seleccione:
    
  - **Habilitar la entrada de la reunión y salir de notificaciones para activarse** Esto está seleccionada por defecto. Si desactiva la casilla de verificación, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.
    
    Cuando selecciona **Habilitar la entrada de la reunión y salir notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio** :
    
  - **Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.
    
  - **Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.
    
    > [!NOTE]
    > Con **tono** como el tipo de anuncio está disponible actualmente para todos los clientes como una característica de vista previa.
  
  - **Llamadores ASK para registrar su nombre antes de unirse a la reunión** Esto está seleccionada por defecto. Si desactiva la casilla de verificación, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.
    
5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Configurar la longitud del PIN de las reuniones
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En la página de **configuración de puente de Microsoft** en **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.
    
    > [!IMPORTANT]
    > El NIP debe tener entre 4 y 12 dígitos. 
  
**Seleccione si desea enviar correo electrónico a los usuarios**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**y, a continuación, haga clic en **Guardar**.
    
    Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede utilizar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar a utilizar Windows PowerShell, consulte estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)

