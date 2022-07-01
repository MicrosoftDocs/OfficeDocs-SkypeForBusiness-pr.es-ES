---
title: Direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Obtenga información sobre cómo configurar microsoft 365 o Office 365 direcciones URL e intervalos de direcciones IP correctamente y omitir el proxy de reenvío cuando sea posible para las conexiones con el servicio de Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563738"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365

Vaya a [Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para Teams. Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que [se suscriba a través de RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para recibir notificaciones cuando esta información se actualice o cambie.

La experiencia de llamadas y reuniones de Teams se basa en la nueva infraestructura basada en la nube que también usan Skype y Skype Empresarial. Entre estas inversiones tecnológicas se incluyen servicios en la nube basados en Azure para procesamiento de medios y señalización, códec de vídeo H.264, códec de audio SILK y Opus, resistencia de red, telemetría y diagnósticos de calidad. Por lo tanto, hay direcciones URL e IP necesarias que pueden estar asociadas con Skype y Skype Empresarial.

Para todas las cargas de trabajo de Microsoft 365 y Office 365, el método de conexión recomendado para los servicios de Teams es omitir el proxy de reenvío siempre que sea posible. Cuando un servidor proxy se coloca entre un cliente y los centros de datos de Office 365, es posible que los medios se vean forzados a través de TCP en lugar de UDP, lo que afectaría a la calidad de los medios. Descargue archivos PAC de proxy de ejemplo que se pueden usar para configurar la omisión del tráfico desde [Administrar Microsoft 365 y Office 365 puntos de conexión](/office365/enterprise/managing-office-365-endpoints).

Si las directivas de red y seguridad requieren Que Microsoft 365 o Office 365 tráfico fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción. Para obtener más información, lea [Servidores proxy para Teams o Skype Empresarial Online](proxy-servers-for-skype-for-business-online.md).