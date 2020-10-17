---
title: Configuración de escenarios de 2013 de Lync Server
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
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499947"
---
# <a name="configure-lync-server-2013-scenarios"></a>Configuración de escenarios de 2013 de Lync Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-28_

Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 (LyncPerfTool), la topología de Lync Server 2013 debe estar configurada primero para los escenarios que se ejecutarán. Si Lync Server 2013 no está configurado o está configurado incorrectamente, se producirá un error en la simulación de carga en la mayoría de los casos. Con la herramienta stress and performance de Lync Server 2013, se proporcionan ejemplos de scripts del shell de administración de Lync Server y archivos de recursos básicos que se pueden usar como punto de partida para configurar Lync Server 2013. En este tema se describen los ejemplos de Windows PowerShell proporcionados. Tenga en cuenta que no es el objetivo de este tema describir cómo configurar Lync Server 2013 en general. Para más detalles sobre cómo trabajar con Windows PowerShell en Lync Server 2013, consulte la documentación del shell de administración de Lync Server en <https://technet.microsoft.com/library/gg398474.aspx> .

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Acerca de la ejecución de scripts del shell de administración de Lync Server

Hemos proporcionado ejemplos de scripts del shell de administración de Lync Server que se pueden usar para preparar la ejecución de la simulación de carga. Debido a que los scripts están diseñados para la simulación de carga, son sencillos y permisivos y, por lo tanto, no son adecuados para la producción. Todos los scripts son ejemplos y deben revisarse y, en algunos casos, se pueden modificar para reflejar la topología. Como mínimo, esperamos que el escenario del servicio de grupo de respuesta (RGS) deba modificarse para especificar los agentes que se asignan a los grupos de agentes. Sin embargo, tiene la opción de no simular esta carga.

<div>


> [!WARNING]  
> Tenga cuidado al revisar y comprender los ejemplos proporcionados. Los scripts sobrescribirán la configuración existente en la topología.



</div>

<div>


> [!NOTE]  
> Para más información sobre el uso de Windows PowerShell y el shell de administración de Lync Server, vea el blog de Lync Server 2013 Windows PowerShell en <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Herramienta de esfuerzo y rendimiento de la versión del cliente de la herramienta

Es posible que tenga que configurar la Directiva de comprobación de versión de cliente si ha cambiado la configuración de los valores predeterminados. Para obtener más información, consulte "configuración de versiones de cliente admitidas" en <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> . La herramienta stress and performance de Lync Server 2013 usa las siguientes versiones de agente de usuario de forma predeterminada al comunicarse con Lync Server 2013:

  - LSPT/15.0.0.0 (herramienta de esfuerzo y rendimiento de Lync Server 2013)

  - OCPHONE/.0.522

Estas son para el cliente de movilidad (UCWA) en LyncPerfTool:

  - Conferencia de rendimiento de Ucwa Tool/Web

  - Herramienta de Perf de Ucwa/móvil

</div>

</div>

<span> </span>

</div>

</div>

</div>

