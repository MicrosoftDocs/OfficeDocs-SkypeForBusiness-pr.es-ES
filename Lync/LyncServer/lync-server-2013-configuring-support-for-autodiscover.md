---
title: 'Lync Server 2013: configuración de la compatibilidad con la detección automática'
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
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configuración de la compatibilidad con la detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-21_

El **servicio de detección automática** de servicios Web de Lync Server apareció en primer lugar en la actualización acumulativa de lync Server 2010:2011 de noviembre. Esta actualización viene acompañada de la versión inicial de clientes móviles de Lync. El servicio de detección automática expuso los servicios de movilidad, conocido como el servicio MCX.

El servicio de detección automática actúa como una única ubicación para que todos los clientes soliciten información sobre los servicios y las características disponibles, y cómo comunicarse con ellos, ya sea mediante un nombre de dominio completo o una referencia de localizador de recursos uniforme Web. Detección automática expone una serie de características y cada cliente realiza solicitudes basadas en las características que el cliente puede usar. Por ejemplo, un cliente de Lync 2013 de escritorio usará autodiscvoer para determinar los servicios web externos, pero no usará los servicios de movilidad (MCX). Para definir correctamente y habilitar a los clientes para que usen las características disponibles, se deben definir los escenarios que permiten a un cliente buscar y usar entradas de detección automática de forma eficaz. Para usar autodoscover, su implementación requiere que un proxy inverso publique los servicios Web de Lync Server, que los registros DNS están configurados para resolver consultas DNS para el servicio Detección automática de Lync Server y los servicios Web de Lync Server, y que los servicios de Certificate Server están correctamente configurados para tu escenario específico.

<div>


> [!TIP]  
> Para obtener información técnica sobre lo que hacen los elementos dentro de la solicitud o respuesta de detección automática, consulte <A href="lync-server-2013-understanding-autodiscover.md">Descripción de la detección automática en Lync Server 2013</A>.



</div>

La siguiente información y tablas definen, por ejemplo, qué configuraciones (si las hay) necesita implementar para proporcionar el uso efectivo y completo del servicio de detección automática. La información de los temas siguientes es específica de Microsoft Lync Server 2013. Si está buscando información sobre cómo planear la movilidad para Lync Server 2010, consulte [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113). Para implementar la movilidad de Lync Server 2010, consulte[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de DNS para la detección automática en Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configuración de certificados para la detección automática en Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configuración de un proxy inverso para detección automática en Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configuración de la detección automática en Lync Server 2013 para implementaciones híbridas](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

