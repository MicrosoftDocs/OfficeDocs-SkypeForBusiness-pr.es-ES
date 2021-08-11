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
description: En este artículo se explica cómo configurar y solucionar problemas Skype Empresarial delegación en línea. En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos de solución de problemas.
ms.openlocfilehash: c672006e8b78e5b3fb881da97e2ab3bbe65e465aa5981cc95fb2caf9bed39e4f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310179"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se explica cómo configurar y solucionar problemas Skype Empresarial delegación en línea. En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos de solución de problemas.
  
## <a name="guidelines-and-requirements"></a>Directrices y requisitos

### <a name="guidelines-for-delegation"></a>Directrices para la delegación

Configurar y conseguir que la delegación funcione correctamente depende de si sigue estas directrices:
  
- Debe usar el cliente completo Skype Empresarial 2015 con las últimas actualizaciones o el cliente completo Skype Empresarial 2016.
    
- Debe usar el cliente Outlook 2013 con las últimas actualizaciones o el Outlook 2016 cliente.
    
- Asegúrese de que el delegado y los equipos delegados tienen un Outlook de correo electrónico que es el perfil principal o el predeterminado. Ese perfil de correo solo debe contener una cuenta.
    
- Skype Empresarial para el delegado y el delegado deben ser usuarios en línea. Además, los Exchange Server para cada cuenta deben ser en línea o ambos locales.
    
- Tanto el delegado como el delegado deben usar la misma versión principal de Outlook.
    
- El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente. Puede comprobar esta configuración ejecutando el cmdlet **Get-CSClientPolicy** en el módulo Skype Empresarial PowerShell en línea.
    
- Tanto el delegado como el delegado deben haber iniciado sesión en Skype Empresarial y Outlook al mismo tiempo en diferentes estaciones de trabajo.
    
- Los buzones compartidos no son compatibles con Skype Empresarial delegación en línea. Esto se debe a que el buzón compartido no tiene la lista de control de acceso (ACL) **de sendonbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Skype Empresarial versión de cliente

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype Empresarial cliente básico**| No se admite |No se admite
|**Skype Empresarial 2015**|Compatible| Compatible|
|**Skype Empresarial 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Requisitos de licencia

**Enterprise Escenario de licencias E3**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> |Skype Empresarial El cliente básico no admite la delegación.  <br/> Para los clientes Mac, puede delegar llamadas, pero no reuniones.  <br/> |
|Enterprise E3 con Sistema telefónico de Office 365 + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype Empresarial El cliente básico no admite la delegación.  <br/> Para los clientes Mac, puede delegar llamadas, pero no reuniones.  <br/> |
   
**Enterprise Escenario de licencias E5**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016.  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> |Skype Empresarial El cliente básico no admite la delegación.  <br/> Para los clientes Mac, puede delegar llamadas, pero no reuniones.  <br/> |
|Enterprise E5 más Office 365 plan de llamadas  <br/> |Skype Empresarial para Mac 2016  <br/> Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016  <br/> Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype Empresarial El cliente básico no admite la delegación.  <br/> Para los clientes Mac, puede delegar llamadas, pero no reuniones.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar y comprobar la delegación

Para configurar la Skype Empresarial en línea, siga estos pasos:
  
### <a name="for-windows-clients"></a>Para Windows clientes

 **Pestaña Reenvío de llamadas**
  
1. Seleccione **Herramientas Opciones**  >  **de** reenvío de llamadas  >  **Configuración**.
    
2. Seleccione **Editar mis miembros delegados.**
    
3. Seleccione **Agregar**, seleccione el delegado que desea agregar y, a continuación, seleccione **Aceptar.**
    
 **Pestaña Sin reenvío de llamadas**
  
1. En Outlook, seleccione Cuenta  >  **de archivo Configuración** Agregar acceso  >    >  **delegado.**
    
2. Busque y agregue el nombre de la persona que va a ser el delegado.
    
3. Seleccione el **menú** Calendario y, a continuación, **seleccione Editor (puede leer, crear y modificar elementos).**
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac: Lync

 **Pestaña Reenvío de llamadas**
  
- Si el cliente no  tiene una pestaña Desviado de llamadas que tiene el vínculo Editar mis miembros delegados y el delegado se encuentra en un equipo Mac, el delegado debe iniciar sesión en un equipo basado en Windows para configurar la delegación.  Esto se debe a que los clientes Mac no pueden realizar conexiones MAPI y este es un requisito para establecer Skype Empresarial delegación desde Outlook.
    
### <a name="verify-success"></a>Comprobar el éxito

Si la configuración se realiza correctamente, el delegado debería ver el mensaje Se le agregó  como delegado para < Nombre>y también que se crea el grupo Personas que administra llamadas **para.** El delegado debe ver que se crea el **grupo** Delegados.
  
> [!NOTE]
> Los permisos de delegación suelen aparecer en un plazo de 30 minutos desde el proceso de configuración. Sin embargo, este proceso puede tardar hasta 24 horas en completarse. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Problemas comunes

- > **Problema 1** La entrada de delegado sigue apareciendo en el grupo Personas que administra llamadas **para** después de que el delegado haya quitado el delegado del Outlook cliente.
    
  - > **Resolución 1** En el Skype Empresarial, haga clic con el botón derecho en el delegado en el grupo **Delegados** y, a continuación, **seleccione Quitar del grupo.**
    
- > **Problema 2** Una vez concedido el acceso delegado a través del cliente Outlook, ni el mensaje de confirmación ni el grupo Personas que administra llamadas **para** aparecen para el delegado.
    
  - > **Resolución 2** Quite la delegación del Outlook, espere unos 15 minutos para la replicación y, a continuación, agregue de nuevo el delegado.
    
### <a name="other-common-issues"></a>Otros problemas comunes

- La delegación no funciona si se supera el umbral de 25 delegados y 25 delegados.
    
- El Skype Empresarial basic no es compatible.
    
    > [!NOTE]
    > Si instala el Skype Empresarial Basic, quitará y interrumpirá la delegación. 
  
- Si el **valor Estado MAPI** no es **correcto,** asegúrese de que los valores **SIP** y **SMTP** coinciden.
    
    > [!NOTE]
    > El estado MAPI puede tardar varios  minutos en mostrarse como correcto después de iniciar por primera vez Skype Empresarial y Outlook.
  
- No se admite la creación de un grupo de seguridad y la adición de permisos de delegación para ese grupo de seguridad.
    
- MAPI no está disponible. Vea [el error "MAPI no disponible" en Skype Empresarial cliente de 2016.](https://support.microsoft.com/help/3147130)
    
- El Exchange Online de correo electrónico no es accesible a través Skype Empresarial cliente. Si esto ocurre, ejecute la prueba [Outlook de conectividad para](https://testconnectivity.microsoft.com/) asegurarse de que se supera.
    
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
