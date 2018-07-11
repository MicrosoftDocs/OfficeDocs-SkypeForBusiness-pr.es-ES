---
title: Prácticas de recopilación de datos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft recopila datos de error, el uso y el recuento para comprender cómo se utiliza Skype para la empresa y donde los usuarios tienen problemas. Los datos se usan para planear mejoras en los productos.
ms.openlocfilehash: 2175d3fea0ab5cc2ca7cb573d48e3c700ac2bd03
ms.sourcegitcommit: 1530670628e8645b9f8e2fc2786dddd989a9e908
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "20246482"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype para profesionales y Microsoft Teams prácticas de recopilación de datos

Skype para Business Server 2015, Skype para profesionales en línea, junto con Skype para las aplicaciones empresariales y Microsoft Teams recopilar datos para ayudar a Microsoft a comprender cómo se utilizan estos productos y qué tipos de errores, como errores de inicio de sesión, se han producido. Esta información nos ayuda a comprender los patrones de uso, planeación de las nuevas características y solucionar problemas y las áreas con problemas.
  
Mientras que algunos datos de uso se recopilan automáticamente, sólo se puedan recopilar otros datos cuando el usuario o el administrador decide lo permiten. Recolección de datos entra en estas tres categorías:
  
- Datos de recuento
    
- Datos de uso
    
- Datos de informes de error
    
## <a name="census-data"></a>Datos de recuento

Datos de recuento se adquieren únicamente para proporcionar, el soporte y mejorar Skype para la empresa. Los equipos de Microsoft y Skype para la empresa en línea. Incluye información del entorno, como las versiones de dispositivo y el sistema operativo y la configuración regional y de idioma. También incluye contadores para los intentos de inicio de sesión y los errores. Estos son algunos ejemplos específicos de los que se recopilan datos de recuento:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Nombre de aplicación  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |El identificador es un algoritmo hash dos veces: una vez en el cliente y de nuevo en el servicio de telemetría. El hash garantiza que el identificador no se puede vincular a un usuario determinado.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |El identificador de dispositivo es un GUID que tiene una vez generado en el dispositivo y se envía al servicio de telemetría aleatoriamente.  <br/> |
   
Datos de recuento no contienen ninguna información que identifica su organización o a los usuarios. Vea el [Skype para la declaración de privacidad de negocio](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener más información.
  
Datos de recuento está activado de forma predeterminada y no se puede desactivar por los administradores o los usuarios finales.
  
## <a name="usage-data"></a>Datos de uso

Los datos de uso incluyen información como el número de llamadas realizadas, número de mensajes instantáneos enviados o recibidos, número de reuniones se unió a, frecuencia de características que se usan y problemas de estabilidad.
  
Los datos de uso pueden contener información que identifique a su organización, por ejemplo, contoso.com. Estos son algunos ejemplos específicos de los datos de uso que se recopilan:
  
|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Mensajes Instantáneos  <br/> |12  <br/> ||
|Mensajería instantánea recibido  <br/> |5  <br/> ||
|Unirse a una reunión (intentos)  <br/> |5  <br/> ||
|Unirse a una reunión (correcto)  <br/> |4  <br/> ||
|Minutos de llamada o reunión  <br/> |30 minutos  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este es el nombre de la organización registrada en Office 365 y se transmite en texto no cifrado, lo que significa que no es confusos.  <br/> |
   
Datos de uso no contienen ninguna información que identifica a los usuarios.
  
Recolección de datos está activado de forma predeterminada, pero local Administradores pueden desactivarla utilizando la configuración de directiva de grupo DisableAutomaticSendTracing en Skype para Business Server 2015. Desactivar esta configuración afecta a todos los usuarios de la organización. Para obtener más información, vea [Configurar directivas de arranque cliente en Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Los usuarios finales no se puede activar o desactivar la recolección de datos.
  
Para la aplicación de las reuniones de Skype y las páginas de web del iniciador de participación, la forma de controlar la telemetría es a través de esta directiva:
 
`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True` 

Esta directiva el valor predeterminado es false, por lo que la colección de telemetría está desactivado de forma predeterminada. Esta configuración es por grupo y controla todos los usuarios que se conectan con la aplicación de las reuniones de Skype a una reunión hospedada en ese servidor.
  
## <a name="error-reporting-data"></a>Datos de informes de error

Datos de informes de error puede incluir información sobre el rendimiento y confiabilidad, configuración de dispositivo, calidad de la conexión de red, los códigos de error, registros de errores y excepciones. Estos son algunos ejemplos específicos de datos que se recopilan de informes de error:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Dirección del mensaje  <br/> |Entrante  <br/> ||
|Estado de la conversación  <br/> |Inactividad  <br/> ||
|Identificador de subproceso de conversación  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA ==  <br/> ||
|UserID  <br/> |amosmarble <br/> |El identificador se envía en texto no cifrado, que el servicio de telemetría aplica el algoritmo hash antes de almacenarlos  <br/> |
   
Datos de informes de error también puede contener información de identificación personal, como la dirección IP y el Session Initiation Protocol Uniform Resource Identifier (URI de SIP) del usuario. Vea el [Skype para la declaración de privacidad de negocio](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se recopilan.
  
Informes de errores requieren dos cosas:
  
- La configuración de directiva de grupo de DisableAutomaticSendTracing se establece en False en el servidor o en el centro de administración de inquilinos (es decir, el estado predeterminado). Para obtener más información, vea [Configurar directivas de arranque cliente en Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Los usuarios finales individualmente participar en de la ficha General (haga clic en el icono del engranaje ![icono de engranaje](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) y, a continuación, se abre el cuadro de diálogo **Opciones** con la ficha **General** que se muestra) en el Skype para clientes empresariales.
    
 
![Skype para checkbox de colección de datos profesionales en las opciones > cuadro de diálogo General](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para la aplicación de las reuniones de Skype, la MeetingUxEnableTelemetry controla también informes de errores, aunque para se bloquea en Windows, la configuración de Watson control cargar información de bloqueo. No hay ninguna configuración de usuario para la aplicación de las reuniones de Skype como se puede ver en el cuadro de diálogo de cliente de escritorio.
  
Para obtener más información, vea [General para establecer opciones de Skype para la empresa](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .
  
Puede ver [configurar su red para Skype para empresarial en línea](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar la red.
  
Si usa Office 365 operado por 21Vianet en China, consulte [Configurar la red para Skype para profesionales Online operado por 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## <a name="related-topics"></a>See also
[Programa para la mejora de la experiencia del usuario](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
