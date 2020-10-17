---
title: 'Lync Server 2013: seguridad de datos de emparejamiento de grupo de servidores front-end'
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
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500727"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Seguridad de datos de emparejamiento de grupo de servidores front-end en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-07_

El servicio de copia de seguridad es un mecanismo de replicación de datos que se incluye en Lync Server 2013 que transfiere datos de usuario y contenido de conferencia entre dos grupos de servidores front-end de forma continua en dos centros de datos para fines de recuperación ante desastres. Los datos de usuario contienen los URI de SIP, además de listas de contactos y configuraciones. El contenido de la Conferencia incluye las cargas de Microsoft PowerPoint 2010, así como las pizarras usadas en las conferencias. En el grupo de servidores de origen, los datos de usuario y el contenido de las conferencias se exportan desde el almacenamiento local, se comprimen y se transfieren al grupo de servidores de destino, donde se descomprimirán e importarán al almacenamiento local. El Servicio de copia de seguridad supone que el vínculo de comunicaciones entre los dos centros de datos está dentro de la red corporativa protegida de Internet. No cifra los datos transferidos entre los centros de datos, ni se encapsulan de forma nativa dentro de un protocolo seguro, como HTTPS. Por tanto, cabe la posibilidad de que personal interno desde la red corporativa lance un ataque de tipo "man-in-the-middle" (MitM, o intermediario).

<div>

## <a name="evaluating-security-risks"></a>Evaluación de los riesgos de seguridad

Cualquier empresa que implemente Lync Server 2013 en varios centros de datos y use la característica de recuperación ante desastres debe asegurarse de que el tráfico del centro de datos cruzado esté protegido por su intranet corporativa. Las empresas preocupadas por la protección de ataques internos deben proteger los vínculos de comunicación entre los centros de datos.

Por regla general, se supone que los centros de datos de una empresa están protegidos detrás de la intranet corporativa. Existen otros muchos tipos de datos confidenciales de la empresa que se transfieren entre estos centros de datos. La infraestructura de TI de la empresa corre un grave riesgo si no protege estos vínculos de comunicación entre centros de datos.

Si bien el riesgo de ataques de tipo "man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico a Internet. Concretamente, los datos de usuario que expone el Servicio de copia de seguridad (como los URI de SIP) suelen estar disponibles para todos los empleados de la compañía a través de otros medios, como la libreta de direcciones global de Exchange u otros programas informáticos de directorios. Por ello, el principal objetivo deber ser proteger la WAN entre los dos centros de datos cuando se usa el Servicio de copia de seguridad para copiar datos entre los dos grupos de servidores emparejados.

</div>

<div>

## <a name="mitigating-security-risks"></a>Reducción de los riesgos de seguridad

Hay muchas formas de mejorar la protección de la seguridad para el tráfico del servicio de copia de seguridad, desde restringir el acceso a los centros de datos hasta asegurar el transporte WAN entre los dos centros de datos. En la mayoría de los casos, las empresas que implementan Lync Server 2013 podrían tener la infraestructura de seguridad necesaria en su ubicación. Para las empresas que buscan orientación, Microsoft proporciona una solución como un ejemplo de cómo crear una infraestructura de ti segura. Sin embargo, esto no implica que sea la única solución, ni implica que es la mejor solución para Lync Server. Se recomienda que los clientes empresariales elijan la solución que se ajuste a sus necesidades específicas, en función de los requisitos y la infraestructura de seguridad de ti. La solución de Microsoft de ejemplo emplea IPSec y la Directiva de grupo para el aislamiento de servidor y dominio. Para obtener más información, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) . Para preguntas y comentarios, póngase en contacto con secwish@microsoft.com.

Otra posible solución es usar IPSec solo para ayudar a proteger los datos enviados por el propio servicio de copia de seguridad. Si elige este método, debe configurar las reglas IPSec para el protocolo SMB para los siguientes servidores, donde el grupo A y el grupo B son dos grupos de servidores front-end emparejados.

  - El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos que usa el grupo B.

  - El servicio SMB (TCP/445) de cada servidor front-end del grupo de servidores B al almacén de archivos que usa el grupo A.

<div>


> [!WARNING]  
> IPsec no pretende ser un sustituto de la seguridad de nivel de aplicación, como SSL/TLS. Una de las ventajas de usar IPsec es que puede proporcionar seguridad de tráfico de red para las aplicaciones existentes sin tener que cambiarlas. Las empresas que quieran proteger el transporte entre los dos centros de datos deben consultar a sus respectivos proveedores de hardware de red sobre formas de configurar conexiones WAN seguras mediante el equipo del proveedor.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

