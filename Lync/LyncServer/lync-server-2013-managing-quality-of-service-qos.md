---
title: 'Lync Server 2013: administración de calidad de servicio (QoS)'
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
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Administración de calidad de servicio (QoS) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. La mayoría de las veces se usa en redes en las que el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio proporciona una forma para que los administradores asignen prioridades mayores a los paquetes datos de audio o vídeo. Al dar a estos paquetes una prioridad más alta, es probable que las comunicaciones de audio y vídeo se completen más rápido y con menos interrupciones, que sesiones de red en las que se incluyen tareas como las transferencias de archivos, la navegación por Internet o las copias de seguridad de la base de datos. Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o las copias de seguridad de la base de datos tienen una prioridad de "mejor esfuerzo".

<div>


> [!NOTE]  
> Como regla general, la calidad de servicio solo se aplica a las sesiones de comunicación de la red interna. Al implementar QoS, puede configurar los servidores y los enrutadores para que admitan la marcación de paquetes; sin embargo, estos dispositivos se configuran para admitir la marcación de paquetes de una manera determinada. No puede dar por sentado que la calidad de servicio será compatible en Internet o en otras redes. Incluso si la calidad es compatible con otras redes, no hay garantía de que QoS se configure de la misma manera en la que se configuró el servicio en la red.



</div>

Microsoft Lync Server 2013 no requiere calidad de servicio; Si actualmente no usa QoS, no es necesario que instale el servicio antes de instalar Lync Server 2013. Si experimenta una cantidad considerable de paquetes perdidos en su red, la forma recomendada para aliviar este problema es agregar ancho de banda adicional. Si no es posible agregar más ancho de banda, es posible que desee implementar la calidad de servicio en su lugar.

Lync Server 2013 ofrece compatibilidad total con la calidad de servicio: eso significa que las organizaciones que ya usan QoS pueden integrar fácilmente Lync Server en su infraestructura de red existente. Para ello, debe realizar las siguientes tareas:

  - [Habilitar QoS en Lync Server 2013 para dispositivos que no se basan en Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Lync Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.

  - [Configurar intervalos de puertos en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. Con Lync Server 2013 no se habilita ni deshabilita la calidad de servicio, por ejemplo, estableciendo un valor de propiedad en verdadero o falso. En su lugar, se habilita la calidad de servicio mediante la configuración de intervalos de puerto y la creación y aplicación de la Directiva de grupo. Si más tarde decide no usar QoS, puede "Deshabilitar" la calidad de servicio simplemente quitando los objetos de directiva de grupo apropiados.

  - [Configurar intervalos de puertos para los servidores perimetrales en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores.

  - [Configurar intervalos de puertos para los clientes de Microsoft Lync en Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Estos intervalos de puertos se aplican solo a los equipos cliente y normalmente no son los mismos que los intervalos de puertos configurados en los servidores.

  - [Configurar una directiva de calidad de servicio en Lync Server 2013 para sus servidores de conferencias, aplicaciones y mediación](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Estas directivas determinan los códigos DSCP que se aplican a tipos de paquetes diferentes.

  - [Configurar una directiva de calidad de servicio para los servidores perimetrales a/V en Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Esto solo se debe hacer para el lado interno de los servidores perimetrales. Esto se debe a que la calidad de servicio está diseñada para su uso en su red interna y no en Internet.

  - [Configurar directivas de calidad de servicio en Lync Server 2013 para clientes que funcionen en Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Tenga en cuenta que Microsoft Lync Server 2013 no es compatible con QoS para otros sistemas operativos de Windows, como Windows Vista o Windows XP.

  - [Configuración de la calidad de servicio en los dispositivos Microsoft Lync Phone Edition en Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). De forma predeterminada, QoS está habilitado para los dispositivos de Lync Phone Edition. Sin embargo, es posible que desee cambiar el valor predeterminado de DSCP para garantizar que todos los paquetes de audio de su organización usen el mismo código DSCP.

<div>


> [!NOTE]  
> Si está usando Microsoft Windows Server 2012 o Windows Server 2012 R2, es posible que esté interesado en el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar la calidad de servicio en esa plataforma. Para obtener más información, consulte cmdlets de calidad de servicio de red en [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Windows PowerShell en.



</div>

</div>

<span> </span>

</div>

</div>

</div>

