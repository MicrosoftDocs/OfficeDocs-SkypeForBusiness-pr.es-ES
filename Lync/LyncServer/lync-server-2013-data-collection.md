---
title: 'Lync Server 2013: Recopilación de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df4f19df012dfeac7576cc5b39d749564a4350a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Recopilación de datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

En el software de comunicaciones Microsoft Lync Server 2013, puede ejecutar Microsoft Lync Server 2013, la herramienta de planeación sin documentar las direcciones IP existentes y propuestas y los nombres de dominio completos (FQDN) del servidor perimetral, pero es mucho más difícil de hacer por lo tanto, sin causar errores de configuración. Por ejemplo, si se necesita la coexistencia durante un período de tiempo, un error común es reutilizar FQDN de una implementación de perimetral existente para la implementación perimetral de Lync Server 2013. Al anotar las direcciones IP y los FQDN propuestos y existentes en una hoja de cálculo, tabla u otro formulario visual, ayuda a evitar problemas de configuración durante la instalación.

<div>


> [!WARNING]  
> Si ha usado versiones anteriores de la herramienta de planeación, es posible que haya usado la herramienta para crear su topología y el documento de topología exportado para usar en el generador de topología para publicar su topología. La capacidad para exportar la topología se ha eliminado de la herramienta de planificación. No se recomienda usar una versión anterior de la herramienta de planeación para crear un documento de topología para Lync Server 2013 y se producirán resultados inesperados.



</div>

Por lo tanto, el enfoque recomendado es usar la siguiente plantilla de recopilación de datos, que corresponde a la topología perimetral, para recopilar las diversas direcciones IP y FQDN que necesitará para especificar en la herramienta de planeación. Al documentar la configuración actual y propuesta, puede poner los valores en el contexto adecuado para su entorno de producción. Y tiene que pensar en cómo se configurará la coexistencia y características, como las direcciones URL simples, los recursos compartidos de archivos y el equilibrio de carga.

Para implementar correctamente Microsoft Lync Server 2013, debe comprender la interacción y la dependencia de los componentes individuales. Al recopilar datos de la infraestructura de servidor y de la red existente, y aplicar las instrucciones de planeación de estas secciones, puede integrar los componentes de Lync Server 2013 Edge Server en su infraestructura.

En la [elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md), hay tres arquitecturas principales con dos variantes, para un total de cinco escenarios de implementación posibles. Uno de estos escenarios será el punto de partida para la recopilación de datos. Las direcciones IP, los nombres de los servidores y los nombres de dominio son ejemplos que coinciden con los diagramas de certificado, Firewall y DNS correspondientes que detallan la información necesaria para una solución de planeación completa. Los diagramas y el rellenado de los valores de certificado, DNS y firewall requeridos son especialmente importantes en las comunicaciones entre equipos donde la administración de la entidad de certificación, la configuración de firewall y DNS está administrada por equipos que no son el equipo en el que planifica la implementación. Los diagramas proporcionan información sobre los componentes necesarios que se pueden usar para comunicar estos requisitos para la colaboración entre equipos.

Los diagramas proporcionados son intencionalmente genéricos, pero permiten la recopilación de toda la información pertinente que sería necesaria para la comunicación de los requisitos en un escenario de equipo cruzado en el que la creación y administración de certificados, servidores la implementación y la administración de servidores son gestionadas por distintos grupos. Disponer de la información necesaria para la configuración de redes, firewalls, puertos y protocolos, certificados y servidores es incalculable cuando la implementación de Lync Server está en curso.

**Servidor perimetral y grupo Edge**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d] (images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy inverso**

![cf63fc50-2D11-4334-afc8-2d664ba1b6bb] (images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2D11-4334-afc8-2d664ba1b6bb")

**Grupo de directores o directores**

![56ba29ff-1309-4d5d-bf5c-35372169e947] (images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

