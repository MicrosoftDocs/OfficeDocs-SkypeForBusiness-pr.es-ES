---
title: Suscripción de conferencia de audio "Saliente" / "Llamada llamándome al" de beneficios
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Los clientes se han proporcionado una capacidad de salida complementaria que termina el 30 de noviembre de 2019.  A partir de 1 de diciembre de 2019, cada suscripción de conferencias de audio proporciona 60 minutos por usuario al mes a cualquiera de los países de la zona A tal como se describe en este documento. '
ms.openlocfilehash: 890441987eb0f08d67afe8a7f231c9a534c59a7f
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2019
ms.locfileid: "31809434"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-benefit"></a>Suscripción de conferencia de audio "Saliente" / "Llamada llamándome al" de beneficios

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Los equipos de Microsoft y Skype para conferencias de Audio de RTC de negocio

Los clientes se han proporcionado una [capacidad de salida complementaria](complimentary-dial-out-period.md) que termina el 30 de noviembre de 2019. A partir de 1 de diciembre de 2019, cada suscripción de conferencias de audio proporciona 60 minutos por usuario al mes a cualquiera de los países de la zona A tal como se describe en este documento. El tamaño del grupo de servidores de salida de minuto inquilino se basa en las licencias *asignadas* y no adquirido licencias. Este beneficio es aplicable a las licencias de *suscripción mensual* de conferencias de Audio y no se extiende a las licencias de pago por minuto de conferencias de Audio. 

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>Conferencia "Marcar un número de una reunión" & "Llamada llamándome al" Detalles del audio

Para los clientes que adopten nuestro servicio de conferencias de Audio, Microsoft proporciona la capacidad de marcar un número de las reuniones organizadas por los usuarios asignados a una licencia de suscripción de conferencias de Audio. Las llamadas de salida a países no incluidos en la lista de país de la "Zona A" se cargan por minuto con créditos Communications. Para las llamadas de salida de la que se facturan por minuto (llamadas que superen el grupo de servidores de inquilino de salida minuto o las llamadas a destinos no está en la lista de país de la zona A), las llamadas y sus índices asociados se basan en el destino de la llamada y no del organizador país de residencia o iniciar la llamada de salida de los participantes. Por ejemplo, una llamada de salida de la conferencia de audio a un número de teléfono en Francia, que es un país de la zona A, se cargará a la misma velocidad por minuto si lo iniciada por el participante de una reunión en los Estados Unidos, Francia o Zimbabue. 


|Ubicación de uso de licencia de organizador de la reunión |Marcado de destino |¿Puedo usar Mis minutos de salida de minuto grupo?|¿Es necesario Communications créditos?|
|---------|---------|---------|---------|
|Estados Unidos |Estados Unidos |Sí (país de la zona A) |Sí *después de* consumir el grupo minuto inquilino         |
|Estados Unidos |Reino Unido|Sí (país de la zona A) |  Sí *después de* consumir el grupo minuto inquilino       |
|Estados Unidos     |Zimbabue|    No     |     Sí en *todas* las llamadas    |
|Reino Unido     |Reino Unido|Sí (país de la zona A) |  Sí *después de* consumir el grupo minuto inquilino       |
|Reino Unido     |Estados Unidos |Sí (país de la zona A) |  Sí *después de* consumir el grupo minuto inquilino       |
|Reino Unido     |Zimbabue|    No     |   Sí en *todas* las llamadas      |
|Zimbabue     |Zimbabue|    No     |    Sí en *todas* las llamadas     |
|Zimbabue     |Estados Unidos | Sí (país de la zona A) | Sí *después de* consumir el grupo minuto inquilino        |
|Zimbabue     |Reino Unido | Sí (país de la zona A) | Sí *después de* consumir el grupo minuto inquilino        |
|Islas Cook     |Islas Cook |   No      |    Sí en *todas* las llamadas     |
|Islas Cook     |Estados Unidos  | Sí (país de la zona A) |  Sí *después de* consumir el grupo minuto inquilino       |
|Islas Cook     |Reino Unido | Sí (país de la zona A) | Sí *después de* consumir el grupo minuto inquilino        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>¿Cómo se calculan los grupos de servidores minutos?

Considere el siguiente ejemplo. Un cliente ha adquirido las licencias de suscripción de conferencias de Audio 115 y tiene 10 usuarios en los Estados Unidos, 100 usuarios en el Reino Unido y 5 usuarios en Zimbabue, todas ellas con las licencias de suscripción de conferencias de Audio asignadas. Todos los 115 usuarios compartan un grupo de servidores de (115 usuarios x 60 min = 6,900 conferencia de salida de minutos por mes del calendario) para realizar llamadas salientes a cualquiera de la zona que se encuentran un países, *independientemente* de donde se concede bajo licencia el organizador de la reunión o físicamente. Por ejemplo, un organizador de la reunión Zimbabue podrán marcar un número a cualquiera de los países de la zona A hasta el límite del grupo de minuto. 

- Todas las llamadas que superan 6,900 minutos por mes del calendario se cargarán por minuto con Communications créditos a nuestros publicados velocidades de ese destino. (Nota: el cliente debe configurar [Communications créditos](what-are-communications-credits.md) y asignar la licencia de créditos de comunicaciones para el organizador de la reunión.)
- Todas las llamadas salientes a destinos no está en la lista de país de la zona se facturan por minuto con Communications créditos a nuestros publicados velocidades de ese destino (siempre que el cliente ha configurado Communications créditos y asignado la licencia de créditos de comunicaciones Organizador de la reunión).

## <a name="how-can-i-monitor-minute-pool-usage"></a>¿Cómo puedo supervisar el uso del grupo minuto?

- Puede supervisar el uso de contra el grupo de servidores de minuto de salida en el "heredado" Skype para el centro de administración de negocio. En el Microsoft Teams Admin Center, vaya al **portal heredado** > **informes** > **Grupos de servidores de RTC minuto**. El minuto de salida de la zona A grupo de servidores se denominará en el informe como "Llamadas salientes a la zona A países".
- Se enviarán notificaciones por correo electrónico a todos los administradores de inquilinos de un cliente determinado cuando el uso del grupo de servidores de acceso telefónico de salida minutos del inquilino alcanza el 80% y 100%.

Para obtener información adicional sobre crédito a la comunicación, vea [Créditos Communications](what-are-communications-credits.md).


|Países de la zona |
|---------|
|Australia      |
|Austria     |
|Bélgica     |
|Brasil     |
|Bulgaria     |
|Canadá     |
|China     |
|Croacia     |
|República Checa      |
|Dinamarca     |
|Estonia     |
|Finlandia     |
|Francia     |
|Alemania     |
|Grecia     |
|Hong Kong     |
|Hungría     |
|India     |
|Irlanda     |
|Italia     |
|Japón     |
|Luxemburgo      |
|Malasia     |
|México     |
|Países Bajos     |
|Nueva Zelanda     |
|Noruega     |
|Polonia     |
|Portugal     |
|Puerto Rico     |
|Rumania     |
|Rusia     |
|Singapur     |
|República Eslovaca     |
|Eslovenia     |
|Sudáfrica     |
|Corea del Sur     |
|España     |
|Suecia     |
|Suiza     |
|Taiwán     |
|Tailandia     |
|Estados Unidos     |
|Reino Unido|
||

## <a name="related-topics"></a>Temas relacionados

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)