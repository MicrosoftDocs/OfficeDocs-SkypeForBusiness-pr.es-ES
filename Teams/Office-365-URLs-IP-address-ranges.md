---
title: Direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Aprenda a configurar correctamente direcciones URL e intervalos de direcciones IP de Microsoft 365 u Office 365 y omita el proxy de reenvío cuando sea posible para las conexiones con el servicio de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582127"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365
=======================================================

Vaya a [Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para Teams. Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que [se suscriba a través de las redes sociales](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando esta información se cambie o se modifique.

La experiencia de llamadas y reuniones de Teams está integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial. Estas inversiones en tecnología incluyen servicios en la nube basados en Azure para el procesamiento de medios y la señalización, códec de vídeo H. 264, códec de audio de seda y Opus, resistencia de red, telemetría y diagnósticos de calidad. Del mismo modo, algunas de las direcciones URL y direcciones IP que se requieren podrían estar asociadas con Skype y Skype Empresarial.

Para todas las cargas de trabajo de Microsoft 365 y Office 365, el método de conexión recomendado para los servicios de Teams es omitir el proxy de reenvío siempre que sea posible. Cuando un servidor proxy se coloca entre un cliente y los centros de datos de Office 365, es posible que se fuerce el paso de un elemento multimedia por TCP en lugar de por UDP, lo que afectaría a la calidad del medio. Descargue archivos PAC de proxy de muestra que se pueden usar para configurar el tráfico por omisión de la [Administración de puntos de conexión de Microsoft 365 y Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Si sus directivas de red y de seguridad requieren que el tráfico de Microsoft 365 u Office 365 fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción. Para obtener más información, lea [servidores proxy para equipos o Skype empresarial online](proxy-servers-for-skype-for-business-online.md).
