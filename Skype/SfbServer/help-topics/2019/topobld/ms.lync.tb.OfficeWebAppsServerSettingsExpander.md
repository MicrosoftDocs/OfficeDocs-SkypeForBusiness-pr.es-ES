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
description: 'Las propiedades del servidor de Office Web Apps configurado se modifican. Pueden modificarse las siguientes propiedades:'
ms.openlocfilehash: 97435749a5eb6aa818ff4bb49d7a9142f6834c1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829930"
---
# <a name="edit-office-web-apps-server-settings"></a>Editar configuración del servidor Office Web Apps

Las propiedades del servidor de Office Web Apps configurado se modifican. Pueden modificarse las siguientes propiedades:

 **FQDN** de Office Web Apps Server: esta propiedad define el nombre de dominio completo de Office Web Apps Server y debe coincidir con un registro A o AAAA (si se usa IPv6) del host del sistema de nombres de dominio (DNS).

 Dirección URL de detección de **Office Web Apps Server:** el localizador uniforme de recursos (URL) para el acceso de cliente a Office Web Apps Server, es posible que tenga que editar esta dirección desde su valor predeterminado si el servidor se coloca en otra zona de red que no sea la red interna de la implementación.

Active la casilla **El Servidor de Office Web Apps está implementado como una red externa** si este servidor está implementado en su red perimetral o en otra zona de red que se encuentra fuera del firewall interno que separa la red perimetral, las redes de poca confianza e Internet de la implementación interna.

![Expansor de configuración de Office Web Apps](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Vea también

[Componentes y topologías para conferencias](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
