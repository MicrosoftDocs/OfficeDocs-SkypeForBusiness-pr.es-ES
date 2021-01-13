---
title: 'Configurar las opciones de red: enrutamiento basado en la ubicación'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y configurar regiones de red, sitios y subredes para el Location-Based de enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822950"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configuración de red de enrutamiento basado en la ubicación

Si aún no lo ha hecho, lea Planear el enrutamiento [Location-Based](location-based-routing-plan.md) para enrutamiento directo para revisar otros pasos que deberá realizar antes de configurar las opciones de red para el enrutamiento Location-Based cliente.

En este artículo se describe cómo configurar las opciones de red para Location-Based de distribución. Después de implementar el enrutamiento directo de sistema telefónico en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.

## <a name="define-network-regions"></a>Definir regiones de red

Una región de red contiene una colección de sitios de red e interconecta varias partes de una red en varias áreas geográficas. Para ver los pasos sobre cómo configurar las regiones de red, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)

## <a name="define-network-sites"></a>Definir sitios de red

Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Debe asociar cada sitio de red de la topología a una región de red. Para ver los pasos sobre cómo configurar sitios de red, consulte Administrar la topología de red para [las características de nube en Teams.](manage-your-network-topology.md)

Un procedimiento recomendado para Location-Based es crear un sitio independiente para cada ubicación que tenga conectividad RTC única. Puede crear un sitio habilitado para el enrutamiento de Location-Based electrónico o un sitio que no esté habilitado para el Location-Based grupo. Por ejemplo, es posible que desee crear un sitio que no esté habilitado para el enrutamiento de Location-Based para permitir que los usuarios habilitados para Location-Based Enrutamiento realicen llamadas RTC cuando se des recorrido a ese sitio.

## <a name="define-network-subnets"></a>Definir subredes de red

Cada subred debe estar asociada a un sitio de red específico. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred. Para ver los pasos sobre cómo configurar subredes de red, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)

Para Location-Based, las subredes IP en la ubicación donde los puntos de conexión de Teams pueden conectarse a la red deben estar definidas y asociadas a una red definida para exigir la omisión de pago. Esta asociación de subredes permite a Location-Based enrutamiento para localizar los puntos de conexión geográficamente con el fin de determinar si se debe permitir una llamada RTC determinada. Se admiten subredes IPv6 e IPv4. Al determinar si un punto de conexión de Teams se encuentra en un sitio, Location-Based enrutamiento comprueba primero si hay una dirección IPv6 que coincida. Si no hay una dirección IPv6, Location-Based enrutamiento comprueba si hay una dirección IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir direcciones IP de confianza (subredes externas)

Las direcciones IP de confianza son las direcciones IP externas a Internet de la red empresarial y se utilizan para determinar si el punto de conexión del usuario se encuentra dentro de la red corporativa. Para ver los pasos sobre cómo configurar direcciones IP de confianza, vaya a Administrar la topología de red [para las características de nube en Teams.](manage-your-network-topology.md)

Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, Location-Based Routing comprueba la subred interna en la que se encuentra el punto de conexión del usuario. Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida y se bloquean las llamadas RTC a un usuario habilitado para Location-Based Routing.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Habilitar Location-Based de enrutamiento directo.](location-based-routing-enable.md)

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)
