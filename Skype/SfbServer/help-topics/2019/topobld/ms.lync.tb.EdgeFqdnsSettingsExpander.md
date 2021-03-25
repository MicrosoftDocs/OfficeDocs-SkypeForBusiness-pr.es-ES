---
title: Expansor de configuración de FQDN del servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar o especificar la configuración externa de los servidores perimetrales, primero debe determinar si usará direcciones IP independientes para el acceso al Protocolo de inicio de sesión (SIP), el servicio perimetral de conferencia web y el servicio perimetral de audio y vídeo.
ms.openlocfilehash: 830a4ad2b18592e209080f86be648ede4dc736b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118659"
---
# <a name="edge-server-fqdns-settings-expander"></a>Expansor de configuración de FQDN del servidor perimetral

Para editar  o especificar la configuración externa de los servidores perimetrales, primero debe determinar si usará direcciones IP independientes para el acceso al Protocolo de inicio de sesión (SIP), el servicio perimetral de conferencia web y el servicio perimetral de audio y vídeo.

Si tiene previsto usar direcciones IP diferentes para cada uno, seleccione la casilla **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**. Cada servicio debe tener su propio registro host (A) de DNS creado para ello.

En cada uno de los servicios de tipo externo, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, para **Acceso SIP**, puede usar sip.contoso.com con un puerto asociado de 5061.

> [!IMPORTANT]
> Si selecciona nombres de dominio completos diferentes para cada uno de los servicios externos, cada servicio debe tener asociado un valor de puerto exclusivo. De forma predeterminada, SIP se encuentra en el puerto 5601/TLS, el servicio perimetral de conferencia web se encuentra en el puerto 444/TLS y el servidor perimetral de conferencia de audio y vídeo se encuentra en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de nombres de dominio completo y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desactive la casilla **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**. A continuación, puede editar los valores del puerto y el nombre de dominio completo de **Acceso SIP** si es necesario.

> [!IMPORTANT]
> Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

Para obtener más información sobre cómo definir y configurar la configuración de los servicios perimetrales, vea [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).