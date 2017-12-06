---
title: "Cambiar la configuración de un puente de conferencia de Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
description: "Get the steps you need to change settings for a Microsoft dial-in conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business clients. "
---

# Cambiar la configuración de un puente de conferencia de Audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](783fad3f-b77c-422b-b91f-7c8b0af324fb.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/783fad3f-b77c-422b-b91f-7c8b0af324fb). 
  
Si está configurando audioconferencia en Office 365, recibirás números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Los números de teléfono se usan cuando las personas que llaman llaman a una reunión. El número de teléfono se incluye en la parte inferior de la Skype Empresarial o Teams Microsoft invitación de reunión.
  
El puente de conferencia responde una llamada y solicita al llamador con mensajes de voz mediante un automática de reunión operador y, a continuación, según su configuración, puede reproducir las notificaciones, pida a las personas que llaman grabar su nombre y controlar la configuración de PIN. PIN se conceden a los organizadores de la reunión para permitirles para iniciar una reunión cuando están no está usando un Skype Empresarial o una aplicación Teams de Microsoft.
  
> [!IMPORTANT]
> Un PIN solo es necesario para el organizador de la reunión cuando un usuario de aplicación de Microsoft Teams o Skype Empresarial ya no ha iniciado la reunión. Si todos los usuarios se llaman a la reunión, el PIN se requiere para el organizador de la reunión iniciar la reunión. 
  
## Cambiar la configuración de un puente de conferencia de audio

 **Configurar la experiencia de reunión cuando las personas que llaman unirse a una reunión**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En la página **Configuración del puente de Microsoft**, en la **experiencia de unirse a la reunión**, seleccione:
    
  - **Habilitar la entrada de la reunión y salir de notificaciones para ser activado** Esta opción está seleccionada de forma predeterminada. Si desactiva la casilla de verificación, los usuarios que ya se han unido a la reunión no recibir una notificación cuando alguien entra o sale de la reunión.
    
    Cuando seleccione **Habilitar la entrada de la reunión y salir de notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio**:
    
  - **Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, su número de teléfono se reproducirá cuando se unan a ella.
    
  - **Tonos** Cuando los usuarios llaman a una reunión, un tono de audio se reproducirá cuando se unan a ella.
    
    > [!NOTE]
    > **Tono** está ahora disponible como tipo de anuncio para todos los clientes como una característica de vista previa.
  
  - **Personas que llaman de ASK grabar su nombre antes de unirse a la reunión** Esta opción está seleccionada de forma predeterminada. Si desactiva la casilla de verificación, las personas que llaman no pedirá que graben sus nombres antes de unirse a una reunión.
    
5. Después de realizar los cambios, haga clic en **Guardar**.
    
 **Establecer la longitud del PIN para las reuniones**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En la página **Configuración del puente de Microsoft**, en **seguridad**, escriba el número de dígitos que desee para el PIN en la lista de **longitud del PIN** y, a continuación, haga clic en **Guardar**.
    
    > [!IMPORTANT]
    > El PIN debe estar entre 4 y 12 dígitos. 
  
 **Seleccione si desea enviar correo electrónico a los usuarios**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En la página **Configuración del puente de Microsoft**, seleccione o desactive **Enviar automáticamente los mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio** y, a continuación, haga clic en **Guardar**.
    
    Para obtener más información, consulte [Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md) .
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no hacer. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
  - [¿Por qué necesita usar PowerShell de Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas velocidad, simplificar y productividad sobre usando solo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los siguientes temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Conferencias de acceso telefónico en Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

