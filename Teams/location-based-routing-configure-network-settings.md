---
title: 'Configurar la configuración de red: enrutamiento basado en la ubicación'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y configurar regiones, sitios y subredes de red para el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141283"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configuración de red de enrutamiento basado en la ubicación

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Si aún no lo ha hecho, lea [planificar el enrutamiento basado en la ubicación para que el enrutamiento directo](location-based-routing-plan.md) Revise otros pasos que debe realizar antes de configurar la configuración de red para el enrutamiento basado en la ubicación.

En este artículo se describe cómo configurar las opciones de red para el enrutamiento basado en la ubicación. Después de implementar el enrutamiento directo de un sistema telefónico en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.

## <a name="define-network-regions"></a>Definir regiones de red

Una región de red contiene una colección de sitios de red y se conecta a varias partes de una red en varias áreas geográficas. Para conocer los pasos sobre cómo configurar regiones de red, vaya a [administrar la topología de red para las características en la nube de Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definir sitios de red

Un sitio de red representa una ubicación en la que su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Debe asociar cada sitio de red de su topología a una región de red. Para conocer los pasos sobre cómo configurar sitios de red, vea [administrar la topología de red para las características en la nube de Teams](manage-your-network-topology.md).

Un procedimiento recomendado para el enrutamiento basado en la ubicación es crear un sitio independiente para cada ubicación que tenga conectividad RTC exclusiva. Puede crear un sitio habilitado para el enrutamiento basado en la ubicación o un sitio que no esté habilitado para el enrutamiento basado en la ubicación. Por ejemplo, es posible que desee crear un sitio que no esté habilitado para el enrutamiento basado en la ubicación para permitir que los usuarios que tengan habilitado el enrutamiento basado en la ubicación realicen llamadas RTC cuando se muevan a ese sitio.

## <a name="define-network-subnets"></a>Definir subredes de red

Cada subred debe estar asociada a un sitio de red específico. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred. Para conocer los pasos sobre cómo configurar subredes de red, vaya a [administrar la topología de red para las características en la nube de Teams](manage-your-network-topology.md).

Para el enrutamiento basado en la ubicación, las subredes IP en la ubicación en la que los puntos de conexión de los equipos se pueden conectar a la red deben definirse y asociarse a una red definida para exigir omisión de pago. Esta asociación de subredes permite que el enrutamiento basado en la ubicación Ubique los puntos de conexión geográficamente para determinar si se debe permitir una llamada RTC determinada. Se admiten subredes IPv6 e IPv4. Al determinar si un punto de conexión de Teams se encuentra en un sitio, el enrutamiento basado en la ubicación comprueba primero si existe una dirección IPv6. Si no hay ninguna dirección IPv6, el enrutamiento basado en la ubicación comprueba la existencia de una dirección IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir direcciones IP fiables (subredes externas)

Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el extremo del usuario está dentro de la red corporativa. Para conocer los pasos sobre cómo configurar las direcciones IP de confianza, vaya a [administrar la topología de red para las características en la nube de Teams](manage-your-network-topology.md).

Si la dirección IP externa del usuario coincide con una dirección IP de la lista de direcciones IP fiables, las comprobaciones de enrutamiento basadas en la ubicación determinan la subred interna en la que se encuentra el punto final del usuario. Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP fiables, el extremo se clasifica como si fuera de una ubicación desconocida y cualquier llamada RTC a o de un usuario que tenga habilitado el enrutamiento basado en la ubicación está bloqueada.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Habilitar el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red de las características de voz en la nube en Teams](cloud-voice-network-settings.md)
