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
description: Obtenga información sobre las opciones de red que debe configurar para el enrutamiento Location-Based para enrutamiento directo y los servicios de emergencia mejorados.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834340"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configuración de red para las características de voz en la nube en Microsoft Teams

Obtenga información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza. Estos términos y conceptos se [](location-based-routing-plan.md) usan en la documentación de voz de la nube para el enrutamiento basado en la ubicación para el enrutamiento directo y las [llamadas de emergencia dinámicas.](configure-dynamic-emergency-calling.md) Si va a implementar estas características de nube en su organización, debe configurar la configuración de red para usarla con estas características en Microsoft Teams.

En este artículo se ofrece información general sobre la configuración de red habitual en el enrutamiento Location-Based dinámica y las llamadas de emergencia dinámicas. En función de la característica y la capacidad de voz en la nube que está implementando, configure algunas o todas estas opciones. Para ver los pasos para configurar estas opciones, consulte Administrar la topología de red para [las características de nube en Teams.](manage-your-network-topology.md)

> [!NOTE]
> Los requisitos específicos de una característica para la configuración de red se documentan en los temas de configuración para esa característica.

## <a name="network-region"></a>Región de red

Una región de red incluye una colección de sitios de red. Interconecta varias partes de una red a través de varias áreas geográficas. Por ejemplo, si su organización tiene muchos sitios ubicados en la India, puede elegir designar "India" como una región de red. Cada sitio de red debe estar asociado a una región de red.

Las mismas regiones de red las comparte Location-Based para enrutamiento directo y servicios de emergencia mejorados. Si ya ha creado regiones de red para una característica, no tiene que crear nuevas regiones de red para la otra característica.

## <a name="network-site"></a>Sitio de red

Un sitio de red representa una ubicación donde su organización tiene un lugar físico, como una oficina, un conjunto de edificios o un campus. Los sitios de red se definen como una colección de subredes IP. Cada sitio de red debe estar asociado a una región de red.

También puede usar sitios de red para habilitar y configurar las llamadas de emergencia.

## <a name="network-subnet"></a>Subred de red

Cada subred debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina según la subred de red y el sitio de red asociado. Puede asociar varias subredes con el mismo sitio de red, pero no puede asociar varios sitios a la misma subred.

La información de subred se usa para determinar el sitio de red en el que se encuentra un punto de conexión cuando se inicia una nueva sesión. Cuando se conoce la ubicación de cada una de las partes en una sesión, la característica de voz en la nube puede aplicar esa información para determinar cómo tratar la configuración de llamadas o el enrutamiento.

Para cada sitio de red, trabaje con el administrador de red para determinar qué subredes IP están asignadas a cada sitio de red. Por ejemplo, el sitio Nueva York de la región Norteamérica puede tener asignadas las siguientes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, que normalmente trabaja en Michigan, viaja a la oficina de Nueva York para recibir entrenamiento, enciende el equipo y se conecta a la red, su pc recibirá una dirección IP en uno de los cuatro rangos que están asignados a Nueva York, por ejemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Dirección IP de confianza

Las direcciones IP de confianza son las direcciones IP externas a Internet de la red empresarial. Determinan si el punto de conexión del usuario está dentro de la red corporativa antes de buscar una coincidencia de sitio específica.

Si la dirección IP externa del usuario coincide con una dirección IP que está en la lista de direcciones IP de confianza, la característica de voz en la nube comprueba la subred interna en la que se encuentra el punto de conexión del usuario. Se puede hacer una coincidencia con las direcciones IP IPv4 o IPv6 y depende del formato del paquete IP enviado a la configuración de red. (Si una dirección IP pública tiene IPv4 e IPv6, debe agregar ambas como direcciones IP de confianza).

Si la dirección IP externa del usuario no coincide con una dirección IP que está en la lista de direcciones IP de confianza, el punto de conexión se clasifica como una ubicación desconocida.
