---
title: 'Lync Server 2013: configuración del servidor de administración principal'
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
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configurar el servidor de administración principal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-19_

Para aprovechar al máximo las nuevas capacidades de supervisión de estado incluidas en Microsoft Lync Server 2013 los administradores deben designar un equipo para que actúe como servidor de administración principal; en ese equipo, debe instalar System Center Operations Manager 2007 R2 o System Center Operations Manager 2012. Además, debe instalar una versión compatible de SQL Server para que funcione como la base de datos back-end de Operations Manager. Si está usando System Center Operations Manager 2012, puede usar cualquiera de las siguientes versiones de SQL Server como base de datos back-end:

  - Service Pack 1 de SQL Server 2008 R2

  - Service Pack 2 de SQL Server 2008 R2

Si está usando System Center Operations Manager 2007 R2, le recomendamos que instale SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3. También puede usar SQL Server 2008 R2 como base de datos de back-end para System Center Operations Manager 2007 R2. Consulte el apéndice 1 de esta documentación para obtener más información sobre cómo configurar SQL Server 2008 R2 para que funcione con System Center Operations Manager 2007 R2.

Al instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, necesita instalar todos los componentes de ese producto, entre los que se incluyen:

  - Base de datos operativa

  - Servidor

  - Consola

  - Cmdlets de Windows PowerShell

  - Consola web

  - Informes

  - Almacén de datos

Estos componentes y su instalación no se tratarán en detalle en este documento. Para obtener más información sobre System Center Operations Manager 2007 R2, consulte la documentación de Operations Manager 2007 R2 en <http://go.microsoft.com/fwlink/p/?linkid=257526> y la documentación de <http://go.microsoft.com/fwlink/p/?linkid=257527>System Center Operations Manager 2012 en. Debe seguir estas instrucciones si va a usar SQL Server 2005 o SQL Server 2008 Service Pack 1 como base de datos back-end.

Si está usando System Center Operations Manager 2012, puede usar SQL Server 2012 como base de datos back-end. Para obtener más información sobre SQL Server 2012, consulte libros en línea para SQL [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)Server 2012 en.

Tenga en cuenta que solo puede tener un único servidor de administración principal por cada implementación de Lync Server. Además, aunque puede usar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, no puede ejecutar las dos aplicaciones a la vez: debe elegir una u otra. Por ejemplo, si está ejecutando System Center Operations Manager 2012, todos sus agentes de System Center también deben estar ejecutando System Center Operations Manager 2012. No puede tener algunos agentes ejecutando System Center Operations Manager 2012 y otros agentes que ejecuten System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

