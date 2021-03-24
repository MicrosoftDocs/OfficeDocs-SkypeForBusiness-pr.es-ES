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
description: Obtenga información sobre cómo configurar correctamente las direcciones URL e intervalos de direcciones IP de Microsoft 365 u Office 365 y omitir el proxy de reenvío cuando sea posible para las conexiones con el servicio de Microsoft Teams.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094522"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Direcciones URL e intervalos de direcciones IP de Microsoft 365 y Office 365
=======================================================

Vaya a Direcciones URL e intervalos de direcciones IP de [Microsoft 365 y Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para Teams. Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que [se suscriba a través de RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para recibir notificaciones cuando esta información se actualice o cambie.

La experiencia de llamadas y reuniones de Teams se basa en la infraestructura basada en la nube de nueva generación que también usan Skype y Skype Empresarial. Estas inversiones tecnológicas incluyen servicios en la nube basados en Azure para procesamiento y señalización multimedia, códec de vídeo H.264, códec de audio SILK y Opus, resistencia de red, telemetría y diagnósticos de calidad. Por lo tanto, hay direcciones URL e IP necesarias que pueden estar asociadas tanto con Skype como con Skype Empresarial.

Para todas las cargas de trabajo de Microsoft 365 y Office 365, el método de conexión recomendado a los servicios de Teams es omitir el proxy de reenvío cuando sea posible. Cuando un servidor proxy se encuentra entre un cliente y los centros de datos de Office 365, es posible que los medios se fuerzan a través de TCP en lugar de UDP, lo que afectaría a la calidad de los medios. Descargue archivos PAC de proxy de ejemplo que se pueden usar para configurar la omisión del tráfico desde Administrar puntos de conexión de [Microsoft 365 y Office 365.](/office365/enterprise/managing-office-365-endpoints)

Si las directivas de seguridad y redes requieren que el tráfico de Microsoft 365 u Office 365 fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción. Para obtener más información, lea [Servidores proxy para Teams o Skype Empresarial Online.](proxy-servers-for-skype-for-business-online.md)