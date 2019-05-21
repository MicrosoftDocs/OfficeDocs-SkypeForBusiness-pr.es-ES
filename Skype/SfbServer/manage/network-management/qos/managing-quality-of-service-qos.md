---
title: Administración de calidad de servicio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia de usuario final óptima para las comunicaciones de audio y vídeo.
ms.openlocfilehash: fbc10c5e94706348b7e3f66687b4868a9feb44ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279406"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Administración de calidad de servicio (QoS) en Skype empresarial Server


Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. La mayoría de las veces se usa en redes en las que el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio proporciona una forma para que los administradores asignen prioridades mayores a los paquetes datos de audio o vídeo. Al dar a estos paquetes una prioridad más alta, es probable que las comunicaciones de audio y vídeo se completen más rápido y con menos interrupciones, que sesiones de red en las que se incluyen tareas como las transferencias de archivos, la navegación por Internet o las copias de seguridad de la base de datos. Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o las copias de seguridad de la base de datos tienen una prioridad de "mejor esfuerzo".


> [!NOTE]  
> Como regla general, la calidad de servicio solo se aplica a las sesiones de comunicación de la red interna. Al implementar QoS, puede configurar los servidores y los enrutadores para que admitan la marcación de paquetes; sin embargo, estos dispositivos se configuran para admitir la marcación de paquetes de una manera determinada. No puede dar por sentado que la calidad de servicio será compatible en Internet o en otras redes. Incluso si la calidad es compatible con otras redes, no hay garantía de que QoS se configure de la misma manera en la que se configuró el servicio en la red.

Skype empresarial Server no requiere calidad de servicio; Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Skype empresarial Server. Si experimenta una cantidad considerable de paquetes perdidos en su red, la forma recomendada para aliviar este problema es agregar ancho de banda adicional. Si no es posible agregar más ancho de banda, es posible que desee implementar la calidad de servicio en su lugar.

Skype empresarial Server ofrece compatibilidad total con la calidad de servicio: eso significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype empresarial Server en su infraestructura de red existente. Para ello, debe realizar las siguientes tareas:

  - [Habilitar QoS para dispositivos que no se basan en Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype empresarial Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.

  - [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencias, aplicaciones y mediación](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. Con Skype empresarial Server no habilita ni deshabilita la calidad de servicio, por ejemplo, estableciendo un valor de propiedad en verdadero o falso. En su lugar, se habilita la calidad de servicio mediante la configuración de intervalos de puerto y la creación y aplicación de la Directiva de grupo. Si más tarde decide no usar QoS, puede "Deshabilitar" la calidad de servicio simplemente quitando los objetos de directiva de grupo apropiados.

  - [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales](configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de calidad de servicio solo debe realizarse en el lado interno de los servidores perimetrales. Esto se debe a que la calidad de servicio está diseñada para su uso en su red interna y no en Internet.

- [Configuración de intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype empresarial Server](configuring-port-ranges-for-your-skype-clients.md)  Estos intervalos de puertos se aplican solo a los equipos cliente y suelen ser distintos de los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype empresarial Server no es compatible con QoS para sistemas operativos Windows que no sean Windows 10.


