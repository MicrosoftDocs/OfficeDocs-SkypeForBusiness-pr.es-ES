---
title: Expansor de configuración perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar la configuración de un grupo de servidores perimetrales de uno o varios servidores existentes, le presentamos las secciones siguientes:'
ms.openlocfilehash: cc8e0094a601faaf89c6a932172d5b6cb3522f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822440"
---
# <a name="edge-settings-expander"></a>Expansor de configuración perimetral

Para editar la configuración de un grupo de servidores perimetrales de uno o varios servidores existentes, le presentamos las secciones siguientes:

- Configuración general

- Configuración de la selección de próximo salto

- Configuración del servidor perimetral


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de servidores internos del grupo de servidores perimetrales. Edite el FQDN del grupo de servidores para cambiar este parámetro.

Active la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** si va a configurar la federación con un servidor de Skype Empresarial Server 2015.

Especifique el número de puerto para el **Puerto de replicación de configuración interna (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Configuración de la selección de próximo salto

Para establecer o  modificar el grupo de servidores del próximo salto que usarán los servidores perimetrales para comunicarse con la infraestructura interna, seleccione un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end en el cuadro de lista desplegable. Solo se seleccionarán los directores o front-ends que se hayan configurado en el Generador de topologías.

## <a name="edge-server-configuration"></a>Configuración del servidor perimetral

Para editar o especificar los parámetros de la **Configuración externa** de los servidores perimetrales, primero debe determinar si utilizará direcciones IP diferentes para el acceso SIP, la conferencia web y el servicio de audio/vídeo.

Si tiene previsto utilizar direcciones IP distintas para cada uno, marque la casilla de verificación **Habilitar FQDN y direcciones IP distintos para conferencia web y A/V**. Cada servicio debe tener el registro (A) DNS creado para ello.

En cada uno de los servicios de tipo externo, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, para **Acceso SIP** puede usar sip.contoso.com con un puerto asociado de 5061.

> [!IMPORTANT]
> Si selecciona FQDN diferentes para cada uno de los servicios externos, cada servicio debe tener asociado un valor de puerto exclusivo. De forma predeterminada, el SIP está en el puerto 5061/TLS, el servicio perimetral de conferencia web está en el puerto 444/TLS y el servidor de conferencia A/V está en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de nombres de dominio completo y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desmarque la casilla de verificación **Habilitar FQDN y direcciones IP diferentes para conferencia web y A/V**. A continuación, si es necesario, puede editar los valores de puerto y FQDN del grupo de servidores de **Acceso SIP**.

> [!IMPORTANT]
> Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

## <a name="see-also"></a>Vea también

Para obtener más información sobre cómo definir y configurar las opciones de los servicios de servidores perimetrales, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


