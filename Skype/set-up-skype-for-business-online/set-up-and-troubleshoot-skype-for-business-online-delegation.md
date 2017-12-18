---
title: "Configurar y solucionar problemas de Skype empresarial Online delegación"
ms.author: tonysmit
author: tonysmit
ms.date: 11/23/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
description: "En este artículo se explica cómo configurar y solucionar problemas de Skype empresarial Online delegación. En este artículo se ofrece instrucciones para recomendaciones de instalación, procedimientos recomendados y pasos para solucionar problemas."
---

# Configurar y solucionar problemas de Skype empresarial Online delegación

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
En este artículo se explica cómo configurar y solucionar problemas de Skype empresarial Online delegación. En este artículo se ofrece instrucciones para recomendaciones de instalación, procedimientos recomendados y pasos para solucionar problemas.
  
## Directrices y requisitos

### Directrices para la delegación

Configurar y obtener delegación funcione correctamente dependen está siguiendo estas instrucciones:
  
- Debe estar usando el Skype empresarial 2015 cliente completo con las actualizaciones más recientes o la Skype cliente completo de empresa 2016.
    
- Debe estar usando el cliente de Outlook 2013 con las últimas actualizaciones o el cliente de Outlook 2016.
    
- Asegúrese de que la persona que delega y equipos de delegado tienen un perfil de correo de Outlook que es el principal o el perfil predeterminado. Que el perfil de correo debe contener solo una cuenta.
    
- Skype empresarial para la persona que delega y el delegado debe ser usuarios en línea. Además, los buzones de Exchange Server para cada cuenta debe estar en línea o estar local.
    
- La persona que delega y el delegado deben estar usando la misma versión principal de Outlook.
    
- El valor del atributo **EnableExchangeDelegateSync** se debe establecer en **true** en la directiva de cliente. Puede comprobar esta configuración, ejecute el cmdlet **Get-CSClientPolicy** en el Skype para módulo de PowerShell en línea de negocio.
    
- La persona que delega y el delegado deben haber iniciado sesión Skype para Business y Outlook al mismo tiempo en diferentes estaciones de trabajo.
    
- Buzones compartidos no se admiten para Skype para la delegación de empresa en línea. Esto es porque el buzón compartido no tiene la lista de control de acceso (ACL) de **sendonbehalf**.
    
### Skype para la compatibilidad con la versión de cliente de empresa

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync o Skype empresarial Client básico**|
|:-----|
|**Skype Empresarial 2015**|
|:-----|
|**Skype Empresarial 2016**|
|:-----|
   
### Requisitos de licencia

**Escenario de licencias Enterprise E3**

|****Licencia****|****Clientes****|****Notas****|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 de empresa se usa con Outlook 2013 o Outlook 2016  <br/> |Skype empresarial básicas cliente no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no en conferencias.  <br/> |
|Enterprise E3 con el sistema telefónico de Office 365 + xCalling Plan de Office 365  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 de empresa se usa con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype empresarial básicas cliente no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no en conferencias.  <br/> |
   
**Escenario de licencias de empresa E5**

|****Licencia****|****Clientes****|****Notas****|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 o Outlook 2016.  <br/> Skype para 2016 de empresa se usa con Outlook 2013 o Outlook 2016  <br/> |Skype empresarial básicas cliente no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no en conferencias.  <br/> |
|E5 Enterprise plus Plan de llamada de Office 365  <br/> |Skype empresarial para Mac 2016  <br/> Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 o Outlook 2016  <br/> Skype para 2016 de empresa se usa con Outlook 2013 o Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype empresarial básicas cliente no admite la delegación.  <br/> Para los clientes de Mac, puede delegar llamadas pero no en conferencias.  <br/> |
   
## Configurar y comprobar la delegación

Para configurar Skype para empresarial Online delegación, siga estos pasos:
  
### Los clientes de Windows

 **Ficha de desvío de llamadas**
  
1. Seleccione **Herramientas** > **Opciones** > **configuración de desvío de llamadas**.
    
2. Seleccione **Editar a Mis miembros delegados**.
    
3. Seleccione **Agregar**, seleccione al delegado que desea agregar y, a continuación, seleccione **Aceptar**.
    
 **Ninguna ficha desvío de llamadas**
  
1. En Outlook, seleccione **archivo** > **Configuración de la cuenta** > **Delegar el acceso** > **Agregar**.
    
2. Busque y, a continuación, agregue el nombre de la persona que será el delegado.
    
3. Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.
    
### Para clientes de Mac: Lync

 **Ficha de desvío de llamadas**
  
- Si el cliente no dispone de una pestaña de **Desvío de llamadas** que tiene el vínculo **Editar mis miembros a delegados** y la persona que delega se encuentra en un equipo Mac, la persona que delega debe iniciar sesión en un equipo basado en Windows para configurar la delegación. Esto es porque los clientes de Mac pueden realizar las conexiones MAPI y esto es necesario establecer Skype para la delegación de la empresa desde Outlook.
    
### Verificar el éxito

Si la configuración es correcta, el delegado debe ver la **ha sido agregado como delegado para < nombre >** mensaje y también se crea el grupo de **personas administro llamadas**. La persona que delega debe ver que se ha creado el grupo **delegados**.
  
> [!NOTE]
> Permisos de delegación suelen aparecerán en 30 minutos del proceso de instalación. Sin embargo, este proceso puede tardar hasta 24 horas. 
  
## Solución de problemas

### Problemas comunes

> **Problema 1** La entrada de delegado sigue apareciendo en el grupo de **personas administro llamadas** después de la persona que delega quitó al delegado desde el cliente de Outlook.
    
    **Solución 1** En Skype empresarial Client, haga clic en el delegado en el grupo **delegados** y, a continuación, seleccione **Quitar del grupo**.
    
> **Problema 2** Después de que se le ha concedido acceso delegado a través del cliente de Outlook, el mensaje de confirmación ni el grupo de **personas para administrar llamadas para las que** aparecen para el delegado.
    
    **Solución 2** Quitar la delegación desde el cliente de Outlook, espere aproximadamente 15 minutos para la replicación y, a continuación, agregar el delegado.
    
### Otros problemas comunes

- Delegación no funciona si se excede el umbral de 25 delegators y 25 delegados.
    
- No se admite la Skype cliente empresas básicas.
    
    > [!NOTE]
    > Si instala la Skype cliente empresas básicas, quitará e interrumpir la delegación. 
  
- Si el valor de **Estado de MAPI** no **Aceptar**, asegúrese de que coinciden con los valores de **SIP** y **SMTP**.
    
    > [!NOTE]
    > Puede tardar varios minutos para que el estado MAPI mostrar como **Aceptar** después de iniciar Skype para Business y Outlook por primera vez.
  
- Crear un grupo de seguridad y agregar permisos de delegación de ese grupo de seguridad no es compatible.
    
- MAPI no está disponible. Consulte [error "MAPI no disponible" en Skype empresarial 2016 cliente](https://support.microsoft.com/en-us/help/3147130).
    
- El buzón de Exchange Online no está disponible a través de la Skype empresarial Client. Si se produce esta situación, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que pasa.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

