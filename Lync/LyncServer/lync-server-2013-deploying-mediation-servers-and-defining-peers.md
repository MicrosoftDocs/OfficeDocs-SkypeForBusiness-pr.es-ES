---
title: 'Lync Server 2013: implementación de servidores de mediación y definición de homólogos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eca427f644d6f94ae7a52900b80320e2517ed2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Implementación de servidores de mediación y definición de pares en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Los grupos de servidores front-end disponen de la carga de trabajo de Enterprise Voice, la Conferencia de acceso telefónico local y las aplicaciones avanzadas de telefonía IP (aplicación de grupo de respuesta, aplicación de estacionamiento de llamadas, control de admisión de llamadas (CAC), etc.). Con Lync Server 2013, la funcionalidad del servidor de mediación está integrada en el servidor front-end. Un servidor de mediación independiente independiente ya no es necesario. Los grupos de servidores front-end se pueden comunicar directamente con puertas de enlace compatibles (una puerta de enlace de red telefónica conmutada (RTC) o una IP-PBX), lo que elimina la necesidad de que un servidor de mediación sirva como intermediario.

La única excepción es si configura un tronco SIP para conectarse a un controlador de borde de sesión para un proveedor de servicios de telefonía por Internet. Para conectar su infraestructura de telefonía IP empresarial a su proveedor de tronco SIP, se debe implementar un servidor de mediación independiente.

La conexión entre Lync Server (el componente del servidor de mediación en un grupo de servidores front-end o un servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica llamada *tronco*. En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente, si se conecta a un tronco SIP.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Definir un servidor de mediación en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definir una puerta de enlace en el generador de topologías de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definir troncos adicionales en el generador de topologías de Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Secciones relacionadas

[Configurar las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

