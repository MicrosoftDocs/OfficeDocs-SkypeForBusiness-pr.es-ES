---
title: "Activar o desactivar los anuncios de entrada y salida para las reuniones"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# Activar o desactivar los anuncios de entrada y salida para las reuniones

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Cuando configura audioconferencia en Office 365, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que personas utilizarán para llamar a un Skype para empresas o Microsoft Teams reunión.
  
El puente de conferencia responde una llamada para un usuario que está marcando a una reunión mediante un teléfono. El puente de conferencia responde a la llamada con mensajes de voz de un operador automático de conferencia y, a continuación, según su configuración, puede reproducir las notificaciones, pida a las personas que llaman a grabar su nombre y a continuación, configure la seguridad PIN. Un PIN le proporcionará un Skype para empresas o Microsoft Teams organizador de la reunión y, a continuación, les permite iniciar una reunión si no pueden iniciar la reunión mediante un Skype para empresas o Microsoft Teams la aplicación. Sin embargo, puede configurarlo para que no se necesita un PIN para iniciar una reunión.
  
## Configurar las opciones para unirse a una reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En **experiencia de unirse a la reunión**, active o desactive **Habilitar la entrada de la reunión y salir de notificaciones para ser activado**. Esta opción está seleccionada de forma predeterminada. Si se desactiva, los usuarios que ya se han unido a la reunión no recibir una notificación cuando alguien entra o sale de la reunión.
    
5. En **tipo de anuncio de entrada o salida**, seleccione **los nombres o números de teléfono** o **tonos**.
    
6. Active o desactive **las personas que llaman de Ask grabar su nombre antes de unirse a la reunión**.
    
7. Después de realizar los cambios, haga clic en **Guardar**.
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Cuando se trata de Windows PowerShell, Skype Empresarial Online consiste en administración de usuarios y lo que los usuarios se permiten o no hacer. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
  - [¿Por qué necesita usar PowerShell de Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas velocidad, simplificar y productividad sobre usando solo el centro de administración de Office 365 como cuando realice cambios en la configuración de muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los siguientes temas:
    
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

