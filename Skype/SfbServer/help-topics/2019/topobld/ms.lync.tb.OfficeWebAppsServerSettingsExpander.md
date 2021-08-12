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
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede editar las propiedades del servidor Office Web Apps Server configurado. Pueden modificarse las siguientes propiedades:'
ms.openlocfilehash: d5e791e8f405941c706c20e855b63a47113c68ca33c4233ccacbc7a35d445c90
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320792"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar configuración del servidor Office Web Apps

Puede editar las propiedades del servidor Office Web Apps Server configurado. Pueden modificarse las siguientes propiedades:

 **Office FQDN** de Web Apps Server: esta propiedad define el nombre de dominio completo del servidor de aplicaciones web de Office y debe coincidir con un registro A o AAAA de host del sistema de nombres de dominio (DNS) (si se usa IPv6).

 Office URL de detección de Web **Apps Server:** el localizador uniforme de recursos (URL) para el acceso de cliente al servidor de aplicaciones web de Office, es posible que deba editar esta dirección desde su valor predeterminado si el servidor se coloca en otra zona de red distinta de la red interna para la implementación.

Active la casilla **El Servidor de Office Web Apps está implementado como una red externa** si este servidor está implementado en su red perimetral o en otra zona de red que se encuentra fuera del firewall interno que separa la red perimetral, las redes de poca confianza e Internet de la implementación interna.

![Office Expansor de Configuración aplicaciones web](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Consulte también

[Componentes y topologías para conferencias](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)