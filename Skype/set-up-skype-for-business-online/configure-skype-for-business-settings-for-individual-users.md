---
title: "Administradores Configurar Skype Empresarial para usuarios individuales"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# Administradores: Configurar Skype Empresarial para usuarios individuales

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
En este artículo se explica cómo los administradores configuran Skype empresarial para un pequeño número de usuarios. Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets de Windows PowerShell, que puede usar.
  
Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:
  
- [Permitir que los usuarios se pongan en contacto con usuarios externos de Skype Empresarial](allow-users-to-contact-external-skype-for-business-users.md) : puede permitir que su organización use las características avanzadas de Skype Empresarial (compartir escritorios, buscar quién está en línea) para comunicarse con personas de una empresa de confianza (federada) específica. También se explica cómo bloquear la comunicación con dominios específicos.
    
- [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) . Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.
    
## Establecer la configuración general de un usuario
<a name="__toc325019204"> </a>

Debe disponer de [Acerca de los roles de administrador de Office 365](http://technet.microsoft.com/library/da585eea-f576-4f55-a1e0-87090b6aaa9d%28Office.14%29.aspx) para realizar estos pasos.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**. 
    
3. Seleccione **Usuarios**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Elija los usuarios que desea editar: 
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.
    
|**Opción**|**Detalles**|
|:-----|:-----|
|Audio y vídeo HD  <br/> |Permita que esta persona pueda grabar reuniones de audio, reuniones con audio y vídeo, o impedirle que programe reuniones (ninguna).  <br/> |
|Registrar conversaciones y reuniones  <br/> |Elija lo que puede grabar esta persona.  <br/> Esta opción no está disponible con Skype Empresarial Basic.  <br/> |
|Para cumplir con las normativas, desactive las características no archivadas  <br/> | Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos. <br/>  Si selecciona esta opción desactiva todas las características que no se capturan cuando tenga una[Suspensión en contexto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado en el centro de administración de Exchange. Desactiva las características siguientes: <br/>  Transferencia de archivos por mensajería instantánea <br/>  Páginas de OneNote compartidas <br/>  Anotaciones de PowerPoint <br/> |
   
Para configurar estas opciones de forma masiva, usar PowerShell. Ver [las directivas de administración de Skype empresarial Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## Bloquear comunicaciones externas
<a name="__toc325019206"> </a>

Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.
  
1. Seleccione **los usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar**![Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **Comunicaciones externas** y después desactive las opciones correspondientes:
    
  - **Skype externo para los usuarios empresariales**: desactive esta casilla si no desea que el usuario pueda comunicarse con otros usuarios Skype Empresarial en dominios federados.
    
  - **Los usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuitaSkype.
    
3. Haga clic en **Guardar**.
    
Para configurar estas opciones de forma masiva, usar PowerShell. Vea [administración de las comunicaciones en Skype empresarial Online con usuarios externos y las organizaciones](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## Editar la configuración de conferencias de audio para un usuario
<a name="__toc314837483"> </a>

1. Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio desea para editar, y, a continuación, elija **Editar**![Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Elija **las conferencias de Audio**, seleccione su proveedor de servicios de audioconferencia, escriba o modifique la información solicitada y, a continuación, haga clic en **Guardar**.
    
|**Configuración de conferencias de audio**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/> |
|**Número gratuito** (obligatorio) <br/> |Para un ACP de terceros, estos números de teléfono son los únicos que ha recibido en el proveedor de servicios de audioconferencia. Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números que desea que aparezcan en Skype Empresarial y Teams de Microsoft convocatorias de reunión.  <br/> |
|**Número gratuito** <br/> |Para un ACP de terceros, estos números de teléfono son los únicos que ha recibido en el proveedor de servicios de audioconferencia. Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números que desea que aparezcan en Skype Empresarial y Teams de Microsoft convocatorias de reunión.  <br/> |
|**PIN y el identificador de conferencia** (obligatorio) <br/> |El participante PIN o conferencia código, utilizado para unirse a reuniones programadas por este usuario y se proporcionan desde un proveedor de servicios de audioconferencia de terceros. Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, esto no se requiere.  <br/> |
   
Para configurar estas opciones de forma masiva, usar PowerShell. Consulte [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![Icono pequeño de LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **¿Usa Office 365 por primera vez?**         Descubra cursos en vídeo gratuitos para **administradores de Office 365 y profesionales de TI**, ofrecidos por LinkedIn Learning. |
   
## Temas relacionados
<a name="__toc314837483"> </a>

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

