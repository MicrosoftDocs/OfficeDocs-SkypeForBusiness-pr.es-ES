---
title: Direcciones URL e intervalos de direcciones IP de Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37563874"
---
<a name="office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Office 365
=====================================

Vaya a [Intervalos de direcciones IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para ver una lista detallada y actualizada de las direcciones URL, las direcciones IP, los puertos y los protocolos que deben estar bien configurados para Teams. Microsoft trata de mejorar constantemente el servicio de Office 365 así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que [se suscriba a través de las redes sociales](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando esta información se cambie o se modifique.

La experiencia de llamadas y reuniones de Teams está integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios en la nube basados en Azure para el procesamiento de medios y la señalización, códec de vídeo H. 264, códec de audio de seda y Opus, resistencia de red, telemetría y diagnósticos de calidad. Del mismo modo, algunas de las direcciones URL y direcciones IP que se requieren podrían estar asociadas con Skype y Skype Empresarial.

En el caso de todas las cargas de trabajo de Office 365, el método de conexión con los servicios de Teams que se recomienda consiste en omitir el proxy de reenvío siempre que sea posible. Cuando un servidor proxy se coloca entre un cliente y los centros de datos de Office 365, es posible que se fuerce el paso de un elemento multimedia por TCP en lugar de por UDP, lo que afectaría a la calidad del medio. Descargue los archivos PAC del proxy de muestra que se pueden usar para configurar la omisión de tráfico en [Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si las directivas de red y de seguridad requieren que el tráfico de Office 365 fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción (Revise [los servidores proxy para equipos o Skype empresarial online](proxy-servers-for-skype-for-business-online.md) . para obtener instrucciones).
