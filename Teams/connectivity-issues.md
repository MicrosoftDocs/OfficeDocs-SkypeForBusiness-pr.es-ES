---
title: Solucionar problemas de conectividad con el cliente de Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a resolver problemas de conectividad con el cliente de Microsoft Teams, ocasionadas principalmente por el firewall o la conexión del proxy.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101166"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Solucionar problemas de conectividad con el cliente de Microsoft Teams
==============================================================

La mayoría de los problemas detectados con el cliente de Microsoft Teams se pueden rastrear a la conectividad de firewall o proxy. Comprobar que las direcciones URL, direcciones IP y puertos necesarios se abren en el firewall o proxy minimizará la solución de problemas innecesaria. Para obtener información específica sobre direcciones URL e IP necesarias para Microsoft Teams, consulte el artículo de soporte técnico de direcciones IP y DIRECCIONES IP de [Microsoft 365 y Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) Los escenarios siguientes requieren que se abran direcciones URL y puertos específicos en el firewall.

- Autenticación

- Conectividad de cliente de Microsoft Teams

- Colaboración

- Elementos multimedia

- Servicios compartidos

- Integración de terceros

- Interoperabilidad de Skype Empresarial

- Interoperabilidad del cliente de Skype Empresarial

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Cuando Teams está sin conexión o en condiciones de ancho de banda bajo

La buena noticia es que Teams sigue ejecutándose incluso cuando está sin conexión o en condiciones de ancho de banda bajos. Teams guarda todos los mensajes no enviados para chats existentes (hasta 24 horas) y los envía tan pronto como vuelva a estar en línea. Si está desconectado durante más de 24 horas, Teams le permite volver a enviar o eliminar mensajes no enviados. Estamos trabajando para agregar esta funcionalidad a nuevos chats y actualizaremos esta documentación cuando esté disponible.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)