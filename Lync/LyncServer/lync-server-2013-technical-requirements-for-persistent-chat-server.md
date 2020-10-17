---
title: 'Lync Server 2013: requisitos técnicos para el servidor de chat persistente'
description: 'Lync Server 2013: requisitos técnicos para el servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905563f31de36d41a48aea5fb8db3cfde9cb2434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550336"
---
# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Requisitos técnicos para el servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-06_

Cada equipo que hospede el servidor de chat persistente debe tener acceso a una topología existente de Lync Server 2013 con los siguientes componentes:

  - **Lync server 2013, servidor front-end.**   El servidor front-end es la base del enrutamiento del Protocolo de inicio de sesión (SIP), que hace posible la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente. Antes de empezar a implementar el servidor de chat persistente, Compruebe la implementación de Lync Server 2013, Standard Edition o un grupo de servidores front-end de Lync Server y cualquier otro equipo interno que ejecute Lync Server, según corresponda a su organización.

En las secciones siguientes se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos de chat persistente.

<div>

## <a name="persistent-chat-server-requirements"></a>Requisitos del servidor de chat persistente

Para obtener información detallada sobre el hardware recomendado para la implementación de Lync Server y la versión más reciente del servidor de chat persistente, vea [plataformas de hardware de servidor para Lync server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

Para obtener más información sobre la compatibilidad del sistema operativo de servidor y herramientas con Lync Server y el servidor de chat persistente, consulte [Server and Tools Operating System support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación sobre compatibilidad.

Para obtener más información sobre el software adicional necesario para implementar el servidor de chat persistente, vea la tabla siguiente.

### <a name="persistent-chat-server-software-prerequisites"></a>Requisitos previos del software del servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Message Queue Server</p></td>
<td><p>Lo usa el servidor de chat persistente y el servicio de cumplimiento de chat persistente, si se implementan.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Requisitos de la base de datos del servidor de chat persistente

El servidor de chat persistente usa la base de datos de chat persistente para almacenar los datos del historial de chats, la configuración y el aprovisionamiento de usuarios. Opcionalmente, usa la base de datos de cumplimiento de chat persistente para almacenar datos de cumplimiento.

<div>


> [!IMPORTANT]  
> La base de datos de chat persistente (MGC) y la base de datos de cumplimiento (mgccomp) pueden encontrarse en la misma instancia de SQL Server o en diferentes servidores SQL Server.



</div>

Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumple los requisitos de hardware y, a continuación, instale el software necesario como requisito previo.

La plataforma de servidor para los servidores de base de datos de chat persistente requiere el mismo hardware que el servidor de base de datos back-end de Lync Server. Para obtener más información, consulte [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre compatibilidad.

En el servidor de bases de datos, asegúrese de que esté instalada una de las siguientes aplicaciones de software:

  - Microsoft SQL Server 2012. Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, consulte "instalar SQL Server 2012" en [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559) .

  - Microsoft SQL Server 2008 R2. Para obtener más información sobre cómo instalar Microsoft SQL Server 2008 R2, vea "instalación de SQL Server (SQL Server 2008 R2)" en [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702) .

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificados del servidor de chat persistente

Para obtener información detallada acerca de la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

