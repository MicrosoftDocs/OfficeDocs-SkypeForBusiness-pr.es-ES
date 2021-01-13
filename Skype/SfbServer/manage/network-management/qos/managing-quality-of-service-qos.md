---
title: Administración de calidad de servicio (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeo.
ms.openlocfilehash: 77fae69a6ceeaf65f80dd38e78e42e186786c4ed
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814160"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Administración de la calidad de servicio (QoS) en Skype Empresarial Server


La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en redes donde el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.


> [!NOTE]  
> Como regla general, la calidad de servicio se aplica solamente a las sesiones de comunicación de la red interna. Al implementar QoS, debe configurar los servidores y enrutadores para que admitan el marcado de paquetes, pero de una manera especial. No puede dar por sentado que la calidad de servicio se admitirá en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que QoS se configurará de la misma manera que configuró el servicio en la red.

Skype Empresarial Server no requiere calidad de servicio; si actualmente no usa QoS, no es necesario instalar el servicio antes de instalar Skype Empresarial Server. Si experimenta una cantidad considerable de pérdida de paquetes en la red, la forma recomendada de solucionar este problema es agregar ancho de banda adicional. Si no es posible agregar más ancho de banda, es posible que desee implementar la calidad de servicio en su lugar.

Skype Empresarial Server ofrece compatibilidad completa con la calidad de servicio: esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype Empresarial Server en su infraestructura de red existente. Para ello, es necesario realizar las siguientes tareas:

  - [Habilitar QoS para dispositivos que no se basan en Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype Empresarial Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos DSCP usados por estos dispositivos.

  - [Configurar intervalos de puertos y una directiva de calidad](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)de servicio para los servidores de conferencia, aplicación y mediación. Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Con Skype Empresarial Server no habilita ni deshabilita calidad de servicio estableciendo, por ejemplo, un valor de propiedad en True o False. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos, y al crear y aplicar luego una directiva de grupo. Si más adelante decide no usar QoS, para "deshabilitar" la calidad de servicio, simplemente puede quitar los objetos de directiva de grupo adecuados.

  - [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales.](configuring-port-ranges-for-your-edge-servers.md) Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de calidad de servicio solo debe realizarse para el lado interno de los servidores perimetrales. Esto se debe a que la calidad de servicio está diseñada para su uso en la red interna y no en Internet.

- [Configurar intervalos de puertos y una directiva de calidad](configuring-port-ranges-for-your-skype-clients.md)  de servicio para sus clientes en Skype Empresarial Server  Estos intervalos de puertos solo se aplican a los equipos cliente y normalmente son diferentes de los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype Empresarial Server no admite QoS para sistemas operativos Windows distintos de Windows 10.


