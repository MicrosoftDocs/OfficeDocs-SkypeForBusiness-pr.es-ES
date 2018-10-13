---
title: Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación en línea de negocio. En este artículo se ofrece instrucciones para el programa de instalación recomendaciones, procedimientos recomendados y pasos para solucionar problemas.
ms.openlocfilehash: e3131b28be1ad01e0965b2739dc152a627826d5e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546679"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online

En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación en línea de negocio. En este artículo se ofrece instrucciones para el programa de instalación recomendaciones, procedimientos recomendados y pasos para solucionar problemas.
  
## <a name="guidelines-and-requirements"></a>Instrucciones y requisitos

### <a name="guidelines-for-delegation"></a>Directrices para la delegación

Configurar y obtención de delegación para que funcione correctamente dependen de seguir estas instrucciones:
  
- Debe usar la Skype para todo el cliente de 2015 empresarial con las últimas actualizaciones o la Skype para todo el cliente de 2016 empresarial.
    
- Debe usar el cliente de Outlook 2013 con las actualizaciones más recientes o el cliente de Outlook 2016.
    
- Asegúrese de que el usuario delegado y equipos de delegado tienen un perfil de correo de Outlook que es la principal o el perfil predeterminado. Ese perfil de correo debe contener únicamente una cuenta.
    
- Skype para la empresa para el usuario delegado y el delegado debe ser usuarios en línea. Además, los buzones de Exchange Server para cada cuenta debe ser estar en línea o local.
    
- El usuario delegado y el delegado deben usar la misma versión principal de Outlook.
    
- El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente. Puede comprobar esta configuración, ejecute el cmdlet **Get-CSClientPolicy** en la Skype para el módulo de PowerShell en línea de negocio.
    
- El usuario delegado y el delegado deben haber iniciado sesión en Skype para profesionales y Outlook al mismo tiempo en diferentes estaciones de trabajo.
    
- Buzones compartidos no son compatibles para Skype para la delegación en línea de negocio. Esto es debido a que el buzón compartido no tiene la lista de control de acceso (ACL) de **sendonbehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Skype para compatibilidad con la versión de cliente de negocio

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype para cliente básico de negocio**| No se admite |No se admite
|**Skype Empresarial 2015**|Compatible| Compatible|
|**Skype para profesionales de 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Los requisitos de licencia

**Escenario de licencias E3 de empresa**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016  <br/> |Skype para cliente empresarial básica no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.  <br/> |
|E3 de empresa con el sistema telefónico de Office 365 + xCalling Plan de Office 365  <br/> |Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype para cliente empresarial básica no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.  <br/> |
   
**Escenario de licencia Enterprise E5**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|E5 de la empresa  <br/> |Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o 2016 de Outlook.  <br/> Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016  <br/> |Skype para cliente empresarial básica no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.  <br/> |
|E5 Enterprise plus Plan de llamada de Office 365  <br/> |Skype para la empresa para Mac 2016  <br/> Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype para cliente empresarial básica no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar y comprobar la delegación

Para configurar Skype para la delegación en línea de negocio, siga estos pasos:
  
### <a name="for-windows-clients"></a>Para los clientes de Windows

 **Ficha de desvío de llamadas**
  
1. Seleccione **Herramientas** > **Opciones de** > **configuración de desvío de llamadas**.
    
2. Seleccione **Editar a Mis miembros delegados**.
    
3. Seleccione **Agregar**, seleccione al delegado que desea agregar y, a continuación, seleccione **Aceptar**.
    
 **Ninguna ficha de desvío de llamadas**
  
1. En Outlook, seleccione **archivo** > **Configuración de la cuenta** > **Acceso delegado** > **Agregar**.
    
2. Busque y, a continuación, agregue el nombre de la persona que se va a ser el delegado.
    
3. Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.
    
### <a name="for-mac-clients---lync"></a>Para los clientes de Mac - Lync

 **Ficha de desvío de llamadas**
  
- Si el cliente no tiene una ficha de **Desvío de llamadas** que tiene el vínculo **Editar mis miembros a delegados** y el usuario delegado se encuentra en un equipo Mac, el usuario delegado debe iniciar sesión en un equipo basado en Windows con el fin de configurar la delegación. Esto es debido a que los clientes de Mac no pueden realizar conexiones de MAPI y es un requisito para establecer Skype para la delegación de negocio desde Outlook.
    
### <a name="verify-success"></a>Compruebe el éxito

Si el programa de instalación se realiza correctamente, el delegado debería ver la **ha sido agregado como delegado para < nombre >** mensaje y también que se crea el grupo **de personas puedo administrar las llamadas para** . El usuario delegado debería ver que se ha creado el grupo de **delegados** .
  
> [!NOTE]
> Permisos de delegación suelen aparecerán dentro de 30 minutos al proceso de instalación. Sin embargo, este proceso puede tardar hasta 24 horas para llevar a cabo. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Problemas comunes

- > **Problema 1** La entrada de delegado sigue apareciendo en el grupo **de personas puedo administrar las llamadas para** una vez que el usuario delegado quite al delegado desde el cliente de Outlook.
    
  - > **Resolución 1** En Skype para clientes empresariales, secundario del delegado en el grupo de **delegados** y, a continuación, seleccione **quitar de grupo**.
    
- > **Problema 2** Una vez concedido el acceso de delegado a través del cliente de Outlook, ni en el mensaje de confirmación ni en el grupo **de personas puedo administrar las llamadas para** aparecen para el delegado.
    
  - > **Resolución 2** Quitar la delegación desde el cliente de Outlook, espere unos 15 minutos para la replicación y, a continuación, vuelva a agregar al delegado.
    
### <a name="other-common-issues"></a>Otros problemas comunes

- Delegación no funciona si se supera el umbral de 25 delegators y 25 delegados.
    
- No se admite la Skype para cliente empresarial básico.
    
    > [!NOTE]
    > Si instala el Skype para cliente empresarial básico, quitará y delegación de interrupción. 
  
- Si el valor de **Estado de MAPI** no es **Aceptar**, asegúrese de que coinciden con los valores de **SIP** y **SMTP** .
    
    > [!NOTE]
    > Puede tardar varios minutos para el estado MAPI mostrar como **Aceptar** después de iniciar en primer lugar Skype para profesionales y Outlook.
  
- No se admiten la creación de un grupo de seguridad y agregar los permisos de delegación para ese grupo de seguridad.
    
- MAPI no está disponible. Vea el [error de "MAPI no está disponible" de Skype para cliente de 2016 empresarial](https://support.microsoft.com/en-us/help/3147130).
    
- El buzón de Exchange Online no está accesible a través de la Skype para clientes empresariales. Si esto ocurre, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que se pasa.
    
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
