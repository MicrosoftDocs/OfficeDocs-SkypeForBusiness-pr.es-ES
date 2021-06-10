---
title: 'Configurar la configuración de red: enrutamiento basado en ubicación'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y configurar regiones de red, sitios y subredes para Location-Based enrutamiento directo.
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

Si aún no lo ha hecho, lea [Plan de enrutamiento Location-Based](location-based-routing-plan.md) para enrutamiento directo para revisar otros pasos que tendrá que seguir antes de configurar la configuración de red para Location-Based enrutamiento.

En este artículo se describe cómo configurar la configuración de red para Location-Based enrutamiento. Después de implementar Sistema telefónico enrutamiento directo en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.

## <a name="define-network-regions"></a>Definir regiones de red

Una región de red contiene una colección de sitios de red e interconecta varias partes de una red en varias áreas geográficas. Para obtener pasos sobre cómo configurar regiones de red, vaya a Administrar la topología de red para las características de la nube [en Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definir sitios de red

Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Debe asociar cada sitio de red de la topología con una región de red. Para obtener pasos sobre cómo configurar sitios de red, vea Administrar la topología de red para las características de nube [en Teams](manage-your-network-topology.md).

Un procedimiento recomendado para Location-Based enrutamiento es crear un sitio independiente para cada ubicación que tenga conectividad RTC única. Puede crear un sitio habilitado para Location-Based enrutamiento o un sitio que no esté habilitado para Location-Based enrutamiento. Por ejemplo, es posible que desee crear un sitio que no esté habilitado para el enrutamiento de Location-Based para permitir que los usuarios habilitados para el enrutamiento de Location-Based realicen llamadas RTC cuando se deslomen a ese sitio.

## <a name="define-network-subnets"></a>Definir subredes de red

Cada subred debe estar asociada a un sitio de red específico. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred. Para obtener pasos sobre cómo configurar subredes de red, vaya a Administrar la topología de red para las características de la [nube en Teams](manage-your-network-topology.md).

Para Location-Based enrutamiento, las subredes IP en la ubicación donde Teams puntos de conexión pueden conectarse a la red deben definirse y estar asociadas a una red definida para exigir la omisión de pago. Esta asociación de subredes permite a Location-Based enrutamiento localizar geográficamente los puntos de conexión para determinar si se debe permitir una llamada RTC determinada. Se admiten las subredes IPv6 e IPv4. Al determinar si un punto Teams de conexión se encuentra en un sitio, Location-Based enrutamiento primero comprueba si hay una dirección IPv6 que coincida. Si una dirección IPv6 no está presente, Location-Based enrutamiento busca una dirección IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir direcciones IP de confianza (subredes externas)

Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el punto de conexión del usuario está dentro de la red corporativa. Para ver los pasos sobre cómo configurar direcciones IP de confianza, vaya a Administrar la topología de red para las características de la [nube en Teams](manage-your-network-topology.md).

Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, Location-Based Enrutamiento comprueba para determinar la subred interna donde se encuentra el punto de conexión del usuario. Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida y las llamadas RTC a o desde un usuario habilitado para Location-Based Enrutamiento se bloquean.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Habilitar Location-Based enrutamiento directo.](location-based-routing-enable.md)

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)
