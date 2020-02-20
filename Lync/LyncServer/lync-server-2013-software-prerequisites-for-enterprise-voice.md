---
title: 'Lync Server 2013: requisitos previos de software para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36ec427751fc6593f03af11bfecddf3bd0bb6280
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Compruebe que la infraestructura en la que tiene pensado implementar la Telefonía IP empresarial satisface el siguiente software necesario como requisito previo:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en la red.

  - Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales que ejecutan el servicio perimetral de acceso, el servicio perimetral A/V, el servicio perimetral de conferencia web y un proxy inverso.

  - Se requiere Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 para integrar la mensajería unificada de Exchange con Lync Server y proporcionar notificaciones enriquecidas e información del registro de llamadas al Puntos de conexión de Lync.

  - Se han creado uno o más usuarios y están habilitados para Lync Server.

  - Los clientes y dispositivos de Lync se han implementado correctamente.

  - El generador de topologías está instalado en un servidor de la red.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Pasos siguientes: Comprobar los requisitos previos de configuración y seguridad

Tras comprobar los requisitos previos de software de la Telefonía IP empresarial, puede usar la documentación para seguir con la preparación de la implementación de Telefonía IP empresarial:

1.  Compruebe la seguridad, la configuración de usuario y la perquisites de hardware, como se describe en [Security and Configuration Prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Instale el servidor de mediación, tal y como se describe en [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero *solo* si desea implementar un servidor o grupo de servidores de mediación independiente, ya que los servidores de mediación se instalan como parte del grupo de servidores front-end o del proceso de implementación de servidor Standard Edition al combinarse.

3.  Configure las conexiones troncales para proporcionar conectividad con RTC a los usuarios, como se describe en [Configuring troncos in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

