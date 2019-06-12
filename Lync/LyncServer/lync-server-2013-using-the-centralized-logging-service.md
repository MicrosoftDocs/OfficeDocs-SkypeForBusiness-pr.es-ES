---
title: 'Lync Server 2013: usar el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Usar el servicio de registro centralizado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El servicio de registro centralizado es una nueva característica de Lync Server 2013. Se trata de una sustitución mejorada para las herramientas **OCSLogger** y **OCSTracer** que se proporcionaron en versiones anteriores. Puede usar el servicio de registro centralizado para realizar las siguientes tareas:

  - Iniciar el registro en uno o más equipos y grupos de repositorios desde una sola ubicación y un mismo comando.

  - Detener el registro de uno o varios equipos y grupos desde una única ubicación y comando.

  - Buscar registros en uno o más equipos y grupos para una única ubicación y un comando. Puede personalizar el comando de búsqueda para que devuelva toda la agregación de registros que se han capturado y almacenado en todos los equipos, o bien devolver un resultado recortado que captura datos específicos.

  - Configure las sesiones de registro de la siguiente manera:
    
      - Defina un **Escenario** o use un escenario predeterminado. Un *escenario* en el servicio de registro centralizado está formado por ámbito (global o sitio), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar dos escenarios en cualquier momento en un equipo.
    
      - Use un *proveedor* existente o cree uno. Un *proveedor* define qué recopila la sesión de registro, su nivel de detalle, qué componentes seguirá y qué marcas se aplican.
        
        <div>
        

        > [!TIP]  
        > Si conoce OCSLogger, el término <EM>proveedores</EM> hace referencia a la colección de <STRONG>componentes</STRONG> (por ejemplo, S4, SIPStack), un <STRONG>tipo de registro</STRONG> (por ejemplo, WPP, EventLog o IIS logfile), un <STRONG>nivel de seguimiento</STRONG> (por ejemplo, Todo, Detallado, Depuración) y las <STRONG>marcas</STRONG> (por ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el proveedor (una variable de Windows PowerShell) y se pasan al comando del servicio de registro centralizado.

        
        </div>
    
      - Configure los equipos y grupos de los que desea recopilar registros.
    
      - Defina el ámbito de la sesión de registro en el **sitio** de opciones (ejecutar registro de capturas en equipos de ese sitio solo) o **global** (ejecutar captura de registro en todos los equipos de la implementación).

El servicio de registro centralizado es extremadamente eficaz y puede cumplir casi todas las necesidades de solución de problemas de solución de problemas: grande o pequeño. Desde el análisis de causa raíz hasta problemas de rendimiento, el servicio de registro centralizado puede ser una herramienta importante para cualquier administrador. Se muestran todos los ejemplos con el shell de administración de Lync Server. Hay un componente de línea de comandos para el servicio de registro centralizado denominado **CLSController. exe**. La herramienta de línea de comandos proporciona ayuda a través de la propia herramienta. Sin embargo, hay un conjunto limitado de funciones que puede ejecutar desde la línea de comandos. Mediante el shell de administración de Lync Server, tiene acceso a un conjunto de características mucho más amplio y configurable. Siempre debe considerar el shell de administración de Lync Server como el primer y más importante método al usar el servicio de registro centralizado.

En los temas de esta sección se explica cómo usar el servicio de registro centralizado y ejemplos de uso de sus numerosas características.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre el servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Administración de la configuración del servicio de registro centralizado en Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Descripción de la configuración del servicio de registro centralizado en Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Uso de iniciar para el servicio de registro centralizado para capturar registros en Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Usar detener para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Usar la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lectura de registros de captura del servicio de registro centralizado en Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

