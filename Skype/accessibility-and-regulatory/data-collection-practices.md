---
title: "Skype para Business y Microsoft Teams prácticas de recopilación de datos"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype para Business y Microsoft Teams prácticas de recopilación de datos

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
clientes Skype Empresarial Server 2015, Skype Empresarial Online y Skype Empresarial recopilan datos para ayudar a Microsoft a comprender cómo se utilizan estos productos y qué tipos de errores, como los errores de inicio de sesión, se han producido. Esta información nos ayuda a comprender los patrones de uso, planear características nuevas y solucionar problemas y corregir las áreas de problema.
  
Mientras que algunos datos de uso se recopilan de manera automática, otros datos solo pueden recopilarse cuando el administrador o el usuario lo permite. La recopilación de datos se divide en estas tres categorías: 
  
- Datos censales
    
- Datos de uso
    
- Datos de informe de errores
    
## Datos censales

Datos del censo se adquieren únicamente para proporcionar, soporte técnico y mejorar Skype Empresarial y Skype Empresarial Online. Incluye información ambiental como versiones de dispositivo y el sistema operativo y configuración regional y de idioma. También diversos recuentos de intentos de inicio de sesión y errores. Estos son algunos ejemplos específicos de los datos del censo que se recopilan:
  
|
|
|****Tipo de datos****|****Ejemplo****|****Notas****|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |ES-ES  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |El Id. se encripta dos veces: una en el cliente y otra vez en el servicio de telemetría. El hash garantiza que el Id. no esté vinculado a un usuario específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |El identificador de dispositivo es un GUID que ha generado una vez en el dispositivo y envía al servicio de telemetría aleatoriamente.  <br/> |
   
Datos del censo no contienen información que identifica la organización o los usuarios. Consulte la [Skype para la declaración de privacidad de la empresa](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener más información.
  
Los datos censales están activados de forma predeterminada y no pueden desactivarse por los administradores ni por los usuarios finales.
  
## Datos de uso

Los datos de uso incluyen información como el número de llamadas realizadas, el número de mensajes instantáneos enviados o recibidos, el número de reuniones en las que ha participado, la frecuencia de las características usadas y los problemas de estabilidad.
  
Los datos de uso podrían contener información que identifique a su organización, como contoso.com. Aquí se muestran algunos ejemplos específicos de los datos de uso que se recopilan:
  
|
|
|****Tipo de datos****|****Ejemplo****|****Notas****|
|:-----|:-----|:-----|
|Mensaje instantáneo enviado  <br/> |12  <br/> ||
|Mensaje instantáneo Recibido  <br/> |5  <br/> ||
|Unirse a una reunión (intentos)  <br/> |5  <br/> ||
|Unirse a una reunión (realizado)  <br/> |4  <br/> ||
|Minutos de la llamada o la reunión  <br/> |30 minutos  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este es el nombre de la organización registrada en Office 365 y se transmite en texto no cifrado, lo que significa que no está ofuscada.  <br/> |
   
Los datos de uso NO contienen ninguna información que identifique a los usuarios.
  
Recopilación de datos de uso está activada de forma predeterminada, pero los administradores pueden desactivar la opción usando la configuración de directiva de grupo DisableAutomaticSendTracing en Skype Empresarial Server 2015 en local. La desactivación de esta configuración afecta a todos los usuarios de la organización. Para obtener más información, vea [Configurar directivas de inicio de cliente de Skype empresarial Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Los usuarios finales no se puede activar la recopilación de datos de uso o desactivar.
  
Aplicación de reuniones de Skype y las páginas web de selector de combinación, la manera de controlar telemetría es a través de esta directiva:
  
Establecer CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Esta directiva predeterminado es false, por lo que la colección de telemetría está desactivada de forma predeterminada. Esta configuración es por grupo y controles de todos los usuarios que se conectan con la aplicación de las reuniones de Skype a una reunión alojada en el servidor.
  
## Datos de informe de errores

Los datos de informe de errores pueden contener información acerca del rendimiento y la confiabilidad, la configuración del dispositivo, la calidad de la conexión a la red, los códigos de error, los registros de error y las excepciones. Aquí se muestran algunos ejemplos específicos de los datos de informe de errores que se recopilan:
  
|
|
|****Tipo de datos****|****Ejemplo****||
|:-----|:-----|:-----|
|Dirección del mensaje  <br/> |Entrante  <br/> ||
|Estado de la conversación  <br/> |Inactivo  <br/> ||
|Id. del hilo de conversación  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> ||El Id. se envía como texto no cifrado , que el servicio de telemetría encripta antes de almacenarlo  <br/> |
   
Datos de informes de error también pueden contener información personal como dirección IP y la sesión de iniciación protocolo identificador uniforme de recursos (URI del SIP) del usuario. Consulte la [Skype para la declaración de privacidad de la empresa](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se recopila.
  
El informe de errores requiere dos cosas: 
  
- Establecer la configuración de directiva de grupo DisableAutomaticSendTracing en False en el servidor o en el centro de administración de inquilinos (es decir, el estado predeterminado). Para obtener más información, vea [Configurar directivas de inicio de cliente de Skype empresarial Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Los usuarios finales individualmente participar en desde la ficha General (haga clic en el icono de engranaje y el cuadro de diálogo de la opción, se abre con la ficha General muestra) en el cliente Skype Empresarial.
    
     ![Icono de engranaje](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Aplicación de reuniones de Skype, la MeetingUxEnableTelemetry controla también informes de errores, aunque para se bloquea en Windows, la configuración de Watson control cargar información de bloqueo. No hay ningún valor de usuario de la aplicación de reuniones de Skype igual que aparece en el cuadro de diálogo de cliente de escritorio.
  
Consulte [Configurar opciones generales en Skype Empresarial](http://technet.microsoft.com/library/e1a46d3e-dcea-437a-ba7b-6d442a40f439%28Office.14%29.aspx) para obtener más información.
  
Puede ver [Configurar una red para Skype Empresarial Online](http://technet.microsoft.com/library/81fa5e16-418d-4698-a5f0-e666211c5c66%28Office.14%29.aspx) para configurar su red.
  
Si está usando Office 365 operador por 21Vianet en China, consulte [Set up your network for Lync Online](http://technet.microsoft.com/library/d21f89b0-3afc-432e-b735-036b2432fdbf%28Office.14%29.aspx).
  
## Temas relacionados

[Programa para la mejora de la experiencia del usuario](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[URL de Office 365 e intervalos de direcciones IP](http://technet.microsoft.com/library/8548a211-3fe7-47cb-abb1-355ea5aa88a2%28Office.14%29.aspx)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

