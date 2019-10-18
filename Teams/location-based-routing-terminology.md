---
title: Terminología de enrutamiento basado en la ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Aprenda terminología y conceptos relacionados con el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9c7a323bb252c254d7422c30251414742608529
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572016"
---
# <a name="location-based-routing-terminology"></a>Terminología de enrutamiento basado en la ubicación

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Estos son algunos términos y conceptos que se usan en toda la documentación de enrutamiento basado en la ubicación. Es buena idea estar familiarizado con estas condiciones y conceptos antes de que la documentación se vea más detallada.

|Término  |Descripción  |
|---------|---------|
|Regiones de red     | Una región de red incluye una colección de sitios de red. Por ejemplo, si tu organización tiene muchos sitios ubicados en India, puedes elegir designar "India" como región de red.        |
|Sitios de red    | Un sitio de red representa una ubicación en la que su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Los sitios de red se definen como una colección de subredes IP. Un procedimiento recomendado para el enrutamiento basado en la ubicación es crear un sitio independiente para cada ubicación que tenga conectividad RTC exclusiva.  Cada sitio de red debe estar asociado a una región de red. Puede crear un sitio habilitado para el enrutamiento basado en la ubicación o un sitio que no esté habilitado para el enrutamiento basado en la ubicación. Por ejemplo, es posible que desee crear un sitio que no esté habilitado para el enrutamiento basado en la ubicación para permitir que los usuarios que tengan habilitado el enrutamiento basado en la ubicación realicen llamadas RTC cuando se muevan a ese sitio. Tenga en cuenta que los sitios de red también pueden usarse para habilitar y configurar llamadas de emergencia.        |
|Subredes de red     |Las subredes IP en la ubicación en la que se pueden conectar los puntos de conexión de Teams a la red deben definirse y asociarse a una red definida para exigir omisión de pago. Varias subredes pueden estar asociadas al mismo sitio de red, pero es posible que varios sitios no estén asociados a una misma subred. Esta asociación de subredes permite que el enrutamiento basado en la ubicación Ubique los puntos de conexión geográficamente para determinar si se debe permitir una llamada RTC determinada. Se admiten subredes IPv6 e IPv4. Al determinar si un punto de conexión de Teams se encuentra en un sitio, el enrutamiento basado en la ubicación comprueba primero si existe una dirección IPv6. Si no hay ninguna dirección IPv6, el enrutamiento basado en la ubicación comprueba la existencia de una dirección IPv4. <br><br>
|Direcciones IP externas de confianza    |Las direcciones IP externas de confianza son las direcciones IP externas de Internet de la red empresarial. Determinan si el extremo del usuario está dentro de la red corporativa antes de comprobar si hay una coincidencia con un sitio específico. Si la IP externa del usuario coincide con una dirección IP definida en la lista de confianza, las comprobaciones de enrutamiento basadas en la ubicación determinarán la subred interna en la que se encuentra el extremo del usuario. Si la dirección IP externa del usuario no coincide con ninguna dirección IP definida en la lista de confianza, el extremo se clasifica como si fuera de una ubicación desconocida y cualquier llamada RTC a o de un usuario que tenga habilitado el enrutamiento basado en la ubicación está bloqueada.          |

### <a name="related-topics"></a>Temas relacionados
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Habilitar enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md)
