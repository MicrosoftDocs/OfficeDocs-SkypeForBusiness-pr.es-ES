---
title: "Iniciar una conferencia de Audio por teléfono sin un PIN"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# Iniciar una conferencia de Audio por teléfono sin un PIN

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Puede ser frustrante para los usuarios que llaman a una reunión para guardarlo en la sala de espera de la reunión escuchar música porque la Skype para empresas o Microsoft Teams organizador de la reunión no ha iniciado la reunión.
  
Si el organizador de la reunión se comunica con la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Puede configurarlo para que todos los usuarios pueden llamar a una reunión y no se le pida un PIN iniciar la reunión. Puede usar la Skype centro de administración de la empresa para habilitar o deshabilitar a esta configuración para un único usuario.
  
Un PIN no es necesario para el organizador de la reunión si alguien ha empezado a la reunión desde un Skype para empresas o Microsoft Teams la aplicación. Un PIN solo es necesario cuando el organizador de la reunión unan a la reunión a través de un teléfono. El PIN para las reuniones se envía al usuario audio cuando se asigna la licencia de **Conferencias de Audio** y están habilitados para conferencias de Audio. Ver[Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)y [Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) .
  
## Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **usuarios**.
    
4. En la lista, seleccione el usuario y en el panel Acción, haga clic en **Editar**.
    
5. En la página de propiedades del usuario, en **Opciones de reunión**, active o desactive **no autenticado de permitir que las personas que llaman para ser los primeros en una reunión. Si no, a continuación, esperará en la sala de espera hasta que se unan a un usuario autenticado**.
    
6. Haga clic en **Guardar**.
    
 **Para habilitar o deshabilitar a las personas que llaman anónimas a todas las reuniones del usuario con Windows Powershell**
  
- Ejecute lo siguiente: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## ¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de conferencia de Audio para un usuario](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Si está habilitado el acceso anónimo, o no requieren un PIN iniciar una reunión:
    
  - Si no se ha iniciado la reunión (hay nadie de la reunión todavía): una llamada le preguntará si es el organizador; Si dice que sí, le preguntará para su PIN y después de que escribe el PIN, comenzará la reunión y el usuario se une a una reunión.
    
  - Si la reunión ya ha iniciado (otra persona ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la reunión y unirá a la persona que llama.
    
- Si se deshabilita el acceso anónimo o no requieren un PIN iniciar una reunión:
    
  - Si no se ha iniciado la reunión (hay nadie de la reunión todavía): no se solicita un llamador si es el organizador y nunca se pedirá el PIN. Dado que la configuración del organizador se establece en desactivado, comenzará la reunión y las personas que llaman anónimas se une a una reunión.
    
  - Si la reunión ya ha iniciado (otra persona ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la reunión y unirá a la persona que llama.
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para varios usuarios, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Cuando se trata de Windows PowerShell, Skype Empresarial Online consiste en administración de usuarios y lo que los usuarios se permiten o no hacer. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas a realizar. Para empezar con Windows PowerShell, consulte estos temas:
    
  - [¿Por qué necesita usar PowerShell de Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas velocidad, simplificar y productividad sobre usando solo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los siguientes temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

