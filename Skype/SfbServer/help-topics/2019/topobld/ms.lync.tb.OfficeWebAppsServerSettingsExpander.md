---
title: Editar configuración del servidor Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede editar las propiedades del servidor Office Web Apps Server configurado. Pueden modificarse las siguientes propiedades:'
ms.openlocfilehash: 708687ddc191e11d4563445bd2146e928cda1fad
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726289"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar configuración del servidor Office Web Apps

Puede editar las propiedades del servidor Office Web Apps Server configurado. Pueden modificarse las siguientes propiedades:

 **Office FQDN** de Web Apps Server: esta propiedad define el nombre de dominio completo del servidor de aplicaciones web de Office y debe coincidir con un registro A o AAAA de host del sistema de nombres de dominio (DNS) (si se usa IPv6).

 Office URL de detección de Web **Apps Server:** el localizador uniforme de recursos (URL) para el acceso de cliente al servidor de aplicaciones web de Office, es posible que deba editar esta dirección desde su valor predeterminado si el servidor se coloca en otra zona de red distinta de la red interna para la implementación.

Active la casilla **El Servidor de Office Web Apps está implementado como una red externa** si este servidor está implementado en su red perimetral o en otra zona de red que se encuentra fuera del firewall interno que separa la red perimetral, las redes de poca confianza e Internet de la implementación interna.

![Office Expansor Configuración aplicaciones web.](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Vea también

[Componentes y topologías para conferencias](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)