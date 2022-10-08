---
title: 'Configurar las opciones de red: enrutamiento basado en ubicación'
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y configurar regiones, sitios y subredes de red para Location-Based Enrutamiento directo.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999335"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configuración de red de enrutamiento basado en la ubicación

En este artículo se describe cómo configurar las opciones de red para el enrutamiento de Location-Based. Si aún no lo ha hecho, lea [Planear Location-Based Enrutamiento para enrutamiento directo para](location-based-routing-plan.md) revisar otros pasos que deberá realizar antes de configurar la configuración de red.

Después de implementar el enrutamiento directo en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red.

## <a name="define-network-regions"></a>Definir regiones de red

Una región de red contiene una colección de sitios de red e interconecta varias partes de una red a través de varias áreas geográficas. Para conocer los pasos para configurar regiones de red, vaya a [Administrar la topología de red para las características de nube en Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definir sitios de red

Un sitio de red representa una ubicación en la que su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Debe asociar cada sitio de red de la topología con una región de red. Para conocer los pasos para configurar sitios de red, consulte [Administrar la topología de red para las características de nube en Teams](manage-your-network-topology.md).

Un procedimiento recomendado para el enrutamiento de Location-Based es crear un sitio independiente para cada ubicación que tenga conectividad única de red telefónica conmutada (RTC). Puede crear un sitio habilitado para Location-Based Enrutamiento o un sitio que no esté habilitado para Location-Based Enrutamiento. Por ejemplo, es posible que desee crear un sitio que no esté habilitado para Location-Based Enrutamiento para permitir que los usuarios habilitados para Location-Based Enrutamiento puedan realizar llamadas RTC cuando vayan de itinerancia a ese sitio.

## <a name="define-network-subnets"></a>Definir subredes de red

Cada subred debe estar asociada a un sitio de red específico. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios a la misma subred. Para conocer los pasos para configurar subredes de red, consulte  [Administrar la topología de red para las características de nube en Teams](manage-your-network-topology.md).

Para el enrutamiento Location-Based, las subredes IP situadas en la ubicación donde los puntos de conexión de Teams se pueden conectar a la red deben definirse y asociarse a una red definida para exigir la omisión de peaje. Esta asociación de subredes permite Location-Based enrutamiento para localizar geográficamente los puntos de conexión para determinar si se debe permitir una llamada RTC determinada. Se admiten subredes IPv6 e IPv4. Al determinar si un punto de conexión de Teams se encuentra en un sitio, Location-Based Enrutamiento comprueba primero si hay una dirección IPv6 coincidente. Si no hay una dirección IPv6, Location-Based Enrutamiento comprueba si hay una dirección IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir direcciones IP de confianza (subredes externas)

Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el punto de conexión del usuario se encuentra dentro de la red corporativa. Para conocer los pasos para configurar direcciones IP de confianza, consulte [Administrar la topología de red para las características de nube en Teams](manage-your-network-topology.md).

Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, Location-Based Enrutamiento comprueba para determinar la subred interna donde se encuentra el punto de conexión del usuario. Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida y las llamadas RTC a un usuario habilitado para Location-Based enrutamiento se bloquean.

## <a name="next-steps"></a>Pasos siguientes

Vaya a [Habilitar Location-Based enrutamiento para enrutamiento directo](location-based-routing-enable.md).

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)
