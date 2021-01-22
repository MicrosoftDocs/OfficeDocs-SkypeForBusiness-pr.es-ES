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
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918546"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Solucionar problemas de conectividad con el cliente de Microsoft Teams
==============================================================

La mayoría de los problemas detectados con el cliente de Microsoft Teams se pueden rastrear hasta la conectividad de proxy o firewall. Comprobar que las direcciones URL, las direcciones IP y los puertos necesarios están abiertos en el firewall o proxy minimizará la solución de problemas innecesaria. Para obtener información específica sobre las URL e IP necesarias para Microsoft Teams, consulte el artículo de soporte técnico de direcciones IP y URL de [Microsoft 365 y Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) Los siguientes escenarios requieren que se abran puertos y DIRECCIONES URL específicas en el firewall.

- Autenticación

- Conectividad de cliente de Microsoft Teams

- Colaboración

- Elementos multimedia

- Servicios compartidos

- Integración de terceros

- Interoperabilidad de Skype Empresarial

- Interoperabilidad del cliente de Skype Empresarial

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Cuando Teams está sin conexión o con condiciones de ancho de banda bajo

La buena noticia es que Teams sigue ejecutándose incluso cuando trabaja sin conexión o con poco ancho de banda. Teams guarda todos los mensajes no enviados de los chats existentes (hasta 24 horas) y los envía en cuanto vuelve a estar en línea. Si está sin conexión durante más de 24 horas, Teams le permite elegir entre reenviar o eliminar los mensajes no enviados. Estamos trabajando para agregar esta funcionalidad a nuevos chats y actualizaremos esta documentación cuando esté disponible.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
