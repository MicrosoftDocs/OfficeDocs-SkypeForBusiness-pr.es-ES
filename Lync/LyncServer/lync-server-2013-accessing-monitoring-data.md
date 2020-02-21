---
title: 'Lync Server 2013: acceso a datos de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aee3b01eaefa08bfa35ba7355debe347bc07ff0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="b5329-102">Obtener acceso a los datos de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5329-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5329-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="b5329-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="b5329-p101">Los datos de supervisión se almacenan en dos bases de datos de SQL Server: LcsCdr para obtener los datos de registro de detalles y QoEMetrics para los datos de Calidad de la experiencia. No hay nada especial en estas dos bases de datos; esto significa que los datos almacenados en estas bases de datos pueden accederse con cualquiera de las herramientas que usa generalmente para acceder y analizar los datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5329-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="b5329-106">Una herramienta que debe tener en cuenta para obtener acceso a los datos de supervisión y analizarlos es los informes de supervisión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5329-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="b5329-107">Los Informes de supervisión son un conjunto de informes estándar que son publicados por el servicio de informes del servidor de Microsoft SQL.</span><span class="sxs-lookup"><span data-stu-id="b5329-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="b5329-108">Estos informes, a los que se puede acceder con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE.</span><span class="sxs-lookup"><span data-stu-id="b5329-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="b5329-109">Los informes de supervisión se incluyen en Lync Server 2013 y se pueden instalar desde el Asistente para la implementación de Lync Server después de que Lync Server se haya instalado y se haya configurado la supervisión.</span><span class="sxs-lookup"><span data-stu-id="b5329-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="b5329-p103">Como se observó, los Informes de supervisión requieren el uso del servicio de informes del servidor SQL. El servicio de informes del servidor SQL puede instalarse simultáneamente con el Servidor SQL o puede instalarse en cualquier momento después de haber instalado el Servidor SQL.</span><span class="sxs-lookup"><span data-stu-id="b5329-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="b5329-112">Para obtener más información, vea el tema [Installing Lync server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) en la guía de implementación de lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5329-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

