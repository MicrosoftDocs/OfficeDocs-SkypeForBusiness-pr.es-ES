---
title: Configuración de red para características de voz en la nube
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre la configuración de red que debe configurar para Location-Based enrutamiento directo y servicios de emergencia mejorados.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97ddf7f6b7410e83a5e2257d7df6ae2ad27cb7f
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096287"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configuración de red para las características de voz en la nube en Microsoft Teams

Obtenga información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza. Estos términos y conceptos se usan en toda la documentación de voz de la nube para enrutamiento basado en ubicación [para](location-based-routing-plan.md) enrutamiento directo y [llamadas de emergencia dinámicas.](configure-dynamic-emergency-calling.md) Si va a implementar estas características de nube en su organización, debe configurar la configuración de red para su uso con estas características en Microsoft Teams.

En este artículo se ofrece información general sobre la configuración de red que son comunes a Location-Based enrutamiento y llamadas de emergencia dinámicas. En función de la característica y la capacidad de voz en la nube que implemente, puede configurar algunas o todas estas opciones de configuración. Para obtener pasos sobre cómo configurar estas opciones, vea Administrar la topología de red para las características de la nube [en Teams](manage-your-network-topology.md).

> [!NOTE]
> Los requisitos específicos de características para la configuración de red se documentan en los temas de configuración de esa característica.

## <a name="network-region"></a>Región de red

Una región de red incluye una colección de sitios de red. Interconecta varias partes de una red en varias áreas geográficas. Por ejemplo, si su organización tiene muchos sitios ubicados en india, puede elegir designar "India" como una región de red. Cada sitio de red debe estar asociado a una región de red.

Las mismas regiones de red se comparten Location-Based enrutamiento directo y servicios de emergencia mejorados. Si ya ha creado regiones de red para una característica, no tiene que crear nuevas regiones de red para la otra característica.

## <a name="network-site"></a>Sitio de red

Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Los sitios de red se definen como una colección de subredes IP. Cada sitio de red debe estar asociado a una región de red.

También puede usar sitios de red para habilitar y configurar las llamadas de emergencia.

## <a name="network-subnet"></a>Subred de red

Cada subred debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina en función de la subred de red y el sitio de red asociado. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred.

La información de subred se usa para determinar el sitio de red en el que se encuentra un punto de conexión cuando se inicia una nueva sesión. Cuando se conoce la ubicación de cada parte de una sesión, la característica de voz en la nube puede aplicar esa información para determinar cómo controlar la configuración de llamadas o el enrutamiento.

Para cada sitio de red, trabaje con el administrador de red para determinar qué subredes IP se asignan a cada sitio de red. Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, que suele trabajar en Detroit, viaja a la oficina de Nueva York para recibir aprendizaje, activa su equipo y se conecta a la red, su equipo recibirá una dirección IP en uno de los cuatro rangos asignados para Nueva York, por ejemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Dirección IP de confianza

Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial. Determinan si el punto de conexión del usuario está dentro de la red corporativa antes de comprobar si hay una coincidencia de sitio específica.

Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, la característica de voz de la nube comprueba la subred interna donde se encuentra el punto de conexión del usuario. Se puede hacer una coincidencia con direcciones IP IPv4 o IPv6 y depende del formato del paquete IP enviado a la configuración de red. (Si una dirección IP pública tiene IPv4 e IPv6, debe agregar ambas como direcciones IP de confianza).

Si la dirección IP externa del usuario no coincide con una dirección IP que está en la lista de direcciones IP de confianza, el punto de conexión se clasifica como en una ubicación desconocida.

> [!Important]
> Las búsquedas de configuración de red no son compatibles con implementaciones de servicio de proxy en la nube que modifican las direcciones IP de origen Teams clientes.
