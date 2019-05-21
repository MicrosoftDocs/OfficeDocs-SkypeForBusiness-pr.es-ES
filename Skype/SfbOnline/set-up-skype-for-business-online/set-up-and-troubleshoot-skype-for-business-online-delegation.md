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
f1keywords: None
ms.custom:
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas de delegación de Skype empresarial online. Este artículo le ofrece instrucciones para las recomendaciones de configuración, procedimientos recomendados y pasos de solución de problemas.
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285248"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online

En este artículo se explica cómo configurar y solucionar problemas de delegación de Skype empresarial online. Este artículo le ofrece instrucciones para las recomendaciones de configuración, procedimientos recomendados y pasos de solución de problemas.
  
## <a name="guidelines-and-requirements"></a>Pautas y requisitos

### <a name="guidelines-for-delegation"></a>Directrices para la delegación

La configuración y la obtención de la delegación para funcionar correctamente depende de estas pautas:
  
- Debe usar el cliente completo de Skype empresarial 2015 con las actualizaciones más recientes o el cliente completo de Skype empresarial 2016.
    
- Debe usar el cliente de Outlook 2013 con las actualizaciones más recientes o el cliente de Outlook 2016.
    
- Asegúrese de que los delegados y los equipos delegados tienen un perfil de correo de Outlook que es el principal o el predeterminado. Ese perfil de correo debería contener solo una cuenta.
    
- Skype empresarial para el delegador y el delegado deben ser usuarios en línea. Además, los buzones de Exchange Server para cada cuenta deben estar conectados o ser locales.
    
- Tanto el delegado como el delegado deben usar la misma versión principal de Outlook.
    
- El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la Directiva de cliente. Puede comprobar esta configuración ejecutando el cmdlet **Get-ClientPolicy** en el módulo de PowerShell de Skype empresarial online.
    
- Tanto el delegado como el delegado deben haber iniciado sesión en Skype empresarial y Outlook al mismo tiempo en diferentes estaciones de trabajo.
    
- Los buzones compartidos no son compatibles con la delegación de Skype empresarial online. Esto se debe a que el buzón de correo compartido no tiene la lista de control de acceso (ACL) **sendonbehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Compatibilidad con versiones de cliente de Skype empresarial

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype empresarial para clientes básicos**| No compatible |No compatible
|**Skype Empresarial 2015**|Compatible| Compatible|
|**Skype empresarial 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Requisitos de licencias

**Escenario de licencias de Enterprise E3**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016  <br/> Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016  <br/> |El cliente básico de Skype empresarial no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas, pero no reuniones.  <br/> |
|Enterprise E3 con Office 365 Phone System + Office 365 plan xCalling  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016  <br/> Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |El cliente básico de Skype empresarial no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas, pero no reuniones.  <br/> |
   
**Escenario de licencias de Enterprise E5**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016.  <br/> Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016  <br/> |El cliente básico de Skype empresarial no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas, pero no reuniones.  <br/> |
|Enterprise E5 más plan de llamadas de Office 365  <br/> |Skype empresarial para Mac 2016  <br/> Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016  <br/> Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |El cliente básico de Skype empresarial no es compatible con la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas, pero no reuniones.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar y comprobar la delegación

Para configurar la delegación de Skype empresarial online, siga estos pasos:
  
### <a name="for-windows-clients"></a>Para clientes de Windows

 **Ficha desvío de llamadas**
  
1. Seleccione **herramientas** > **Opciones Opciones** > de**desvío de llamadas**.
    
2. Seleccione **Editar mis miembros**delegados.
    
3. Seleccione **Agregar**, seleccione el delegado que desea agregar y, a continuación, seleccione **Aceptar**.
    
 **Pestaña sin desvío de llamadas**
  
1. En Outlook, seleccione **** > **configuración** > de la cuenta de archivo**delegar acceso** > **Add**.
    
2. Busque y agregue el nombre de la persona que será el delegado.
    
3. Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac: Lync

 **Ficha desvío de llamadas**
  
- Si el cliente no tiene una ficha de **desvío de llamadas** que tiene el vínculo **Editar mis miembros del delegado** y el delegador se encuentra en un equipo Mac, el delegadodor debe iniciar sesión en un equipo basado en Windows para poder configurar la delegación. Esto se debe a que los clientes de Mac no pueden hacer conexiones MAPI, y esto es un requisito para establecer la delegación de Skype empresarial desde Outlook.
    
### <a name="verify-success"></a>Comprobar el éxito

Si la configuración se realiza correctamente, el delegado debería ver lo **que se agregó como delegado de _LT_ Name>** mensaje y también se crean las personas a las que administro las **llamadas para** el grupo. El delegador debe ver que **** se crea el grupo delegados.
  
> [!NOTE]
> Los permisos de delegación suelen aparecer dentro de los 30 minutos del proceso de configuración. Sin embargo, este proceso puede demorar hasta 24 horas en completarse. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Problemas comunes

- > **Problema 1** La entrada de delegado continúa apareciendo en las **llamadas de grupo personas que administro** después de que el delegador haya eliminado el delegado del cliente de Outlook.
    
  - > **Solución 1** En el cliente de Skype empresarial, haga clic con el botón derecho en **** el delegado en el grupo delegados y, a continuación, seleccione **quitar del grupo**.
    
- > **Problema 2** Después de conceder acceso delegado a través del cliente de Outlook, no se muestra para el delegado ni el mensaje de confirmación ni las **personas que administro las llamadas para** el grupo.
    
  - > **Solución 2** Quite la delegación del cliente de Outlook, espere aproximadamente 15 minutos para la replicación y, a continuación, vuelva a agregar el delegado.
    
### <a name="other-common-issues"></a>Otros problemas comunes

- La delegación no funciona si se supera el umbral de 25 delegados y 25 delegados.
    
- No se admite el cliente de Skype empresarial Basic.
    
    > [!NOTE]
    > Si instala el cliente de Skype empresarial Basic, se eliminará y interrumpirá la delegación. 
  
- Si el valor de **Estado de MAPI** no es **correcto**, asegúrese de que los valores **SIP** y **SMTP** coinciden.
    
    > [!NOTE]
    > El estado de MAPI puede tardar varios minutos en mostrarse como **correcto** después de iniciar Skype empresarial y Outlook.
  
- No se admite la creación de un grupo de seguridad ni la adición de permisos de delegación para ese grupo de seguridad.
    
- MAPI no está disponible. Consulte el [error "MAPI unavailable" en el cliente de Skype empresarial 2016](https://support.microsoft.com/en-us/help/3147130).
    
- No se puede obtener acceso al buzón de Exchange Online a través del cliente de Skype empresarial. Si esto sucede, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que pasa.
    
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
