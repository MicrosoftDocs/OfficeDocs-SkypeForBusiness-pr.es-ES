---
title: Uso del servicio de registro centralizado de Lync Server 2013
TOCTitle: Uso del servicio de registro centralizado de Lync Server 2013
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49889240
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso del servicio de registro centralizado de Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

El Servicio de registro centralizado es una nueva característica de Lync Server 2013. Es un reemplazo mejorado para las herramientas **OCSLogger** y **OCSTracer** que se proporcionaron en las versiones anteriores. Puede usar el Servicio de registro centralizado para realizar las siguientes tareas:

  - Comience por iniciar sesión en uno o más PC y grupos desde una sola ubicación y comando.

  - No inicie sesión en una o más PC y grupos desde una sola ubicación y comando.

  - Busque registros en una o más PC y grupos para una sola ubicación y comando. Puede personalizar el comando de búsqueda para que devuelva toda la suma de registros que se capturaron y almacenaron en todos los PC o devolver un resultado recortado que captura la información específica.

  - Configurar las sesiones de registro de la siguiente manera:
    
      - Defina un **Escenario** o use un escenario predeterminado. Un *escenario* en Servicio de registro centralizado está conformado de un ámbito (global o local), un nombre de escenario para identificar el propósito del escenario y uno o más proveedores. Puede ejecutar dos escenarios en cualquier momento en una computadora.
    
      - Use un *proveedor* existente o cree un nuevo proveedor. Un *proveedor* define qué sesión de registro recopila, qué nivel de detalle, qué componentes seguirá y qué marcas se aplican.
        
        > [!TIP]  
        > Si conoce el OCSLogger, el término <em>proveedores</em> hace referencia a la colección de <strong>componentes</strong> (por ejemplo, S4, SIPStack), un <strong>tipo de registro</strong> (por ejemplo, WPP, EventLog o IIS logfile), un <strong>nivel de seguimiento</strong> (por ejemplo, Todo, Detallado, depuración) y <strong>marcas</strong> (por ejemplo, TF_COMPONENT, TF_DIAG). Estos elementos se definen en el comando del proveedor (una variable Windows PowerShell) y se pasan al comando Servicio de registro centralizado.
        
    
      - Configurar los PC y grupos desde donde desea recopilar los registros.
    
      - Defina el ámbito de la sesión de registro desde las opciones **Sitio** (ejecutar las capturas de registro en los PC solo en ese sitio) o **Global** (ejecutar las capturas de registro en todas los PC de la implementación).

El Servicio de registro centralizado es extremadamente potente y puede satisfacer casi todas las necesidades para resolver problemas, ya sean grandes o pequeños. Desde el análisis de las causas principales hasta los problemas de rendimiento, el Servicio de registro centralizado puede ser una importante herramienta para cualquier administrador. Todos los ejemplos se muestran con el Shell de administración de Lync Server. Existe un componente de línea de comando para el Servicio de registro centralizado llamado **CLSController.exe**. Se proporciona ayuda para la herramienta de la línea de comandos a través de la misma herramienta. Sin embargo, existe una cantidad limitada de funciones que puede ejecutar desde la línea de comandos. Al utilizar Shell de administración de Lync Server, tiene acceso a un conjunto mucho mayor y mucho más configurable de características. Siempre debe considerar Shell de administración de Lync Server como el método principal y más importante al usar el Servicio de registro centralizado.

Los temas en esta sección explican cómo usar el Servicio de registro centralizado y ejemplifica cómo usar sus variadas características.

## En esta sección

  - [Descripción general del servicio de registro centralizado](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Administración de las opciones de configuración del servicio de registro centralizado con PowerShell](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Introducción a las opciones de configuración del servicio de registro centralizado](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Uso de Inicio para el servicio de registro centralizado para los registros de captura](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Uso de Detener en el servicio de registro centralizado](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Uso de búsquedas en registros de captura creados por el servicio de registro centralizado](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lectura de registros de captura desde el servicio de registro centralizado](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

