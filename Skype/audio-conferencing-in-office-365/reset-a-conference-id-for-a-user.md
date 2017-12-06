---
title: "Restablecer un id. de conferencia para un usuario"
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
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# Restablecer un id. de conferencia para un usuario

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](6e12242c-55f7-4bf4-90d7-0f36c0326b8e.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/6e12242c-55f7-4bf4-90d7-0f36c0326b8e). 
  
Cuando las organizaciones todavía no ha habilitado para identificadores de conferencia dinámico, un identificador de conferencia estático se crea automáticamente cuando se habilita un Skype para empresas o Microsoft Teams usuario para conferencias de Audio con Microsoft como proveedor. Este ID de conferencia se incluye en la parte inferior de la reunión de invitaciones junto con los números de teléfono que pueden ser usadas por las personas que llaman para llamar a una reunión. Cuando el usuario marca el número de teléfono, el operador automático para la reunión le preguntará el llamador escriba este identificador de conferencia, por lo que pueden asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencias es Microsoft, identificadores de conferencia de los usuarios se establecen en sólo dinámicos de forma predeterminada. Desgraciadamente, no podrá cambiar en el Skype para el centro de administración de la empresa o con Windows Powershell. Tendrá que ponerse en contacto con soporte técnico de Microsoft. 
  
Identificadores estáticos se usan cuando los usuarios de su organización no necesita recordar un número aleatorio; Puede seleccionar un número determinado o utilice uno que sea fácil de recordar. Cuando se usan los identificadores de conferencia dinámicos, cada reunión las programaciones de un usuario obtener asignará un identificador único. Si desea asignar dinámico en lugar de la conferencia estático identificadores, [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Identificadores de conferencia solo se establecen automáticamente solo para Skype para Business y Microsoft Teams usuarios habilitados para conferencias de Audio con Microsoft como su proveedor de servicios de audioconferencia. Si necesita restablecer un identificador de conferencia para un usuario que está usando un proveedor de servicios de audioconferencia de terceros (ACP), deberá especificar manualmente un identificador de conferencia en la página de propiedades para el usuario.
  
## Restablecer el identificador de conferencia para un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Centro de administración de Skype Empresarial**, haga clic en **conferencias de Audio** > **usuarios**, seleccione un usuario y, a continuación, en el panel Acción, en **El identificador de conferencia**, haga clic en **Restablecer**.
    
4. En la **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Una conferencia que se crearán automáticamente ID y un correo electrónico enviado al usuario con el nuevo identificador de conferencia. De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto puede estar desactivada.
    
    > [!NOTE]
    > Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 
  
## ¿Qué más debo saber?

- Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y números de teléfono de acceso telefónico haciendo clic en **Enviar información de conferencia por correo electrónico** para el usuario en el panel acción. No enviar el PIN.
    
- Un identificador de conferencia contendrá 7 dígitos y no puede cambiar su longitud en el Skype centro de administración de la empresa o con Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El identificador de conferencia para conferencias de audio para un usuario puede verse en la parte inferior del panel de acciones en **conferencias de Audio** cuando se selecciona el usuario en la página **usuarios**.
    
- Después de crea un nuevo identificador de conferencia, el identificador de conferencia antiguo no puede ser usado por las personas que llaman. Debe notificar a los usuarios a programar sus existentes invitaciones para asegurarse de que la conferencia nueva que identificador se agrega a las invitaciones de la reunión. Los usuarios pueden usar Skype Empresarial herramienta de reuniones para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reuniones de empresa, consulte:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)
    
  - [Skype empresarial Online, la herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype empresarial Online, la herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

