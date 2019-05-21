---
title: Prestación del plan de audioconferencia “Llamada de salida”/“Llamarme al”
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'A los clientes se les ha proporcionado una capacidad de llamada gratuita que finalizará el 30 de noviembre de 2019.  A partir del 1 de diciembre de 2019, cada suscripción de audioconferencia proporciona 60 minutos por usuario a cualquiera de los países de la zona A, tal y como se describe en este documento. '
ms.openlocfilehash: 8c60a469684705b2a227711c5bfb22cd6baa9111
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283527"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>Beneficios de la suscripción de audioconferencias de "acceso telefónico local"/"llamarme al"

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft Teams y conferencias de audio RTC de Skype empresarial

A los clientes se les ha proporcionado una [capacidad de llamada gratuita](complimentary-dial-out-period.md) que finalizará el 30 de noviembre de 2019. A partir del 1 de diciembre de 2019, cada suscripción de audioconferencia proporciona 60 minutos por usuario y se puede usar para llamar a números no Premium en cualquiera de los países de la zona, tal y como se describe en este documento. El tamaño del grupo de minutos de acceso telefónico de inquilino ** se basa en las licencias asignadas y no en las licencias compradas. Este beneficio es aplicable a las licencias de *suscripción mensuales* de audioconferencias y no se extiende a las licencias de audioconferencia por minuto. 

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>Conferencias de audio "llamar desde una reunión" & "llamarme al" más información

Para los clientes que adoptan nuestro servicio de audioconferencia, Microsoft ofrece la posibilidad de marcar desde las reuniones organizadas por los usuarios a los que se les ha asignado una licencia de suscripción de audioconferencia. Las llamadas de llamada a países que no están incluidos en la lista de países de la "zona A" se cobran por minuto con créditos de comunicaciones. Para las llamadas de aceptación de llamada que se facturan por minuto (llamadas que superen el grupo de minutos de llamadas de inquilino o a destinos que no se encuentran en la lista de países de la zona), las llamadas y las tarifas correspondientes se basan en el destino de la llamada y no en el país del organizador de la residencia o el participante de la reunión que inicia la llamada de aceptación de llamada. Por ejemplo, una llamada de llamada de conferencia de audio a un número de teléfono en Francia, que es un país de zona, se facturará a la misma tarifa por minuto si fue iniciada por un participante de la reunión en Estados Unidos, Francia o Zimbabue. 


|Ubicación de uso de licencias de organizador de reuniones |Destino marcado |¿Puedo usar mis minutos de grupos de minutos de llamadas?|¿Necesito créditos de comunicación?|
|---------|---------|---------|---------|
|Estados Unidos |Estados Unidos |Sí (zona A de zona) |Sí *después* de consumir el grupo de minutos de inquilino         |
|Estados Unidos |Reino Unido|Sí (zona A de zona) |  Sí *después* de consumir el grupo de minutos de inquilino       |
|Estados Unidos     |Zimbabue|    No     |     Sí en *todas las* llamadas    |
|Reino Unido     |Reino Unido|Sí (zona A de zona) |  Sí *después* de consumir el grupo de minutos de inquilino       |
|Reino Unido     |Estados Unidos |Sí (zona A de zona) |  Sí *después* de consumir el grupo de minutos de inquilino       |
|Reino Unido     |Zimbabue|    No     |   Sí en *todas las* llamadas      |
|Zimbabue     |Zimbabue|    No     |    Sí en *todas las* llamadas     |
|Zimbabue     |Estados Unidos | Sí (zona A de zona) | Sí *después* de consumir el grupo de minutos de inquilino        |
|Zimbabue     |Reino Unido | Sí (zona A de zona) | Sí *después* de consumir el grupo de minutos de inquilino        |
|Islas Cook     |Islas Cook |   No      |    Sí en *todas las* llamadas     |
|Islas Cook     |Estados Unidos  | Sí (zona A de zona) |  Sí *después* de consumir el grupo de minutos de inquilino       |
|Islas Cook     |Reino Unido | Sí (zona A de zona) | Sí *después* de consumir el grupo de minutos de inquilino        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>¿Cómo se calculan los grupos de minutos?

Considere el ejemplo siguiente. Un cliente ha comprado 115 licencias de suscripción de audioconferencias y tiene 10 usuarios en Estados Unidos, 100 usuarios en el Reino Unido y 5 usuarios en Zimbabue, todos con licencias de suscripción de audioconferencia asignadas. Todos los usuarios de 115 comparten un grupo de (115 usuarios x 60 min = 6.900 conferencias, minutos de espera por mes del calendario) para realizar llamadas salientes a números no Premium en cualquiera de los países de la zona a, *independientemente* de dónde se haya concedido la licencia o el organizador de la reunión. encuentra. Por ejemplo, un organizador de la reunión de Zimbabue podrá llamar a cualquiera de los países de la zona hasta el límite de la agrupación de minutos. 

- Todas las llamadas de acceso telefónico que superen los 6.900 minutos por mes del calendario se cobran por minuto usando créditos de comunicaciones de nuestras tarifas publicadas para ese destino. (Nota: el cliente debe configurar [créditos de comunicaciones](what-are-communications-credits.md) y asignar la licencia de créditos para comunicaciones al organizador de la reunión).
- Todas las llamadas de llamada a destinos que no se encuentren en la lista de países de la zona A se facturan por minuto con créditos de comunicaciones de nuestras tarifas publicadas a ese destino (siempre que el cliente haya configurado créditos en las comunicaciones y le haya asignado la licencia de créditos de comunicaciones) al organizador de la reunión).

## <a name="how-can-i-monitor-minute-pool-usage"></a>¿Cómo puedo supervisar el uso del grupo de minutos?

- Puede supervisar el uso de su grupo de minutos de aceptación de llamada en el centro de administración de Skype empresarial "heredado". En el centro de administración de Microsoft Teams **** > , vaya a**informes** > de portales heredados de**minutos RTC**. La zona a la que se asignará un grupo de minutos de salida de llamada en el informe como "llamadas salientes a un país de la zona a".
- Las notificaciones por correo electrónico se enviarán a todos los administradores de inquilinos de un cliente dado cuando la utilización del grupo de minutos de llamadas salientes del inquilino haya alcanzado el 80% y el 100%.

Para obtener más información sobre créditos de comunicación, consulte [créditos de comunicaciones](what-are-communications-credits.md).


|Países de la zona A |
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
