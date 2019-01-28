---
title: Direcciones URL e intervalos de direcciones IP de Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9673d25234f4dfa8d28259701a18739c5307ee9
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2019
ms.locfileid: "29593921"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Office 365
=====================================

Vaya a [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obtener una lista detallada y actualizada de la direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para los equipos. Microsoft está mejorando continuamente el servicio Office 365 y agregar la nueva funcionalidad, lo que significa que los puertos requeridos, las direcciones URL, y pueden cambiar las direcciones IP a través del tiempo. Se recomienda que [suscribirse a través de RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando esta información se actualiza o se ha cambiado.

Los equipos de la experiencia de llamadas y las reuniones se basa en la siguiente generación basada en la nube infraestructura que también se usa en Skype y Skype para la empresa. Estas inversiones en tecnología incluyen servicios de nube basados en Azure para el procesamiento y la señalización de medios, códec de vídeo H.264, códecs de audio SILK y Opus, resiliencia de red, telemetría y diagnósticos de la calidad. Por lo tanto, hay direcciones URL y direcciones IP que son necesarios que pueda asociarse con Skype y Skype para la empresa.

Para todas las cargas de trabajo de Office 365, el método recomendado de conexión a los servicios de los equipos es no usar al proxy de reenvío que sea posible. Cuando un servidor proxy se sitúa entre un cliente y los centros de datos de Office 365, es posible que se puede forzar la medios a través de TCP en lugar de UDP, que podría afectar la calidad de los medios. Descargar archivos de PAC de proxy de ejemplo que se pueden usar para configurar el desvío de tráfico desde [los extremos de administración de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si las directivas de seguridad y redes requieren el tráfico de Office 365 fluya a través de un servidor proxy, asegúrese de que ya se cumplan los requisitos anteriores antes de implementar los equipos en producción (revisión de [Los servidores Proxy de Skype para empresarial en línea](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) para instrucciones).
