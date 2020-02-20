---
title: 'Lync Server 2013: configuración de la compatibilidad con detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee85d984f0d60d4275972982e4ff65b380f0f9b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configuración de la compatibilidad con detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

El **servicio Detección automática** de servicios Web de Lync Server apareció por primera vez en la actualización acumulativa de lync Server 2010: noviembre de 2011. Esta actualización viene acompañada de la versión inicial de clientes móviles de Lync. El servicio Detección automática expuso los servicios de movilidad, conocido como el servicio MCX.

El servicio Detección automática actúa como una única ubicación para que todos los clientes soliciten información sobre los servicios y las características que están disponibles y cómo ponerse en contacto con los servicios, ya sea mediante un nombre de dominio completo o una referencia de localizador de recursos uniforme Web. La detección automática expone una serie de características y cada cliente realizará solicitudes basadas en las características que el cliente puede usar. Por ejemplo, un cliente de Lync 2013 de escritorio usará autodiscvoer para determinar los servicios web externos, pero no usará los servicios de movilidad (MCX). Para definir y habilitar correctamente a los clientes para que usen las características disponibles, se deben definir los escenarios que permiten a un cliente buscar y usar entradas de detección automática de manera eficaz. Para usar autodoscover, su implementación requiere que un proxy inverso publique los servicios Web de Lync Server, que los registros DNS están configurados para resolver consultas DNS para el servicio Detección automática de Lync Server y los servicios Web de Lync Server, y que los servicios de certificados están configurados correctamente para su escenario específico.

<div>


> [!TIP]  
> Para obtener información técnica sobre los elementos que se encuentran dentro de la solicitud o respuesta de detección automática, consulte <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.



</div>

La siguiente información y tablas definen, por escenario, qué configuraciones debe implementar (si las hay) para proporcionar el uso eficaz y completo del servicio de detección automática. La información de los siguientes temas es específica de Microsoft Lync Server 2013. Si está buscando instrucciones sobre cómo planear la movilidad para Lync Server 2010, consulte [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113). Para implementar Mobility para Lync Server 2010, consulte[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de DNS para la detección automática en Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configuración de certificados para la detección automática en Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configuración de un proxy inverso para detección automática en Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configuración de detección automática en Lync Server 2013 para implementaciones híbridas](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

