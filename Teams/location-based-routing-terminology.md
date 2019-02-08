---
title: Terminología de enrutamiento basados en ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la terminología y los conceptos asociados con el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bcf4341d171f8b9faf8c11bbe8d85503cf2240b
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771003"
---
# <a name="location-based-routing-terminology"></a>Terminología de enrutamiento basados en ubicación

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

A continuación presentamos algunos términos y conceptos que se usan en toda la documentación de enrutamiento basado en la ubicación. Es una buena idea estar familiarizado con estos términos y conceptos antes de obtener más profunda en la documentación.

|Término  |Descripción  |
|---------|---------|
|Regiones de red     | Una región de red incluye una colección de sitios de red. Por ejemplo, si su organización tiene muchos sitios que se encuentra en la India, puede designar "India" como una región de red.        |
|Sitios de red    | Un sitio de red representa una ubicación donde la organización tiene una ubicación física, como una oficina, un conjunto de edificios o un campus. Sitios de red se definen como una colección de subredes IP. Es una práctica recomendada para el enrutamiento basado en la ubicación crear un sitio independiente para cada ubicación que tiene conectividad con RTC única.  Cada sitio de red debe asociarse con una región de red. Puede crear un sitio que está habilitado para enrutamiento basado en la ubicación o un sitio que no está habilitado para enrutamiento basado en la ubicación. Por ejemplo, es posible que desee crear un sitio que no está habilitado para que enrutamiento basados en ubicación permitir a los usuarios que están habilitados para que enrutamiento basados en ubicación realizar llamadas de RTC cuando desplazan a ese sitio. Tenga en cuenta que también se pueden usar los sitios de red para habilitar y configurar llamadas de emergencia.        |
|Subredes de red     |Subredes IP en la ubicación donde los extremos de los equipos pueden conectarse a la red deben ser definidas y asociadas a una red definida para aplicar el desvío de pago. Varias subredes pueden estar asociadas con el mismo sitio de red, pero no se pueden asociados con una misma subred varios sitios. Esta asociación de subredes permite enrutamiento basados en ubicación buscar los extremos geográficamente para determinar si se debe permitir una determinada llamada de RTC. Se admiten las subredes tanto IPv4 como IPv6. Al determinar si un extremo de los equipos está ubicado en un sitio, el enrutamiento basado en la ubicación comprueba primero para una dirección IPv6 coincidente. Si una dirección IPv6 no está presente, enrutamiento basados en ubicación comprueba una dirección IPv4. <br><br>Compatibilidad con IPv6 está en curso y estará disponible por disponibilidad General (GA) de enrutamiento basado en la ubicación.          |
|Direcciones IP externas de confianza    |Confianza direcciones IP externas son las direcciones IP externas de Internet de la red de la empresa. Determinan si el extremo del usuario está dentro de la red corporativa antes de comprobar una coincidencia de sitio específico. Si la dirección IP externa del usuario coincide con una dirección IP que se define en la lista de confianza, enrutamiento basados en ubicación comprueba para determinar la subred interna donde se encuentra extremo del usuario. Si la dirección IP externa del usuario no coincide con cualquier dirección IP que se define en la lista de confianza, el extremo se clasifica como está en una ubicación desconocida y se bloquean las llamadas RTC a o desde un usuario habilitado para enrutamiento basado en la ubicación.          |

### <a name="related-topics"></a>Temas relacionados
- [Planeación de enrutamiento basado en ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Establecer la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar el enrutamiento basado en ubicación para el enrutamiento directo](location-based-routing-enable.md)
