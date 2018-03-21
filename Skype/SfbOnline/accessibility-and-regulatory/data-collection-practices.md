---
title: "Prácticas de recopilación de datos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
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
hideEdit: 
description: "Microsoft recopila datos de censos, el uso y el error para entender cómo se utiliza Skype para el negocio y donde los usuarios tienen problemas. Los datos se utilizan para planificar mejoras del producto."
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype para las prácticas de recopilación de datos de negocio y Teams de Microsoft

Skype para Business Server 2015, Skype para los negocios en línea, junto con Skype para aplicaciones de negocios y Teams de Microsoft recopilar datos para ayudar a Microsoft a entender cómo se utilizan estos productos y qué tipos de errores, como errores de inicio de sesión, se han producido. Esta información nos ayuda a comprender los patrones de uso, planificar nuevas características y solucionar problemas y corregir las áreas con problemas.
  
Mientras que algunos datos de uso se recopilan automáticamente, otros datos pueden recopilarse sólo cuando el administrador o el usuario decide permitirla. Recopilación de datos se divide en estas tres categorías:
  
- Datos del censo
    
- Datos de uso
    
- Datos de informe de errores
    
## <a name="census-data"></a>Datos del censo

Datos del censo se adquiere únicamente para proporcionar, soporte y mejorar Skype para el negocio. Los equipos de Microsoft y Skype para negocios en línea. Incluye información medioambiental, como las versiones del dispositivo y el sistema operativo y configuración regional y de idioma. También incluye contadores de intentos de inicio de sesión y errores. A continuación presentamos algunos ejemplos específicos de los que se recopilan datos del censo:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|ID de usuario  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |El identificador se calcula dos veces: una vez en el cliente y otra vez en el servicio de telemetría. El hash garantiza que el identificador no puede vincularse a un usuario específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |El identificador de dispositivo es un GUID que se genera una vez en el dispositivo y envía al servicio de telemetría aleatoriamente.  <br/> |
   
Datos del censo no contienen ninguna información que identifica la organización o los usuarios. Consulte el [Skype para la declaración de privacidad de la empresa](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener más información.
  
Datos del censo está activada de forma predeterminada y no se puede desactivar por los administradores o los usuarios finales.
  
## <a name="usage-data"></a>Datos de uso

Estos datos incluyen información como el número de llamadas realizadas, número de IMs enviados o recibidos, número de reuniones Unido, frecuencia de características se utilizan y problemas de estabilidad.
  
Uso de datos puede contener información que identifique a su organización, como contoso.com. A continuación presentamos algunos ejemplos específicos de los datos de uso se recopilan:
  
|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Mensajes Instantáneos enviados  <br/> |12  <br/> ||
|Recibido de IM  <br/> |5  <br/> ||
|Unirse a una reunión (intentos)  <br/> |5  <br/> ||
|Unirse a una reunión (correcto)  <br/> |4  <br/> ||
|Actas de reunión o llamada  <br/> |30 minutos  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este es el nombre de la organización registrada en Office 365 y se transmite en texto sin cifrar, lo que significa que no se ofusca.  <br/> |
   
Datos de uso no contienen ninguna información que identifica a los usuarios.
  
Colección de datos uso está activada de forma predeterminada, pero local Administradores pueden desactivarlo utilizando la configuración de directiva de grupo DisableAutomaticSendTracing en Skype para Business Server 2015. Desactivar esta configuración afecta a todos los usuarios de la organización. Para obtener más información, consulte [Configurar directivas de inicio de cliente de Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Los usuarios finales no puede activar la recopilación de datos de uso o desactivar.
  
Para reuniones de Skype la aplicación y las páginas web de selector de combinación, la forma de controlar la telemetría es a través de esta directiva:
  
Set-CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Esta directiva de forma predeterminada en false, para que colección de telemetría está desactivada de forma predeterminada. Esta configuración es por grupo y controla todos los usuarios que se conectan con la aplicación de las reuniones de Skype a una reunión alojada en ese servidor.
  
## <a name="error-reporting-data"></a>Datos de informe de errores

Datos de informes de error pueden incluir información sobre rendimiento y confiabilidad, configuración de dispositivo, calidad de la conexión de red, los códigos de error, registros de errores y excepciones. A continuación presentamos algunos ejemplos específicos de datos que se recopilan de informe de errores:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Dirección del mensaje  <br/> |Entrante  <br/> ||
|Estado de la conversación  <br/> |Inactivo  <br/> ||
|Identificador de subproceso de conversación  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA ==  <br/> ||
|ID de usuario  <br/> |amosmarble <br/> |El identificador se envía en texto no cifrado, que el servicio de telemetría aplica un algoritmo hash antes de guardarlo  <br/> |
   
Datos de informes de error también pueden contener información personal como dirección IP y la Session Initiation Protocol Uniform Resource Identifier (URI de SIP) del usuario. Consulte el [Skype para la declaración de privacidad de la empresa](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se recopila.
  
Informe de errores requiere dos cosas:
  
- Establecer la configuración de directiva de grupo de DisableAutomaticSendTracing en False en el servidor o en el centro de administración de inquilinos (es decir, el estado predeterminado). Para obtener más información, consulte [Configurar directivas de inicio de cliente de Skype para Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Los usuarios finales individualmente optar desde la ficha General (haga clic en el icono del engranaje y del cuadro de diálogo se abre con la ficha General muestra) en el Skype por la empresa cliente.
    
     ![Icono de engranaje](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype para Business checkbox de colección de datos en las opciones > diálogo General](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para la aplicación de las reuniones de Skype, el MeetingUxEnableTelemetry controla también informes de errores, aunque fallos en Windows, la configuración de Watson control carga información de bloqueo. No hay ninguna configuración de usuario para la aplicación de las reuniones de Skype como se puede ver en el cuadro de diálogo cliente de escritorio.
  
Consulte [Opciones Set General en Skype para el negocio](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obtener más información.
  
Puede ver [configurar su red para Skype para los negocios en línea](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar la red.
  
Si está utilizando Office 365 operado por 21Vianet en China, consulte [Configurar la red para Skype para los negocios en línea operado por 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## <a name="related-topics"></a>See also
[Programa para la mejora de la experiencia del usuario](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
