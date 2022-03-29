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
ms.openlocfilehash: 524a78f5a588b0a3a233385f7892624c46e5bac541f7e8a13f647e541b0ffbff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308959"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Solucionar problemas de conectividad con el cliente de Microsoft Teams

La mayoría de los problemas detectados con el cliente de Microsoft Teams podrían estar relacionados con la conectividad del proxy o el firewall. Compruebe que las direcciones IP, URL y los puertos necesarios están abiertos en el firewall o el proxy. De esta forma, evitará tener que resolver problemas innecesarios. Para obtener información específica sobre las direcciones IP y URL necesarias para Microsoft Teams, vea el artículo de soporte técnico [dirección IP y URL de Microsoft 365 y Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). Los escenarios siguientes requieren abrir determinados puertos y direcciones URL en el firewall.

- Autenticación

- Conectividad de cliente de Microsoft Teams

- Colaboración

- Elementos multimedia

- Servicios compartidos

- Integración de terceros

- Interoperabilidad de Skype Empresarial

- Interoperabilidad del cliente de Skype Empresarial

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Cuando Teams está sin conexión o en condiciones de ancho de banda bajo

La buena noticia es que Teams se seguirá ejecutando incluso cuando esté sin conexión o se esté ejecutando en condiciones de ancho de banda bajo. Teams guardará todos los mensajes no enviados para chats existentes (durante un máximo de 24 horas) y los enviará tan pronto como vuelva a estar en línea. Si está sin conexión durante más de 24 horas, Teams permite volver a enviar o eliminar mensajes no enviados. Estamos trabajando para agregar esta funcionalidad a nuevos chats y actualizaremos esta documentación cuando esté disponible.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)