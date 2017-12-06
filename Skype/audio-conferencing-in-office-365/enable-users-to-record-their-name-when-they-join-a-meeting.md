---
title: "Permitir a los usuarios grabar su nombre al unirse a una reunión"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
description: "Learn how to enable or disable whether your users can record their names when they join a meeting "
---

# Permitir a los usuarios grabar su nombre al unirse a una reunión

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](1d649328-ada7-422d-a074-d6da4da36970.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/1d649328-ada7-422d-a074-d6da4da36970). 
  
Si está configurando audioconferencia en Office 365, recibirás números de teléfono y lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartidas.
  
El puente de conferencia responde una llamada para un usuario que está marcando a una reunión mediante un teléfono. El puente de conferencia responde a la llamada con mensajes de voz de un operador automático y, a continuación, según su configuración, puede reproducir las notificaciones, pida a las personas que llaman a grabar su nombre y a continuación, configure la seguridad PIN para los organizadores de la reunión. PIN reciben a los organizadores de la reunión para que puedan empezar a una reunión. Sin embargo, puede configurarlo para que no se necesita un PIN para iniciar una reunión.
  
## Establecer si los autores de las llamadas tienen que grabar sus nombres

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En **experiencia de unirse a la reunión**, vea la casilla de verificación **Habilitar la entrada de la reunión y salir de notificaciones para ser activado**.
    
  - **Seleccionado** Las personas que llaman se solicitará que graben sus nombres antes de unirse a la reunión. Esta opción está seleccionada de forma predeterminada.
    
  - **Desactivada** Las personas que llaman no pedirá que graben sus nombres antes de unirse a la reunión.
    
5. Después de realizar los cambios, haga clic en **Guardar**.
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios pueden hacer. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
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

