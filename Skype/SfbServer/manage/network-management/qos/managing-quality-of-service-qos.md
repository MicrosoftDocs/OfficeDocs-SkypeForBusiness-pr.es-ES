---
title: Administración de la calidad de servicio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeos.
ms.openlocfilehash: b63655cabbce642c05530adb80b94e8bfd1c34b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913065"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Administración de la calidad del servicio (QoS) en Skype para Business Server


Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeos. QoS se usa con más frecuencia en las redes donde el ancho de banda es limitado: con un gran número de paquetes de red que compiten para una relativamente pequeña cantidad de ancho de banda disponible, calidad de servicio proporciona una forma para que los administradores asignar prioridades mayores a los paquetes llevar a cabo los datos de audio o vídeos. De forma que estos paquetes proporcionan una mayor prioridad, están probable que para llevar a cabo más rápidamente y con menos interrupciones, de sesiones de red con cosas como las transferencias de archivos, exploración web o las copias de seguridad de la base de datos comunicaciones de audio y vídeo. Esto es debido a que los paquetes de red utilizados para las transferencias de archivos o las copias de seguridad de la base de datos se les asigna una prioridad de "mejor esfuerzo".


> [!NOTE]  
> Como regla general, la calidad de servicio se aplica únicamente a las sesiones de comunicación en la red interna. Cuando se implementan QoS, configurar los servidores y los enrutadores para admitir marcado; de paquetes Sin embargo, configurar estos dispositivos para admitir el marcado de una manera determinada de paquetes. No se puede suponer que calidad de servicio se admitirá en Internet o en otras redes. Incluso si calidad si se admite el servicio en otras redes, no hay ninguna garantía de que será QoS había configurado del mismo modo que se ha configurado el servicio en la red.

Skype para Business Server no requiere la calidad de servicio; Si actualmente no utiliza QoS no es necesario instalar el servicio antes de instalar Skype para Business Server. Si experimenta una cantidad considerable de pérdida de paquetes en la red, el método recomendado para solucionar este problema es agregar el ancho de banda adicional. Si no es posible agregar más ancho de banda, es posible que desee implementar en su lugar la calidad de servicio.

Skype para Business Server ofrece compatibilidad total con la calidad de servicio: que significa que las organizaciones que ya está usando la QoS fácilmente pueden integrar Skype para Business Server en su infraestructura de red existente. Para ello debe realizar las siguientes tareas:

  - [Habilitar QoS para dispositivos que no están basados en Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype para Business Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no se puede usar el producto para modificar los códigos DSCP utilizados por estos dispositivos.

  - [Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. Con Skype para Business Server no habilitar o deshabilitar calidad de servicio, por ejemplo, establecer un valor de la propiedad en True o en False. En su lugar, habilite calidad de servicio mediante la configuración de los intervalos de puerto y, a continuación, crear y aplicar directiva de grupo. Si más adelante decide no usar QoS puede "Deshabilitar" calidad de servicio, basta con quitar los objetos de directiva de grupo adecuados.

  - [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales](configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. Configuración de una directiva de calidad de servicio sólo debe realizarse para el lado interno de los servidores perimetrales. Esto es debido a que la calidad de servicio está diseñada para su uso en la red interna y no en Internet.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype para Business Server](configuring-port-ranges-for-your-skype-clients.md)  Estos intervalos de puertos se aplican sólo a los equipos cliente y están normalmente diferentes de los intervalos de puerto configurados en sus servidores. Tenga en cuenta que Skype para Business Server no es compatible con QoS para sistemas operativos Windows que no sea Windows 10.


