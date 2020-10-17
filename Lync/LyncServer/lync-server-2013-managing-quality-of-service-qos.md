---
title: 'Lync Server 2013: administración de la calidad de servicio (QoS)'
description: 'Lync Server 2013: administración de la calidad de servicio (QoS).'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0e84389cc030cd63fe04c46929bd981a074aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552726"
---
# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Administración de la calidad de servicio (QoS) en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en redes donde el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.

<div>


> [!NOTE]  
> Como regla general, la calidad de servicio se aplica solamente a las sesiones de comunicación de la red interna. Al implementar QoS, debe configurar los servidores y enrutadores para que admitan el marcado de paquetes, pero de una manera especial. No puede dar por sentado que la calidad de servicio se admitirá en Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no existe ninguna garantía de que QoS se configurará de la misma manera que configuró el servicio en la red.



</div>

Microsoft Lync Server 2013 no requiere calidad de servicio; Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Lync Server 2013. Si experimenta una cantidad considerable de pérdida de paquetes en la red, la forma recomendada para paliar este problema es agregar ancho de banda adicional. Si no es posible agregar más ancho de banda, puede que desee implementar la calidad de servicio en su lugar.

Lync Server 2013 ofrece total compatibilidad con la calidad de servicio: Esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Lync Server en su infraestructura de red existente. Para ello, es necesario realizar las siguientes tareas:

  - [Habilitación de QoS en Lync Server 2013 para dispositivos que no están basados en Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Lync Server para habilitar y deshabilitar la calidad de servicio para dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.

  - [Configuración de intervalos de puertos en Lync Server 2013 para los servidores de conferencia, aplicación y mediación](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Con Lync Server 2013 no puede habilitar o deshabilitar la calidad de servicio por, por ejemplo, estableciendo un valor de propiedad en true o en false. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos, y al crear y aplicar luego una directiva de grupo. Si más adelante decide no usar QoS, para "deshabilitar" la calidad de servicio, simplemente puede quitar los objetos de directiva de grupo adecuados.

  - [Configuración de intervalos de puertos para los servidores perimetrales en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.

  - [Configuración de intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores.

  - [Configurar una directiva de calidad de servicio en Lync Server 2013 para los servidores de conferencia, aplicación y mediación](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Estas directivas determinan los códigos DSCP que se aplican a diferentes tipos de paquetes.

  - [Configurar una directiva de calidad de servicio para los servidores perimetrales a/V en Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Esto solo debe realizarse para el lado interno de los servidores perimetrales. Esto se debe a que la calidad de servicio está diseñada para usarse en la red interna y no en Internet.

  - [Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que ejecutan Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Tenga en cuenta que Microsoft Lync Server 2013 no es compatible con QoS para otros sistemas operativos Windows, como Windows Vista o Windows XP.

  - [Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition en Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). De forma predeterminada, la QoS está habilitada para los dispositivos de Lync Phone Edition. Sin embargo, recomendamos cambiar el valor predeterminado de DSCP a fin de garantizar que todos los paquetes de audio de la organización usen el mismo código DSCP.

<div>


> [!NOTE]  
> Si usa Microsoft Windows Server 2012 o Windows Server 2012 R2, es posible que le interese el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar la calidad de servicio en esa plataforma. Para obtener más información, consulte red de cmdlets de calidad de servicio en Windows PowerShell en [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps) .



</div>

</div>

<span> </span>

</div>

</div>

</div>

