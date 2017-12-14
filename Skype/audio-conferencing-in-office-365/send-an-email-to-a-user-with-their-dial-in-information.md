---
title: "Enviar un correo electrónico a un usuario con su información de conferencias de Audio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Enviar un correo electrónico a un usuario con su información de conferencias de Audio

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](7440d3e2-1b49-4258-bd2c-79e9072f8c8d.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/7440d3e2-1b49-4258-bd2c-79e9072f8c8d). 
  
A veces Skype para empresas o Microsoft Teams usuarios deba enviarles su información de conferencias de Audio. Puede hacerlo con la **Skype centro de administración de la empresa** y haciendo clic en **Enviar información de conferencia por correo electrónico** en las propiedades de un usuario. Al enviar este correo electrónico, contendrá toda la información de conferencias de audio, incluidos:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
- El id. de conferencia del usuario.
    
    > [!NOTE]
    > Identificadores estáticos se usan cuando los usuarios de su organización no necesita recordar un número aleatorio; Puede seleccionar un número determinado o utilice uno que sea fácil de recordar. Cuando se usan los identificadores de conferencia dinámicos, cada reunión las programaciones de un usuario obtener asignará un identificador único. Si desea asignar dinámico en lugar de la conferencia estático identificadores, [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Aquí tiene un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Enviar un correo electrónico con la información de conferencias de audio a un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial**y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios** y, a continuación, seleccione el usuario.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
> [!TIP]
> También puede enviar correo electrónico al usuario con la configuración de conferencias de audio editar las propiedades del usuario y, a continuación, haciendo clic en **conferencias de Audio** > **Enviar información de conferencia por correo electrónico**. 
  
## ¿Qué más debe saber sobre este correo electrónico?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencias de Audio** en ellos.
    
  - Al restablecer manualmente PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita una licencia de **Conferencias de Audio** de ellos.
    
  - Cuando se cambia el proveedor de conferencias de audio para un usuario de Microsoft a otro proveedor, o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencias de audio para un usuario a Microsoft.
    
- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:
    
  - Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.
    
  - Establezca el parámetro SendEmailOverride en True.
    
  - Escriba el nombre de la pantalla de correo electrónico en el parámetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 
  
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
    Para enviar un correo electrónico al usuario con su información de conferencias de audio, ejecute lo siguiente:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

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
  

