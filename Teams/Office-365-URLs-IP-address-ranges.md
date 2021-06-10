---
title: Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Obtenga información sobre cómo configurar correctamente Microsoft 365 o Office 365 direcciones URL e intervalos de direcciones IP y omitir el proxy de reenvío cuando sea posible para las conexiones con Microsoft Teams servicio.
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
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP
=======================================================

Vaya a Microsoft 365 y Office 365 direcciones URL e [intervalos](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) de direcciones IP para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para Teams. Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo. Le recomendamos que [se suscriba a través de RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para recibir notificaciones cuando esta información se actualice o cambie.

La Teams de llamadas y reuniones se basa en la infraestructura basada en la nube de nueva generación que también usan Skype y Skype Empresarial. Estas inversiones tecnológicas incluyen servicios en la nube basados en Azure para procesamiento y señalización multimedia, códec de vídeo H.264, códec de audio SILK y Opus, resistencia de red, telemetría y diagnósticos de calidad. Por lo tanto, hay direcciones URL e IP necesarias que pueden estar asociadas con Skype y Skype Empresarial.

Para todas las Microsoft 365 y Office 365 de trabajo, el método de conexión recomendado para Teams servicios es omitir el proxy de reenvío siempre que sea posible. Cuando un servidor proxy se encuentra entre un cliente y los centros de datos Office 365, es posible que los medios se forzaran a través de TCP en lugar de UDP, lo que afectaría a la calidad de los medios. Descargue archivos PAC de proxy de ejemplo que se pueden usar para configurar la omisión del tráfico desde Administrar Microsoft 365 y [Office 365 extremos](/office365/enterprise/managing-office-365-endpoints).

Si las directivas de red y seguridad requieren que Microsoft 365 o Office 365 tráfico fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción. Para obtener más información, lea [Servidores proxy para Teams o Skype Empresarial en línea.](proxy-servers-for-skype-for-business-online.md)