---
title: 'Lync Server 2013: requisitos técnicos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Requisitos técnicos para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-06_

Cada equipo que hospede un servidor de chat persistente debe tener acceso a una topología existente de Lync Server 2013 con los siguientes componentes:

  - **Lync Server 2013, servidor front-end.**  El servidor front-end es la base del enrutamiento SIP (Protocolo de inicio de sesión), que hace posible la comunicación entre equipos que ejecutan el servidor de chat persistente y la funcionalidad de chat persistente. Antes de empezar a implementar un servidor de chat persistente, Compruebe la implementación de Lync Server 2013, Standard Edition o un grupo de servidores front-end de Lync Server y cualquier otro equipo interno que ejecute Lync Server, según corresponda a su organización.

En las siguientes secciones se describen los requisitos específicos para el servidor de chat persistente y la base de datos que almacena los datos persistentes del chat.

<div>

## <a name="persistent-chat-server-requirements"></a>Requisitos del servidor de chat persistente

Para obtener detalles sobre el hardware recomendado para implementar Lync Server y la versión más reciente del servidor de chat persistente, consulte [plataformas de hardware de servidor para Lync server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.

Para obtener más información sobre el servidor y las herramientas que admite el sistema operativo para Lync Server y el servidor de chat persistente, consulte [compatibilidad del sistema operativo servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación de soporte técnico.

Para obtener más información sobre software adicional necesario para implementar un servidor de chat persistente, consulte la tabla siguiente.

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
<td><p>Utilizado por el servidor de chat persistente y por el servicio de cumplimiento de chat persistente, si se ha implementado.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Requisitos de base de datos del servidor de chat persistente

El servidor de chat persistente usa la base de datos de chat persistente para almacenar el historial de chat, la configuración y los datos de aprovisionamiento de usuario. De manera opcional, usa la base de datos de cumplimiento de chat persistente para almacenar los datos de cumplimiento.

<div>


> [!IMPORTANT]  
> La base de datos de chat persistente (MGC) y la base de datos de cumplimiento (mgccomp) se pueden encontrar en la misma instancia de SQL Server o en diferentes servidores SQL.



</div>

Para preparar una plataforma de servidor de base de datos, asegúrese de que cada equipo cumpla los requisitos de hardware y, luego, instale el software que se necesita como requisito previo.

La plataforma de servidor de los servidores de base de datos de chat persistente requiere el mismo hardware que el servidor de base de datos back-end de Lync Server. Para obtener más información, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de soporte técnico.

Confirma que una de las siguientes aplicaciones de software está instalada en el servidor de bases de datos:

  - Microsoft SQL Server 2012. Para obtener más información sobre cómo instalar Microsoft SQL Server 2012, consulte "instalar SQL Server 2012" [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)en.

  - Microsoft SQL Server 2008 R2. Para obtener más información sobre cómo instalar Microsoft SQL Server 2008 R2, consulte "instalación de SQL Server (SQL Server 2008 R2) [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)" en.

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Requisitos de certificados del servidor de chat persistente

Para obtener detalles sobre la adquisición de certificados, la creación de la base de datos de SQL Server y la creación de almacenes de archivos, vea [implementar Lync server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

