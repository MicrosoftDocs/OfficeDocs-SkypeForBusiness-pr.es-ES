---
title: 'Lync Server 2013: Implementar servidores de mediación y definir servidores del mismo nivel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La carga de trabajo de telefonía empresarial, las conferencias de acceso telefónico local y las aplicaciones de voz avanzadas para empresas (aplicación de grupo de respuesta, aplicación de Parque de llamadas, control de admisión de llamadas (CAC), etc.) están disponibles en los grupos de aplicaciones para el usuario. Con Lync Server 2013, la funcionalidad del servidor de mediación está integrada en el servidor front-end. Ya no es necesario un servidor de mediación independiente independiente. Los grupos de aplicaciones para el usuario se pueden comunicar directamente con las puertas de enlace compatibles (una puerta de enlace de red de telefonía pública conmutada (RTC) o una IP-PBX), lo que elimina la necesidad de un servidor de mediación para funcionar como intermediario.

La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet. Para conectar su infraestructura de voz empresarial con su proveedor de troncal de SIP, se debe implementar un servidor de mediación independiente.

La conexión entre Lync Server (el componente de servidor de mediación en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica denominada *troncal*. En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco de SIP.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir un servidor de mediación en el generador de topología en Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definir una puerta de enlace en el generador de topología de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definir más troncos en el generador de topología en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Secciones relacionadas

[Configurar una conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

