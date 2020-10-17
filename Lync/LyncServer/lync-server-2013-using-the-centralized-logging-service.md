---
title: 'Lync Server 2013: uso del servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 276cc87d6ec943332fc30dc21c0906a03703382d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529957"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Uso del servicio de registro centralizado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio de registro centralizado es una nueva característica de Lync Server 2013. Es un reemplazo mejorado para las herramientas **OCSLogger** y **OCSTracer** que se proporcionaron en las versiones anteriores. Puede usar el servicio de registro centralizado para realizar las siguientes tareas:

  - Comience por iniciar sesión en uno o más PC y grupos desde una sola ubicación y comando.

  - No inicie sesión en una o más PC y grupos desde una sola ubicación y comando.

  - Busque registros en una o más PC y grupos para una sola ubicación y comando. Puede personalizar el comando de búsqueda para que devuelva toda la suma de registros que se capturaron y almacenaron en todos los PC o devolver un resultado recortado que captura la información específica.

  - Configurar las sesiones de registro de la siguiente manera:
    
      - Defina un **Escenario** o use un escenario predeterminado. Un *escenario* en el servicio de registro centralizado se compone de ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar dos escenarios en cualquier momento en una computadora.
    
      - Use un *proveedor* existente o cree un nuevo proveedor. Un *proveedor* define qué sesión de registro recopila, qué nivel de detalle, qué componentes seguirá y qué marcas se aplican.
        
        <div>
        

        > [!TIP]  
        > Si conoce el OCSLogger, el término <EM>proveedores</EM> hace referencia a la colección de <STRONG>componentes</STRONG> (por ejemplo, S4, SIPStack), un <STRONG>tipo de registro</STRONG> (por ejemplo, WPP, EventLog o IIS logfile), un <STRONG>nivel de seguimiento</STRONG> (por ejemplo, Todo, Detallado, depuración) y <STRONG>marcas</STRONG> (por ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan al comando del servicio de registro centralizado.

        
        </div>
    
      - Configurar los PC y grupos desde donde desea recopilar los registros.
    
      - Defina el ámbito de la sesión de registro desde las opciones **Sitio** (ejecutar las capturas de registro en los PC solo en ese sitio) o **Global** (ejecutar las capturas de registro en todas los PC de la implementación).

El servicio de registro centralizado es extremadamente eficaz y puede satisfacer casi todas las necesidades de solución de problemas, tanto grandes como pequeñas. Desde el análisis de causa raíz a problemas de rendimiento, el servicio de registro centralizado puede ser una herramienta importante para los administradores. Todos los ejemplos se muestran con el shell de administración de Lync Server. Hay un componente de línea de comandos para el servicio de registro centralizado denominado **CLSController.exe**. Se proporciona ayuda para la herramienta de la línea de comandos a través de la misma herramienta. Sin embargo, existe una cantidad limitada de funciones que puede ejecutar desde la línea de comandos. Mediante el shell de administración de Lync Server, tiene acceso a un conjunto de características mucho más amplio y mucho más configurable. Debe considerar siempre el shell de administración de Lync Server como el primer y más importante método al usar el servicio de registro centralizado.

En los temas de esta sección se explica cómo usar el servicio de registro centralizado y ejemplos de cómo usar sus numerosas características.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Administración de las opciones de configuración del servicio de registro centralizado en Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Información sobre las opciones de configuración del servicio de registro centralizado en Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Uso de inicio para el servicio de registro centralizado para capturar registros en Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Uso de STOP para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lectura de registros de captura desde el servicio de registro centralizado en Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

