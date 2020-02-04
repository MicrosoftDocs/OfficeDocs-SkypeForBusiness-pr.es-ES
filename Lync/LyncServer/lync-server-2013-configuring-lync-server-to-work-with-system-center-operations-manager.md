---
title: Configurar Lync Server para que funcione con System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0cf422ddab501acf521c26c36d8f373bd42dbf9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Configuración de Lync Server 2013 para que funcione con System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Para configurar la infraestructura de Microsoft Lync Server 2013 de forma que funcione con System Center Operations Manager, debe realizar tres acciones:

  - Identifique y configure su servidor de administración principal de System Center Operations Manager. La configuración del servidor de administración incluye la instalación de System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, así como la configuración de una base de datos back-end con SQL Server. La versión real de SQL Server que necesita usar depende de la versión de System Center Operations Manager que esté usando. Para obtener más información, vea [configurar el servidor de administración principal en Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifique y configure los equipos de Lync Server que desea supervisar. Para supervisar un equipo de Lync Server con System Center Operations Manager, debe instalar los archivos del agente System Center Operations Manager y configurar cada servidor para que actúe como proxy.

  - Identifique y configure los equipos que desea que actúen como *nodos de monitor*de Lync Server. Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Lync Server, que son cmdlets de Windows PowerShell que comprueban que los componentes clave de Lync Server, como la capacidad de iniciar sesión en el sistema o la posibilidad de intercambiar mensajes instantáneos, funciona según lo esperado.

Los temas de esta sección contienen instrucciones para llevar a cabo cada una de estas tareas.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar el servidor de administración principal en Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Instalar los módulos de administración de Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configurar los equipos de Lync Server que se supervisarán en Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Instalar y configurar nodos de monitor en Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

