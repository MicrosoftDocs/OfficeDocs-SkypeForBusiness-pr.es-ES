---
title: Direcciones URL e intervalos de direcciones IP de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 713815836b2edcad31528abc01c74a2332ecf88a
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
<a name="office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Office 365
=====================================

Ir a [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para los equipos. Microsoft está mejorando continuamente el servicio Office 365 y agregar nueva funcionalidad, lo que significa que los puertos requeridos, direcciones URL, y direcciones IP pueden cambiar con el tiempo. Recomendamos que [Suscribirse mediante RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando se actualiza o cambia esta información.

Los equipos de experiencia de llamada y las reuniones se basa en la siguiente generación basada en nube infraestructura que también es utilizada por Skype y Skype para el negocio. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad. Como tales, hay direcciones URL y direcciones IP que son necesarios que pueda asociarse con Skype y Skype para el negocio.

Para todas las cargas de trabajo de Office 365, el método recomendado de conexión a los servicios de los equipos está omitiendo al proxy de reenvío cuando sea posible. Cuando un servidor proxy se sitúa entre un cliente y los centros de datos de Office 365, los medios de comunicación pueden verse obligado sobre TCP en lugar de UDP, que afectaría la calidad media. Descargar archivos de PAC de proxy de ejemplo que pueden utilizarse para configurar la omisión de tráfico de los [extremos de administración de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si las directivas de seguridad y redes requieren Office 365 tráfico fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores se cumplen antes de implementar equipos en producción (revisión de [Servidores Proxy para Skype para los negocios en línea](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) para Guía).
