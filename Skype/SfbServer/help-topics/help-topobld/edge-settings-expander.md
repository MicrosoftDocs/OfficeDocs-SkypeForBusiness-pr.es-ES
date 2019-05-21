---
title: Expansor de configuración perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Dispone de las siguientes secciones para editar la configuración de un servidor perimetral o un grupo de servidores perimetrales existente:'
ms.openlocfilehash: 307a861814a8e05065c70299b5ef2a82c20c8c42
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282534"
---
# <a name="edge-settings-expander"></a>Expansor de configuración perimetral

Dispone de las siguientes secciones para editar la configuración de un servidor perimetral o un grupo de servidores perimetrales existente:

- Configuración general

- Configuración de la selección de próximo salto

- Configuración del servidor perimetral



## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) de grupo interno del grupo de servidores perimetrales. Edite el FQDN del grupo de servidores para cambiar este parámetro.

Active la casilla **Habilitar Federación para este grupo perimetral (puerto 5061)** si va a configurar la Federación con un socio de confianza de lync Server 2013, Microsoft lync Server 2010 o Microsoft Office Communications Server 2007 R2.

Seleccione **Habilitar la federación XMPP para este grupo de servidores perimetrales** para habilitar la federación XMPP.

Indique el número de puerto del **Puerto interno de replicación de configuración (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Configuración de la selección de próximo salto

Para definir o modificar el **Grupo de servidores del próximo salto** que van a usar los servidores perimetrales para comunicarse con la infraestructura interna, seleccione un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end de la lista desplegable. Solo los directores o los clientes front-end que se hayan configurado en el generador de topología aparecerán para la selección.

## <a name="edge-server-configuration"></a>Configuración del servidor perimetral

Para modificar o especificar los parámetros de **Configuración externa** de los servidores perimetrales, antes necesitará determinar si va a usar direcciones IP diferentes para el acceso SIP, la conferencia web y el servicio de audio/vídeo.

Si tiene previsto usar direcciones IP distintas para cada uno de ellos, active la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. Cada servicio necesita tener el registro del host DNS (A) pertinente creado para ello.

En cada uno de los servicios externos, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, en **Acceso SIP** puede usar sip.contoso.com con el puerto asociado 5061.

> [!IMPORTANT]
> Si selecciona FQDN diferentes para cada uno de los servicios externos, cada servicio necesita tener asociado un valor de puerto exclusivo. SIP se encuentra de forma predeterminada en el puerto 5061/TLS, el servicio perimetral de conferencia web se encuentra en el puerto 444/TLS y el servidor de conferencia de audio y vídeo, en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQFN y direcciones IP o puertos diferentes, necesitará actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desactive la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. Luego, puede editar los valores del puerto y el nombre de dominio completo de **Acceso SIP** si es necesario.

> [!IMPORTANT]
> Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, necesita actualizar todos los demás servicios que dependan de los valores configurados inicialmente.

## <a name="see-also"></a>Vea también

Para más detalles sobre cómo definir y configurar las opciones de los servicios perimetrales, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


