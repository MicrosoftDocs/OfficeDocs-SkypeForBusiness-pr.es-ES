---
title: Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas de la delegación de Skype Empresarial Online. En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos para la solución de problemas.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010803"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online

En este artículo se explica cómo configurar y solucionar problemas de la delegación de Skype Empresarial Online. En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos para la solución de problemas.
  
## <a name="guidelines-and-requirements"></a>Directrices y requisitos

### <a name="guidelines-for-delegation"></a>Directrices para la delegación

Configurar y hacer que la delegación funcione correctamente depende de que se de acuerdo con estas instrucciones:
  
- Debe usar el cliente completo de Skype Empresarial 2015 con las últimas actualizaciones o el cliente completo de Skype Empresarial 2016.
    
- Debe usar el cliente de Outlook 2013 con las últimas actualizaciones o el cliente de Outlook 2016.
    
- Asegúrese de que el delegador y los equipos delegados tienen un perfil de correo de Outlook que sea el principal o el perfil predeterminado. Ese perfil de correo debe contener solo una cuenta.
    
- Skype Empresarial para el delegador y el delegado deben ser usuarios en línea. Además, el Exchange Server para cada cuenta debe ser en línea o ambos ser locales.
    
- Tanto el delegado como el delegado deben usar la misma versión principal de Outlook.
    
- El **valor del atributo EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente. Puede comprobar esta configuración ejecutando el cmdlet **Get-CSClientPolicy** en el módulo PowerShell de Skype Empresarial Online.
    
- Tanto el delegado como el delegado deben haber iniciado sesión en Skype Empresarial y Outlook al mismo tiempo en diferentes estaciones de trabajo.
    
- Los buzones compartidos no son compatibles con la delegación en Skype Empresarial Online. Esto se debe a que el buzón compartido no tiene la lista de control de acceso (ACL) **sendonbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Compatibilidad con la versión del cliente de Skype Empresarial

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Cliente básico de Lync/Skype Empresarial**| No se admite |No se admite
|**Skype Empresarial 2015**|Compatible| Compatible|
|**Skype Empresarial 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Requisitos de licencias

**Escenario de licencias Enterprise E3**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> |El cliente de Skype Empresarial Basic no admite la delegación.  <br/> Para los clientes Mac, puede delegar las llamadas, pero no las reuniones.  <br/> |
|Enterprise E3 con Office 365 Phone System + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |El cliente de Skype Empresarial Basic no admite la delegación.  <br/> Para los clientes Mac, puede delegar las llamadas, pero no las reuniones.  <br/> |
   
**Escenario de licencias Enterprise E5**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016.  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> |El cliente de Skype Empresarial Basic no admite la delegación.  <br/> Para los clientes Mac, puede delegar las llamadas, pero no las reuniones.  <br/> |
|Enterprise E5 plus Plan de llamadas de Office 365  <br/> |Skype Empresarial para Mac 2016  <br/> Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |El cliente de Skype Empresarial Basic no admite la delegación.  <br/> Para los clientes Mac, puede delegar las llamadas, pero no las reuniones.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar y comprobar la delegación

Para configurar la delegación de Skype Empresarial Online, siga estos pasos:
  
### <a name="for-windows-clients"></a>Para clientes Windows

 **Pestaña Desviado de llamadas**
  
1. Seleccione **Opciones de**  >    >  **Herramientas, Configuración del reenvío de llamadas.**
    
2. Seleccione **Editar mis miembros delegados.**
    
3. Seleccione **Agregar,** seleccione el delegado que desea agregar y, a continuación, haga clic **en Aceptar.**
    
 **Sin pestaña Desviado de llamadas**
  
1. En Outlook, seleccione Configuración **de la cuenta de**  >    >  **archivo: Agregar acceso**  >  **delegado.**
    
2. Busque y agregue el nombre de la persona que será el delegado.
    
3. Seleccione el **menú** Calendario y, a continuación, **seleccione Editor (puede leer, crear y modificar elementos).**
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac: Lync

 **Pestaña Desviado de llamadas**
  
- Si el cliente no  tiene una pestaña Desviador de llamadas que tenga el vínculo Editar mis miembros delegados y el delegador se encuentra en un equipo Mac, el delegador debe iniciar sesión en un equipo basado en Windows para configurar la delegación.  Esto se debe a que los clientes Mac no pueden realizar conexiones MAPI y esto es un requisito para establecer la delegación de Skype Empresarial desde Outlook.
    
### <a name="verify-success"></a>Comprobar éxito

Si la configuración se realiza correctamente, el delegado debería ver el mensaje Se le agregó  como delegado de < **Name>** y también que se creó el grupo Personas a las que manage llamadas. El delegador debe ver que se **ha** creado el grupo Delegados.
  
> [!NOTE]
> Los permisos de delegación suelen aparecer en un plazo de 30 minutos tras el proceso de configuración. Sin embargo, este proceso puede tardar hasta 24 horas en completarse. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Problemas comunes

- > **Problema 1** La entrada del delegado continúa apareciendo en el grupo Personas a las que manageo llamadas **después** de que el delegador haya quitado el delegado del cliente de Outlook.
    
  - > **Resolución 1** En el cliente de Skype Empresarial, haga clic con el botón derecho en el delegado del grupo **Delegados** y, a continuación, **seleccione Quitar del grupo.**
    
- > **Problema 2** Una vez concedido el acceso delegado a través del cliente de Outlook, ni el mensaje de confirmación ni las personas a las que administra las llamadas para **el** grupo aparecen para el delegado.
    
  - > **Resolución 2** Quite la delegación del cliente de Outlook, espere unos 15 minutos para la replicación y, a continuación, agregue el delegado de nuevo.
    
### <a name="other-common-issues"></a>Otros problemas comunes

- La delegación no funciona si se supera el umbral de 25 delegadores y 25 delegados.
    
- El cliente de Skype Empresarial Basic no es compatible.
    
    > [!NOTE]
    > Si instala el cliente de Skype Empresarial Basic, se quitará la delegación y se romperá la delegación. 
  
- Si el **valor del estado MAPI** no es **correcto,** asegúrese de que los valores **SIP** y **SMTP** coinciden.
    
    > [!NOTE]
    > El estado MAPI puede tardar varios  minutos en mostrarse como correcto tras iniciar por primera vez Skype Empresarial y Outlook.
  
- No se admite la creación de un grupo de seguridad ni la adición de permisos de delegación para ese grupo de seguridad.
    
- MAPI no está disponible. Vea [el error "MAPI no disponible" en el cliente de Skype Empresarial 2016.](https://support.microsoft.com/help/3147130)
    
- El buzón de Exchange Online no es accesible a través del cliente de Skype Empresarial. Si esto ocurre, ejecute la prueba [de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que se completa.
    
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
