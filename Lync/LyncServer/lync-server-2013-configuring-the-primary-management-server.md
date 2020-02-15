---
title: 'Lync Server 2013: configurar el servidor de administración principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6640e13209700d50aac04c43728175a4fcb4e6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configurar el servidor de administración principal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-19_

Para sacar el máximo partido a las nuevas funciones de supervisión de estado incluidas en los administradores de Microsoft Lync Server 2013, primero debe designar un equipo para que actúe como servidor de administración principal; en ese equipo, debe instalar System Center Operations Manager 2007 R2 o System Center Operations Manager 2012. Además, debe instalar una versión compatible de SQL Server para que funcione como su base de datos back-end de Operations Manager. Si usa System Center Operations Manager 2012, puede usar cualquiera de las siguientes versiones de SQL Server como base de datos back-end:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Si usa System Center Operations Manager 2007 R2, se recomienda que instale SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3. También puede usar SQL Server 2008 R2 como base de datos back-end para System Center Operations Manager 2007 R2. Vea el apéndice 1 de esta documentación para obtener más información sobre cómo configurar SQL Server 2008 R2 para que funcione con System Center Operations Manager 2007 R2.

Al instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, debe instalar todos los componentes de ese producto, incluidos:

  - Base de datos operativa

  - Servidor

  - Consola

  - Cmdlets de Windows PowerShell

  - Consola web

  - Reporting

  - Almacén de datos

Estos componentes y su instalación no se explicarán en detalle en este documento. Para obtener más información sobre System Center Operations Manager 2007 R2, consulte la documentación de Operations Manager 2007 R2 en <http://go.microsoft.com/fwlink/p/?linkid=257526> y la documentación de <http://go.microsoft.com/fwlink/p/?linkid=257527>System Center Operations Manager 2012 en. Debe seguir estas instrucciones si va a usar SQL Server 2005 o SQL Server 2008 Service Pack 1 como base de datos back-end.

Si usa System Center Operations Manager 2012, puede usar SQL Server 2012 como base de datos back-end. Para obtener más información sobre SQL Server 2012, vea los libros en pantalla de [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)sql server 2012 en.

Tenga en cuenta que solo puede tener un único servidor de administración principal por cada implementación de Lync Server. Además, aunque puede usar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, no puede ejecutar las dos aplicaciones simultáneamente; debe elegir una o la otra. Por ejemplo, si ejecuta System Center Operations Manager 2012, todos los agentes de System Center también deben ejecutar System Center Operations Manager 2012. No puede haber algunos agentes ejecutando System Center Operations Manager 2012 y otros agentes que ejecutan System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

