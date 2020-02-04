---
title: Prácticas de recopilación de datos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Microsoft recopila datos de recuento, uso y error para comprender cómo se usa Skype empresarial y dónde se encuentran los problemas. Los datos se usan para planear mejoras del producto.
ms.openlocfilehash: e84946fd8c61daad7e16f8f7e248f4a0e06c2ae4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680467"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Prácticas de recopilación de datos de Skype empresarial y Microsoft Teams

Skype empresarial Server y Skype empresarial online, junto con las aplicaciones de Skype empresarial y Microsoft Teams, recopilar datos para ayudar a Microsoft a comprender cómo se usan estos productos y qué tipos de errores, como errores de inicio de sesión, se han producido. Esta información nos ayuda a comprender los patrones de uso, planear nuevas características y solucionar y corregir las áreas problemáticas.

Mientras que algunos datos de uso se recopilan automáticamente, otros datos solo se pueden recopilar cuando el administrador o el usuario eligen permitirlos. La recopilación de datos se divide en estas tres categorías:

- Datos de censos

- Datos de uso

- Datos de informes de errores

## <a name="census-data"></a>Datos de censos

Los datos de censos se adquieren exclusivamente para proporcionar, dar soporte técnico y mejorar Skype empresarial. Microsoft Teams y Skype empresarial online. Incluye información medioambiental, como las versiones del dispositivo y del sistema operativo, y la configuración regional y de idioma. También incluye contadores de intentos y errores de inicio de sesión. A continuación se muestran algunos ejemplos específicos de los datos de censo que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Nombreaplicación  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8,3  <br/> ||
|UserLanguage  <br/> |EN-ES  <br/> ||
|Iddeusuario  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |Se aplica un algoritmo hash dos veces: una vez en el cliente y de nuevo en el servicio de telemetría. El hash garantiza que el identificador no se puede vincular a un usuario específico.  <br/> |
|ID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |El identificador de dispositivo es un GUID que se genera de forma aleatoria una vez en el dispositivo y se envía al servicio de telemetría.  <br/> |

Los datos de censos no contienen ninguna información que identifique a la organización o a los usuarios. Para obtener más información, consulta la [declaración de privacidad de Skype empresarial](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) .

De forma predeterminada, los datos de censos están activados y los administradores o los usuarios finales no pueden desactivarlos.

## <a name="usage-data"></a>Datos de uso

Los datos de uso incluyen información como el número de llamadas realizadas, el número de mensajes instantáneos enviados o recibidos, el número de reuniones combinadas, la frecuencia de las características usadas y los problemas de estabilidad.

Los datos de uso pueden contener información que identifique a su organización, como contoso.com. A continuación se muestran algunos ejemplos específicos de los datos de uso que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Mensaje instantáneo enviado  <br/> |2007  <br/> ||
|Mensaje instantáneo recibido  <br/> |5  <br/> ||
|Unirse a una reunión (intentos)  <br/> |5  <br/> ||
|Unirse a una reunión (éxito)  <br/> |4  <br/> ||
|Minutos de la llamada o la reunión  <br/> |30 minutos  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este es el nombre de la organización registrada en Office 365 y se transmite en CLEARTEXT, lo que significa que no está ofuscada.  <br/> |

Los datos de uso no contienen ninguna información que identifique a los usuarios.

La recopilación de datos de uso está activada de forma predeterminada, pero los administradores locales pueden desactivarla usando la configuración de directiva de grupo DisableAutomaticSendTracing en Skype empresarial Server. Si desactiva esta configuración afectará a todos los usuarios de la organización. Consulte [configurar directivas](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) de inicio de cliente para obtener más información.

Los usuarios finales no pueden activar o desactivar la recopilación de datos de uso.

Para la aplicación reuniones de Skype y las páginas web del iniciador de la Unión, la manera de controlar la telemetría es a través de esta directiva:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

El valor predeterminado de esta directiva es false, por lo que la colección de telemetría está desactivada de forma predeterminada. Esta configuración es por grupo y controla todos los usuarios que se conectan con la aplicación reuniones de Skype a una reunión hospedada en ese servidor.

## <a name="error-reporting-data"></a>Datos de informes de errores

Los datos de informes de errores pueden incluir información acerca del rendimiento y la confiabilidad, la configuración del dispositivo, la calidad de la conexión de red, códigos de error, registros de errores y excepciones. A continuación se muestran algunos ejemplos específicos de los datos de informes de errores que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Dirección del mensaje  <br/> |Recibidos  <br/> ||
|Estado de la conversación  <br/> |Está  <br/> ||
|IDENTIFICADOR de conversación  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|Iddeusuario  <br/> |amosmarble <br/> |El identificador se envía en CLEARTEXT, que el servicio de telemetría aplica un algoritmo hash antes de almacenarlo.  <br/> |

Los datos de informes de errores también pueden contener información de identificación personal, como la dirección IP del usuario y el identificador uniforme de recursos (URI SIP) del Protocolo de inicio de sesión. Consulte la [declaración de privacidad de Skype empresarial](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se ha recopilado.

El informe de errores requiere dos cosas:

- La configuración de directiva de grupo DisableAutomaticSendTracing se establece en falso en el servidor o en el centro de administración de inquilinos (este es el estado predeterminado). Consulte [configurar directivas](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) de inicio de cliente para obtener más información.
    
- Los usuarios finales pueden participar individualmente desde la ficha General (haga clic en ![el icono de engranaje que representa ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) un engranaje y, a continuación, se abre el cuadro de diálogo **Opciones** con la pestaña **General** ) en el cliente de Skype empresarial.
    
 
![Captura de pantalla de la casilla de recopilación de datos en el cuadro de diálogo Opciones](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Para la aplicación reuniones de Skype, el MeetingUxEnableTelemetry también controla los informes de errores, aunque en el caso de bloqueos en Windows, el control de configuración de Watson está cargando información de bloqueo. No hay ninguna configuración de usuario para la aplicación reuniones de Skype como se ve en el cuadro de diálogo cliente de escritorio.

Para obtener más información, consulte [establecer las opciones generales en Skype empresarial](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .

Puede ver [configurar su red de Skype empresarial online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar su red.

Si está usando Office 365 ofrecido por 21Vianet en China, consulte [configurar su red para Skype empresarial online a través de 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Temas relacionados
[Programa para la mejora de la experiencia del usuario](https://www.microsoft.com/products/ceip/default.mspx)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
