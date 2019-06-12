---
title: 'Lync Server 2013: Requisitos previos de software para la telefonía IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Requisitos previos de software para la telefonía IP empresarial en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Compruebe que la infraestructura en la que desea implementar Enterprise Voice cumpla los siguientes requisitos previos de software:

  - Lync Server 2013 Standard Edition o Enterprise Edition está instalado y en funcionamiento en su red.

  - Todos los servidores perimetrales se implementan y funcionan en la red perimetral, incluidos los servidores perimetrales que ejecutan el servicio perimetral de acceso, el servicio perimetral a/V, el servicio perimetral de conferencias web y un proxy inverso.

  - Se necesita Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 o Microsoft Exchange Server 2013 para integrar la mensajería unificada de Exchange con Lync Server y ofrecer notificaciones enriquecidas e información de registro de llamadas al Puntos de conexión de Lync.

  - Uno o más usuarios se han creado y habilitado para Lync Server.

  - Los clientes y dispositivos de Lync se han implementado correctamente.

  - El generador de topología se instala en un servidor de su red.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Pasos siguientes: comprobar la seguridad y los requisitos previos de configuración

Después de comprobar los requisitos previos de software de telefonía IP empresarial, puede usar la documentación para continuar con la preparación de la implementación de telefonía IP empresarial:

1.  Comprobar la seguridad, la configuración de usuario y el hardware perquisites, como se describe en [seguridad y configuración requisitos previos para telefonía IP empresarial en Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Instale el servidor de mediación, como se describe en [instalar los archivos de Media Server en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), pero *solo* si desea implementar un servidor o grupo de mediación independiente, ya que los servidores de mediación están instalados como parte del grupo de servidores front-end o Proceso de implementación de servidor Standard Edition cuando se colocan.

3.  Configure conexiones troncales para proporcionar conectividad RTC para los usuarios, como se describe en [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

