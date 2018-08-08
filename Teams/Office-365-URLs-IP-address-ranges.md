---
title: Direcciones URL e intervalos de direcciones IP de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998976"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Office 365
=====================================

Vaya a [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) para obtener una lista detallada y actualizada de la direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para los equipos. Microsoft está mejorando continuamente el servicio Office 365 y agregar la nueva funcionalidad, lo que significa que los puertos requeridos, las direcciones URL, y pueden cambiar las direcciones IP a través del tiempo. Se recomienda que [suscribirse a través de RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando esta información se actualiza o se ha cambiado.

Los equipos de la experiencia de llamadas y las reuniones se basa en la siguiente generación basada en la nube infraestructura que también se usa en Skype y Skype para la empresa. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad. Por lo tanto, hay direcciones URL y direcciones IP que son necesarios que pueda asociarse con Skype y Skype para la empresa.

Para todas las cargas de trabajo de Office 365, el método recomendado de conexión a los servicios de los equipos es no usar al proxy de reenvío que sea posible. Cuando un servidor proxy se sitúa entre un cliente y los centros de datos de Office 365, es posible que se puede forzar la medios a través de TCP en lugar de UDP, que podría afectar la calidad de los medios. Descargar archivos de PAC de proxy de ejemplo que se pueden usar para configurar el desvío de tráfico desde [los extremos de administración de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si las directivas de seguridad y redes requieren el tráfico de Office 365 fluya a través de un servidor proxy, asegúrese de que ya se cumplan los requisitos anteriores antes de implementar los equipos en producción (revisión de [Los servidores Proxy de Skype para empresarial en línea](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) para instrucciones).
