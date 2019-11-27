---
title: Configuración de red de las características de voz en la nube en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga más información sobre la configuración de red que debe configurar para el enrutamiento basado en la ubicación para el enrutamiento directo y los servicios de emergencia mejorados.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74cf743d41f37cca2b8df4f25cc8f5328db6d776
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615890"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configuración de red de las características de voz en la nube en Microsoft Teams

Obtenga información acerca de las regiones de red, sitios de red, subredes de red y direcciones IP de confianza. Estos términos y conceptos se usan en nuestra documentación de voz de nube para el [enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) y las [llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md). Si implementa estas características de nube en su organización, debe configurar las opciones de red para usarlas en Microsoft Teams.

En este artículo se ofrece información general sobre la configuración de red que es común para el enrutamiento basado en la ubicación y las llamadas de emergencia dinámicas. En función de la característica de voz de nube y de la capacidad de implementación, debe configurar algunas o todas estas opciones. Para conocer los pasos sobre cómo configurar estas opciones, vea [administrar la topología de red para las características en la nube de Teams](manage-your-network-topology.md).

> [!NOTE]
> En los temas de configuración de esa característica se describen todos los requisitos específicos de la característica para la configuración de red.

## <a name="network-region"></a>Región de red

Una región de red incluye una colección de sitios de red. Interconecta varias partes de una red en varias áreas geográficas. Por ejemplo, si tu organización tiene muchos sitios ubicados en India, puedes elegir designar "India" como región de red. Cada sitio de red debe estar asociado a una región de red.

Las mismas regiones de red se comparten con el enrutamiento basado en la ubicación para el enrutamiento directo y los servicios de emergencia mejorados. Si ya ha creado regiones de red para una característica, no tiene que crear regiones de red nuevas para la otra característica.

## <a name="network-site"></a>Sitio de red

Un sitio de red representa una ubicación en la que su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Los sitios de red se definen como una colección de subredes IP. Cada sitio de red debe estar asociado a una región de red.

También puede usar sitios de red para habilitar y configurar llamadas de emergencia.

## <a name="network-subnet"></a>Subred de red

Cada subred debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina en función de la subred de la red y el sitio de red asociado. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios con la misma subred.

La información de subred se usa para determinar el sitio de red en el que se encuentra un extremo cuando se inicia una nueva sesión. Cuando se conoce la ubicación de cada una de las partes de una sesión, la característica de voz en la nube puede aplicar esa información para determinar cómo controlar la configuración o el enrutamiento de las llamadas.

Para cada sitio de red, trabaje con su administrador de red para determinar qué subredes IP están asignadas a cada sitio de red. Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, que normalmente trabaja en Detroit, viaja a la oficina de Nueva York para la formación, enciende su equipo y se conecta a la red, su equipo obtendrá una dirección IP en uno de los cuatro intervalos que se asignan a Nueva York, por ejemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Dirección IP fiable

Las direcciones IP de confianza son las direcciones IP externas de Internet de la red empresarial. Determinan si el extremo del usuario está dentro de la red corporativa antes de comprobar si hay una coincidencia con un sitio específico.

Si la dirección IP externa del usuario coincide con una dirección IP de la lista de direcciones IP fiables, la característica de voz en la nube realiza comprobaciones para determinar la subred interna en la que se encuentra el punto final del usuario. Se puede establecer una coincidencia con las direcciones IP IPv4 o IPv6, y depende del formato del paquete IP que se envía a la configuración de red. (Si una dirección IP pública tiene IPv4 e IPv6, debe agregar ambas como direcciones IP de confianza).

Si la dirección IP externa del usuario no coincide con una dirección IP que se encuentra en la lista de direcciones IP fiables, el punto de conexión se clasifica como si estuviera en una ubicación desconocida.
