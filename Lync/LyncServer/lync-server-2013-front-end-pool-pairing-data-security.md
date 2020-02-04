---
title: 'Lync Server 2013: seguridad de datos en el emparejamiento de grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Seguridad de datos en el emparejamiento de grupos de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-07_

El servicio de copia de seguridad es un mecanismo de replicación de datos introducido en Lync Server 2013 que transfiere continuamente los datos de usuario y el contenido de conferencia entre dos grupos front-end de dos en dos centros de datos para fines de recuperación ante desastres. Los datos de usuario contienen URI del SIP del usuario, así como listas de contactos y configuración. El contenido en conferencia incluye las cargas de Microsoft PowerPoint 2010, así como las pizarras que se usan en las conferencias. Desde el grupo de origen, los datos del usuario y el contenido de la Conferencia se exportan desde el almacenamiento local, zip, transferido al grupo de destino, donde se descomprime y se importa al almacenamiento local. El servicio de copia de seguridad supone que el vínculo de comunicación entre los dos centros de datos se encuentra dentro de la red corporativa y que se protege de Internet. No cifra los datos transferidos entre los dos centros de datos ni se encapsula de forma nativa dentro de un protocolo seguro, como HTTPS. Por lo tanto, es posible que el ataque de hombre en el medio del personal interno dentro de la red corporativa.

<div>

## <a name="evaluating-security-risks"></a>Evaluación de los riesgos de seguridad

Cualquier empresa que implemente Lync Server 2013 en varios centros de datos y use la característica de recuperación de desastres debe garantizar que el tráfico del centro de datos cruzados esté protegido por su intranet corporativa. Las empresas que tengan que preocuparse por la protección interna de ataques deben proteger los vínculos de comunicación entre los centros de datos.

El supuesto de que los centros de datos de una empresa estén protegidos detrás de la intranet corporativa es estándar. Hay muchos otros tipos de datos confidenciales corporativos que se transfieren entre estos centros de datos. La infraestructura de TI de la empresa está en riesgo de ser arriesgada si estos vínculos del centro de datos cruzados no están protegidos.

Si bien el riesgo de ataques de tipo "Man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico en Internet. En concreto, los datos de usuario expuestos por el servicio de copia de seguridad (como URI de SIP) están generalmente disponibles para todos los empleados de la empresa a través de otros medios, como la libreta de direcciones global de Exchange u otro software de directorio. Por lo tanto, el foco debe estar en la seguridad de la WAN entre los dos centros de datos cuando se usa el servicio de copia de seguridad para copiar datos entre los dos pools emparejados.

</div>

<div>

## <a name="mitigating-security-risks"></a>Mitigar los riesgos de seguridad

Existen muchas maneras de mejorar la protección de la seguridad del tráfico del servicio de copia de seguridad, que abarca desde restringir el acceso a los centros de datos, a fin de asegurar el transporte WAN entre los dos centros de datos. En la mayoría de los casos, es posible que las empresas que implementan Lync Server 2013 ya dispongan de la infraestructura de seguridad necesaria. Para empresas que buscan orientación, Microsoft ofrece la solución como un ejemplo de cómo crear una infraestructura de ti segura. Sin embargo, esto no implica que sea la única solución, ni implica que es la solución preferida para Lync Server. Recomendamos que los clientes empresariales elijan la solución que se adapte a sus necesidades específicas, en función de la infraestructura y los requisitos de seguridad de ti. La solución de ejemplo de Microsoft emplea IPSec y la Directiva de grupo para el aislamiento de servidor y dominio. Para obtener más información [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544), consulte. Para obtener preguntas y comentarios, póngase en contacto con secwish@microsoft.com.

Otra posible solución consiste en usar IPsec solamente para que proteger los datos enviados por el propio servicio de copia de seguridad sea más fácil. Si eliges este método, necesitarás configurar las reglas IPsec del protocolo SMB para los siguientes servidores, donde los grupos A y B son dos grupos de servidores front-end emparejados.

  - El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos que usa el grupo B.

  - El servicio SMB (TCP/445) de cada servidor front-end del grupo B al almacén de archivos que usa el grupo A.

<div>


> [!WARNING]  
> IPsec no está pensado para reemplazar la seguridad de la aplicación, como SSL/TLS. Una ventaja de utilizar IPsec es que puede ofrecer seguridad de tráfico de red para las aplicaciones existentes sin necesidad de cambiarlas. Las empresas que, simplemente, quieren proteger el transporte entre los dos centros de datos necesitan consultar a sus respectivos proveedores de hardware de redes sobre las formas de configurar conexiones WAN seguras con los equipos del proveedor.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

