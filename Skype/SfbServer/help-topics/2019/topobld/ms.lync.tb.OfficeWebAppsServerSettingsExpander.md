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
description: 'Las propiedades del servidor de Office Web Apps configurado se editan. Pueden modificarse las siguientes propiedades:'
ms.openlocfilehash: 0c5dbff11d6cc2f6b25f3afa77cfe12e1e511a8a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121083"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar configuración del servidor Office Web Apps

Las propiedades del servidor de Office Web Apps configurado se editan. Pueden modificarse las siguientes propiedades:

 **FQDN** de Office Web Apps Server: esta propiedad define el nombre de dominio completo de Office Web Apps Server y debe coincidir con un registro A o AAAA de host del sistema de nombres de dominio (DNS) (si se usa IPv6).

 Dirección URL de detección de **Office Web Apps Server:** el localizador uniforme de recursos (URL) para el acceso de cliente a Office Web Apps Server, es posible que deba editar esta dirección desde su valor predeterminado si el servidor se coloca en otra zona de red distinta de la red interna para la implementación.

Active la casilla **El Servidor de Office Web Apps está implementado como una red externa** si este servidor está implementado en su red perimetral o en otra zona de red que se encuentra fuera del firewall interno que separa la red perimetral, las redes de poca confianza e Internet de la implementación interna.

![Expansor de configuración de Office Web Apps](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Ver también

[Componentes y topologías para conferencias](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)