---
title: Agregar opciones de servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 'Seleccione cada una de las funciones que desea habilitar para el grupo de servidores perimetrales. De forma predeterminada, el grupo de servidores perimetrales admite usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de función del grupo de servidores perimetrales:'
ms.openlocfilehash: 5efec8373c16266b05e17d20c6d26678c098e27d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122711"
---
# <a name="add-edge-server-options"></a>Agregar opciones de servidor perimetral

Seleccione cada una de las funciones que desea habilitar para el grupo de servidores perimetrales. De forma predeterminada, el grupo de servidores perimetrales admite usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de función del grupo de servidores perimetrales:

- Utilice un solo nombre de dominio completo (FQDN) y dirección IP para todos los servicios perimetrales, incluidos el servicio perimetral de acceso, servicio perimetral de conferencia web y servicio perimetral A/V. Si no selecciona la opción para utilizar un solo FQDN y dirección IP, deberá especificar unos FQDN y dirección IP distintos para cada uno de estos servicios perimetrales como parte del proceso de implementación. Para más información sobre los servicios perimetrales, consulte [Components Required for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access) en la documentación sobre planificación.

    > [!NOTE]
    > Si selecciona esta opción, debe especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de puerto por defecto recomendada: 444 para el servicio perimetral de acceso, 8057 para el servicio perimetral de conferencia web  y 443 para el servicio perimetral de A/V). La selección de esta opción puede ayudar a impedir posibles problemas de conectividad y a simplificar la configuración porque le permite introducir un FQDN que se utilizará en los tres servicios.

- Compatibilidad para federación. Seleccione esta opción si desea admitir la comunicación entre usuarios internos y externos y usuarios de dominios de confianza externos a la organización, incluidos todos los usuarios de un proveedor de mensajería instantánea (MI) pública compatible. Si selecciona esta opción, deberá configurar la compatibilidad para los dominios federados concretos y proveedores de servicio de conectividad MI que desea que sean compatibles. Para más información sobre cómo configurar la compatibilidad  para federación y otros tipos de acceso de usuarios externos, consulte [Configuring Support for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access) en la documentación sobre implementación de servidores perimetrales.

    > [!NOTE]
    > Solamente se puede publicar externamente para federación un grupo front-end o servidor perimetral estándar en su organización. Todo el acceso de los usuarios federados, incluidos los usuarios de MI pública, pasan por el mismo grupo de servidores perimetrales o servidor perimetral único. Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto se aplica incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres utiliza el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V.

- Habilitar la federación XMPP. Seleccione esta opción si desea admitir la comunicación entre usuarios internos y socios XMPP de confianza.

Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o después. Para obtener más información sobre cómo agregar servidores perimetrales a una topología ya creada, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) en la documentación sobre implementación de servidores perimetrales.