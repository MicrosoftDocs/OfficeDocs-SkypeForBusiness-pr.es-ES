---
title: "Configurar y solucionar problemas de Skype para la delegación de los negocios en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación de los negocios en línea. En este artículo se ofrece instrucciones para instalación recomendaciones, prácticas recomendadas y pasos para solucionar problemas."
ms.openlocfilehash: b69f6712f78906bc955d3ce014fe8ccd6ab252c1
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar y solucionar problemas de Skype para la delegación de los negocios en línea

En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación de los negocios en línea. En este artículo se ofrece instrucciones para instalación recomendaciones, prácticas recomendadas y pasos para solucionar problemas.
  
## <a name="guidelines-and-requirements"></a>Requisitos y directrices

### <a name="guidelines-for-delegation"></a>Directrices para la delegación

Configurar y obtener la delegación funcione correctamente dependen de seguir estas directrices:
  
- Debe utilizar el Skype para 2015 de negocio cliente completo con las actualizaciones más recientes o el Skype para el cliente completo de 2016 de negocio.
    
- Debe utilizar el cliente de Outlook 2013 con las últimas actualizaciones o el cliente de Outlook de 2016.
    
- Asegúrese de que la persona que delega y delegado equipos tienen un perfil de correo de Outlook que es el principal o el perfil predeterminado. Que el perfil de correo debe contener sólo una cuenta.
    
- Skype para el negocio para la persona que delega y el delegado debe ser usuarios en línea. Además, los buzones de Exchange Server para cada cuenta debe estar en línea o ser locales.
    
- El usuario delegado y el delegado deben utilizar la misma versión principal de Outlook.
    
- El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente. Puede comprobar esta configuración ejecutando el cmdlet **Get-CSClientPolicy** en el Skype para el módulo de PowerShell en línea de negocio.
    
- El usuario delegado y el delegado deben iniciar sesión en Skype para Outlook y del negocio al mismo tiempo en diferentes estaciones de trabajo.
    
- Skype no admiten los buzones compartidos para la delegación de los negocios en línea. Esto es porque el buzón compartido no tiene la lista de control de acceso (ACL) de **sendonbehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Skype para compatibilidad con la versión de cliente de empresa

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype para cliente básico de negocio**| No se admite |No se admite
|**Skype para negocios 2015**|Compatible| Compatible|
|**Skype para negocios de 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Requisitos de licencia

**Escenario de licencias de empresa E3**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook  <br/> Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook  <br/> |Skype para cliente Business Basic no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no las reuniones.  <br/> |
|E3 de empresa con sistema de teléfono de Office 365 + xCalling Plan de Office 365  <br/> |Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook  <br/> Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook  <br/> Lync para Mac 2011  <br/> |Skype para cliente Business Basic no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no las reuniones.  <br/> |
   
**Escenario de licencias de empresa E5**

|**Licencia**|**Clientes**|**Notas**|
|:-----|:-----|:-----|
|E5 de la empresa  <br/> |Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook.  <br/> Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook  <br/> |Skype para cliente Business Basic no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no las reuniones.  <br/> |
|E5 Enterprise plus Plan de llamada Office 365  <br/> |Skype para empresas para Mac 2016  <br/> Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook  <br/> Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook  <br/> Lync para Mac 2011  <br/> |Skype para cliente Business Basic no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no las reuniones.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar y comprobar la delegación

Para configurar Skype para la delegación de los negocios en línea, siga estos pasos:
  
### <a name="for-windows-clients"></a>Para clientes Windows

 **Ficha de reenvío de llamada**
  
1. Seleccione **Herramientas** > **Opciones de** > **configuración de desvío de llamadas**.
    
2. Seleccione **Editar a los miembros de mi delegado**.
    
3. Seleccione **Agregar**, seleccione al delegado al que desea agregar y, a continuación, seleccione **Aceptar**.
    
 **No hay ficha de reenvío de llamada**
  
1. En Outlook, seleccione **archivo** > **Configuración de la cuenta** > **Acceso delegado** > **Agregar**.
    
2. Busque y, a continuación, agregue el nombre de la persona que va a ser el delegado.
    
3. Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.
    
### <a name="for-mac-clients---lync"></a>Para los clientes de Mac - Lync

 **Ficha de reenvío de llamada**
  
- Si el cliente no tiene una ficha de **Reenvío de llamada** que tiene el vínculo **Editar los miembros de mi delegado** , y el usuario delegado se encuentra en un equipo Mac, la persona que delega debe iniciar sesión en un equipo basado en Windows para configurar la delegación. Esto es porque los clientes de Mac no pueden establecer conexiones de MAPI y es un requisito para establecer Skype para la delegación de negocio desde Outlook.
    
### <a name="verify-success"></a>Verifique el éxito

Si la configuración es correcta, el delegado debería ver la **ha sido agregado como delegado para < nombre >** mensaje y también se crea el grupo de **personas administrar llamadas para** . La persona que delega debe ver que se crea el grupo de **delegados** .
  
> [!NOTE]
> Permisos de delegación suelen aparecerán dentro de 30 minutos del proceso de instalación. Sin embargo, este proceso puede tardar hasta 24 horas en completarse. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Problemas comunes

- > **Problema 1** La entrada de delegado sigue apareciendo en el grupo de **personas administrar llamadas para** después el usuario delegado quitó al delegado desde el cliente de Outlook.
    
  - > **Resolución 1** En Skype para Business client, haga al delegado en el grupo de **delegados** y, a continuación, seleccione **Quitar del grupo**.
    
- > **Problema 2** Una vez concedido el acceso de delegado a través del cliente de Outlook, el mensaje de confirmación ni el grupo de **personas administrar llamadas para** aparecen para el delegado.
    
  - > **Resolución 2** Quitar la delegación desde el cliente Outlook, espere unos 15 minutos para la replicación y, a continuación, vuelva a agregar al delegado.
    
### <a name="other-common-issues"></a>Otros problemas comunes

- La delegación no funcionará si se excede el umbral de 25 delegators y 25 delegados.
    
- No se admite el Skype para cliente empresarial básico.
    
    > [!NOTE]
    > Si instala el Skype para cliente empresarial básico, quitará y romper la delegación. 
  
- Si el valor de **Estado de MAPI** no es **Aceptar**, asegúrese de que coinciden con los valores **SIP** y **SMTP** .
    
    > [!NOTE]
    > Puede tardar varios minutos para que el estado MAPI mostrar como **Aceptar** después de iniciar por primera vez Skype para Outlook y del negocio.
  
- Crear un grupo de seguridad y agregar permisos de delegación de ese grupo de seguridad no es compatible.
    
- MAPI no está disponible. Vea el [error de "MAPI no disponible" de Skype para 2016 de negocio cliente](https://support.microsoft.com/en-us/help/3147130).
    
- El buzón de Exchange en línea no es accesible a través del Skype para Business client. Si esto ocurre, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que pasa.
    
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
