---
title: 'Lync Server 2013: recopilación de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6ef9454912b2d421302d7e696350a6f83bc9fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Recopilación de datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

En el software de comunicaciones Microsoft Lync Server 2013, puede ejecutar Microsoft Lync Server 2013, la herramienta de planeación sin documentar las direcciones IP existentes y propuestas y los nombres de dominio completos (FQDN) del servidor perimetral, pero es mucho más difícil por lo tanto, sin causar errores de configuración. Por ejemplo, si se requiere la coexistencia durante un período de tiempo, un error común es reutilizar FQDN de una implementación perimetral existente para la implementación perimetral de Lync Server 2013. Si tiene las direcciones IP existentes y las direcciones IP propuestas, así como los FQDN en una misma hoja de cálculo, tabla u otra forma visual, le será más fácil evitar problemas de configuración durante la instalación.

<div>


> [!WARNING]  
> Si ha usado versiones anteriores de la herramienta de planeación, puede que haya usado la herramienta para crear la topología y el documento de topología exportado para su uso en el generador de topologías para publicar la topología. La capacidad para exportar la topología se ha quitado de la herramienta de planeación. No se recomienda usar una versión anterior de la herramienta de planeación para crear un documento de topología para Lync Server 2013 y se producirán resultados inesperados.



</div>

Por lo tanto, el enfoque recomendado es usar la siguiente plantilla de recopilación de datos, que corresponde a la topología perimetral, para recopilar los distintos FQDN y las direcciones IP que tendrá que especificar en la herramienta de planeación. Al documentar la configuración actual y propuesta, puede situar los valores en el contexto adecuado para su entorno de producción. Además, se verá obligado a pensar en cómo configurará la coexistencia y las nuevas características, como direcciones URL sencillas, recursos compartidos de archivos, y equilibrio de carga.

Para implementar correctamente Microsoft Lync Server 2013, debe comprender la interacción y la dependencia de cada uno de los componentes. Al recopilar datos de la infraestructura de red y servidor existente y aplicar la guía de planeación en estas secciones, puede integrar los componentes del servidor perimetral de Lync Server 2013 en su infraestructura.

En la [elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md), hay tres arquitecturas principales con dos variaciones, para un total de cinco escenarios de implementación posibles. Uno de estos será el punto de partida para su colección de datos. Las direcciones IP, nombres de servidores y nombres de dominio son ejemplos que coinciden con el certificado, firewall y diagramas DNS coincidentes que detallan la información necesaria para una completa solución de planeación. El valor de los diagramas y rellenar los valores del certificado, de DNS y de firewall requeridos es especialmente importante en las comunicaciones entre equipos, en las que la administración de la autoridad de certificación, de la configuración de firewall y de DNS es administrada por equipos distintos del que planea la implementación. Los diagramas proporcionan información sobre los componentes requeridos que pueden usarse para comunicar estos requisitos para la colaboración entre equipos.

Los diagramas proporcionados son genéricos intencionadamente, pero permiten recopilar todos los datos pertinentes que son necesarios para la comunicación de requisitos en un escenario de varios equipos, donde varios grupos se encargan de la red, los firewalls, la creación y administración de certificados, la implementación de servidores y la administración de servidores. Disponer de los detalles necesarios para la configuración de la red, los firewalls, los puertos y los protocolos, los certificados y los servidores es invaluable cuando la implementación de Lync Server está en curso.

**Servidor perimetral y grupo de servidores perimetrales**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Proxy inverso**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**Director o grupo de directores**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

