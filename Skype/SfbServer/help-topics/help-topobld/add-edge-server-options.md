---
title: Agregar opciones de servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Seleccione cada una de las características que quiera habilitar para el grupo de servidores perimetrales. El grupo de servidores perimetrales admite de forma predeterminada usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de características del grupo de servidores perimetrales:'
ms.openlocfilehash: 34a5079c5baf5457e93171c5a61d0b91ef8f27c7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820982"
---
# <a name="add-edge-server-options"></a>Agregar opciones de servidor perimetral

Seleccione cada una de las características que quiera habilitar para el grupo de servidores perimetrales. El grupo de servidores perimetrales admite de forma predeterminada usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de características del grupo de servidores perimetrales:

- Use un solo nombre de dominio completo (FQDN) y dirección IP para todos los servicios perimetrales, incluidos el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V. Si no selecciona la opción para usar un solo FQDN y dirección IP, necesitará especificar FQDN y dirección IP distintos para cada uno de estos tres servicios perimetrales como parte del proceso de implementación. Para más información sobre los servicios perimetrales, mire [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) en la documentación de planeación.

    > [!NOTE]
    > Si selecciona esta opción, necesita especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de puerto por defecto recomendada: 444 para el servicio perimetral de acceso, 8057 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Seleccionar esta opción puede ayudar a impedir posibles problemas de conectividad y a simplificar la configuración, ya que permite introducir un FQDN que se va a usar en los tres servicios.

- Compatibilidad con federación. Seleccione esta opción si desea admitir la comunicación entre usuarios internos y externos y usuarios de dominios de confianza externos a la organización, incluidos todos los usuarios de un proveedor de mensajería instantánea (MI) pública compatible. Si selecciona esta opción, necesitará configurar la compatibilidad para los dominios federados y proveedores de servicio de conectividad de MI concretos que desea que sean compatibles. Para más información sobre cómo configurar la compatibilidad para federación y otros tipos de acceso de usuarios externos, mire [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) en la documentación de implementación de servidores perimetrales.

    > [!NOTE]
    > Solamente se puede publicar externamente para federación un grupo front-end o servidor perimetral estándar en su organización. Todo el acceso de los usuarios federados, incluidos los usuarios de MI pública, pasa por el mismo grupo de servidores perimetrales o por un servidor perimetral único. Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

- Habilitar la federación XMPP. Seleccione esta opción si desea permitir la comunicación entre usuarios internos y socios XMPP de confianza.

La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para más detalles sobre cómo agregar servidores perimetrales a una topología existente, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidores perimetrales.


