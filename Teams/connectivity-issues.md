---
title: Solucionar problemas de conectividad con el cliente de Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562169"
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