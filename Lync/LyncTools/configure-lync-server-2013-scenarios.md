---
title: Configurar escenarios de 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Configurar escenarios de 2013 de Lync Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-28_

Para ejecutar la herramienta Lync Server 2013 stress and Performance (LyncPerfTool), la topología de Lync Server 2013 debe estar configurada en primer lugar para los escenarios que se ejecutarán. Si Lync Server 2013 no está configurado o no está configurado correctamente, la simulación de carga fallará en la mayoría de los casos. Con la herramienta Lync Server 2013 stress and performance, hemos proporcionado ejemplos de scripts del shell de administración de Lync Server y archivos de recursos básicos que se pueden usar como punto de partida para configurar Lync Server 2013. En este tema se describen los ejemplos de Windows PowerShell proporcionados. Tenga en cuenta que no es el objetivo de este tema describir cómo configurar Lync Server 2013 en general. Para obtener más información sobre cómo trabajar con Windows PowerShell en Lync Server 2013, consulte la documentación del shell <https://technet.microsoft.com/en-us/library/gg398474.aspx>de administración de Lync Server en.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Acerca de la ejecución de scripts de Shell de administración de Lync Server

Proporcionamos ejemplos de scripts del shell de administración de Lync Server que se pueden usar en la preparación de la ejecución de la simulación de carga. Dado que los scripts están pensados para la simulación de carga, son sencillos y permisivos, por lo que es posible que no sean adecuados para la producción. Todos los scripts son ejemplos y deben revisarse y, en algunos casos, modificarse para reflejar su topología. Como mínimo, esperamos que el escenario del servicio de grupo de respuesta (RGS) deba modificarse para especificar los agentes que se asignan a los grupos de agentes. Sin embargo, tiene la opción de no simular esta carga.

<div>


> [!WARNING]  
> Preste atención en la revisión y la comprensión de los ejemplos proporcionados. Los scripts sobrescribirán cualquier configuración existente en la topología.



</div>

<div>


> [!NOTE]  
> Para obtener más información sobre el uso de Windows PowerShell y el shell de administración de Lync Server, consulte el blog <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>de lync Server 2013 de Windows PowerShell en.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Herramienta de carga y rendimiento del cliente de la versión del cliente

Es posible que tenga que configurar la Directiva de comprobación de versión del cliente si ha cambiado la configuración de los valores predeterminados. Para obtener más información, consulte "configurar versiones de cliente <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>admitidas" en. La herramienta de estrés y rendimiento de Lync Server 2013 usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Lync Server 2013:

  - LSPT/15.0.0.0 (herramienta Lync Server 2013 stress and Performance)

  - OCPHONE/.0.522

Estos son para el cliente de Mobility (UCWA) en LyncPerfTool:

  - Herramienta de rendimiento de Ucwa y conferencia Web

  - Herramienta de Perf de Ucwa/móvil

</div>

</div>

<span> </span>

</div>

</div>

</div>

