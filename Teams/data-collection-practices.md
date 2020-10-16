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
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Obtenga información acerca de cómo Microsoft recopila datos de censo, uso y error para comprender el uso de Teams y Skype empresarial para planear mejoras de producto.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651238"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Prácticas de recopilación de datos de Skype empresarial y Microsoft Teams

Skype empresarial server y Skype empresarial online, junto con las aplicaciones de Skype empresarial y Microsoft Teams, recopilan datos para que Microsoft pueda comprender cómo se usan estos productos y qué tipos de errores (como errores de inicio de sesión) se han producido. Esta información nos ayuda a comprender los patrones de uso, a planificar nuevas características, y a localizar y solucionar áreas problemáticas.

Mientras que algunos datos de uso se recopilan automáticamente, otros datos solo se pueden recopilar si el administrador o el usuario decide permitirlos. La recopilación de datos se divide en estas tres categorías:

- Datos de censo

- Datos de uso

- Datos de informes de errores

## <a name="census-data"></a>Datos de censo

Los datos del censo se adquieren únicamente para proporcionar, respaldar y mejorar Skype empresarial. Microsoft Teams y Skype empresarial online. Incluye información sobre el entorno, como las versiones de los dispositivos y sistemas operativos, y las configuraciones regionales y de idioma. También incluye contadores para intentos de inicio de sesión y errores. Aquí se muestran algunos ejemplos específicos de los datos de censo que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |El Id. tiene un algoritmo hash que se realiza dos veces: una en el cliente y otra en el servicio de telemetría. El algoritmo hash garantiza que el Id. no se puede vincular a un usuario específico.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |El Id. del dispositivo es un GUID que se genera de forma aleatoria una vez en el dispositivo y se envía al servicio de telemetría.  <br/> |

Los datos de censo NO contienen ninguna información que identifique a su organización o a los usuarios. Para obtener más información, vea la [declaración de privacidad de Skype empresarial](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).

De forma predeterminada, los datos de censo están activados y los administradores o los usuarios finales no pueden desactivarlos.

## <a name="usage-data"></a>Datos de uso

Los datos de uso incluyen información como el número de llamadas realizadas, el número de mensajes instantáneos enviados o recibidos, el número de reuniones a las que se ha asistido, la frecuencia con que se usan las características y los problemas de estabilidad.

Los datos de uso podrían contener información que identifique su organización, como contoso.com. Aquí se muestran algunos ejemplos específicos de los datos de uso que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Mensaje instantáneo enviado  <br/> |12  <br/> ||
|Mensaje instantáneo recibido  <br/> |5  <br/> ||
|Unirse a una reunión (intentos)  <br/> |5  <br/> ||
|Unirse a una reunión (éxito)  <br/> |4  <br/> ||
|Minutos de las llamadas y reuniones  <br/> |30 min.  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Este es el nombre de la organización registrada en Office 365 y se transmite en texto no cifrado, lo que significa que no está ofuscado.  <br/> |

Los datos de censo NO contienen ninguna información que identifique a sus usuarios.

La recopilación de datos de uso está activada de forma predeterminada, pero los administradores locales pueden desactivarla mediante la configuración de la directiva de grupo DisableAutomaticSendTracing en Skype empresarial server. Desactivar esta configuración afectará a todos los usuarios de la organización. Para obtener más información, vea [Configurar las directivas de arranque de cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).

Los usuarios finales no pueden activar o desactivar la recopilación de datos de uso.

En el caso de la aplicación Reuniones de Skype y en las páginas web del iniciador de combinación, la manera de controlar la telemetría es a través de esta directiva:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Esta directiva es falsa de forma predeterminada, por lo que la recopilación de telemetría está desactivada de forma predeterminada. Esta configuración es por grupo y controla todos los usuarios que se conectan con la aplicación Reuniones de Skype a una reunión hospedada en ese servidor.

## <a name="error-reporting-data"></a>Datos de informes de errores

Los datos de informe de errores pueden incluir información sobre el rendimiento y la fiabilidad, la configuración de los dispositivos, la calidad de la conexión de la red, los códigos de error, los registros de errores y las excepciones. Aquí se muestran algunos ejemplos específicos de datos de informe de errores que se recopilan:

|**Tipo de datos**|**Ejemplo**|**Notas**|
|:-----|:-----|:-----|
|Dirección del mensaje  <br/> |Recibida  <br/> ||
|Estado de la conversación  <br/> |Inactivo  <br/> ||
|Id. del hilo de conversación  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |El Id. se envía como texto cifrado, el servicio de telemetría aplica un algoritmo hash antes de almacenarlo.  <br/> |

Los datos de notificación de errores también pueden contener información de identificación personal como la dirección IP del usuario y el Identificador uniforme de recursos del protocolo de inicio de sesión (SIP URI). Vea la [Declaración de privacidad de Skype empresarial](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obtener una explicación detallada de lo que se ha recopilado.

El informe de errores necesita dos cosas:

- La configuración de la directiva de grupo DisableAutomaticSendTracing está establecida en falso en el servidor o en el centro de administración de espacios empresariales (este es el estado predeterminado). Para obtener más información, vea [Configurar las directivas de arranque de cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).
    
- Los usuarios finales pueden participar en la pestaña General (haga clic en el icono de engranaje ![un icono que representa un engranaje ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) y, después, se abrirá el cuadro de diálogo **Opciones** con la pestaña **General** desplegada) en el cliente de Skype empresarial.
    
 
![Captura de pantalla de la casilla de recopilación de datos en el cuadro de diálogo Opciones](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
En la aplicación Reuniones de Skype, la telemetría MeetingUxEnable también controla la notificación de errores, aunque en el caso de los bloqueos en Windows, la configuración de Watson controla la carga de la información de los bloqueos. No hay ninguna configuración de usuario para las aplicaciones de Reuniones de Skype, como la que se muestra en el cuadro de diálogo cliente de escritorio.

Para obtener más información, vea [Establecer opciones generales en Skype empresarial](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).

Para configurar su red, vea [Configurar su red para Skype Empresarial Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).

Si usa Microsoft 365 u Office 365 operado por 21Vianet en China, vea [Configurar su red para Skype empresarial online operado por 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Temas relacionados
[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
