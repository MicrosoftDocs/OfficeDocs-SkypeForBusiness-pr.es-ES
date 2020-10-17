---
title: 'Lync Server 2013: usar informes de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae3182dd6129d9ce797739220faeef0cd97a3a92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518817"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a>Uso de informes de supervisión en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

Lync Server 2013 incluye un conjunto de informes estándar que publica Microsoft SQL Server Reporting Service. Estos informes, a los que se puede acceder con un explorador web, proporcionan información de uso, diagnóstico de llamadas y calidad de medios, basada en la información del registro detallado de llamadas (CDR) y la calidad de la experiencia (QoE) almacenada en las bases de datos de CDR y QoE.

Para poder usar estos informes, debe instalar los informes de supervisión en un equipo que ejecute una instancia de SQL Server.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Uso del panel de supervisión en Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)     Proporciona a los administradores una introducción rápida de la salud del sistema y el uso del sistema.

  - [Informes de uso del sistema en Lync Server 2013](lync-server-2013-system-usage-reports.md)     Proporciona información sobre el uso del sistema según los datos CDR recopilados por Lync Server.

  - [Informes de diagnósticos de llamadas (por usuario) en Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)     Proporciona información por usuario sobre sesiones de conferencia y de punto a punto con errores.

  - [Informes de diagnósticos de llamadas en Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     Proporciona información de Resumen y datos de diagnóstico para sesiones de punto a punto y de conferencia en las que se han producido errores.

  - [Informes de diagnóstico de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     Proporciona información sobre la calidad de las llamadas, así como información de diagnóstico y solución de problemas para las llamadas fallidas.

</div>

<div>

## <a name="locating-records"></a>Localización de registros

Los informes de supervisión muestran únicamente un número limitado de registros en pantalla de cada vez. El número de registros que aparece en una pantalla varía en función del informe. Para ver los registros no reflejados en pantalla en un momento dado, se pueden usar los controles habituales para ir hacia delante o hacia atrás, que encontrará en la barra de herramientas de todos los informes y que le permitirán avanzar por los datos de página en página. También se puede ir rápidamente a la primera o a la última página del conjunto de datos.

Además de estos controles, también se puede ir a cualquier página del conjunto de datos escribiendo el número de página en el cuadro **Página actual** y presionando la tecla ENTRAR.

Además de poder avanzar por los datos de página en página, todos los informes incluyen también la capacidad limitada de buscar registros. Para buscar registros según un valor determinado, escriba dicho valor en el cuadro **Buscar** y haga clic en **Buscar**. El informe empieza a buscar en los datos y se detiene la primera vez que aparezca el valor escrito en **Buscar**. Para encontrar el siguiente registro que cumpla con los criterios de búsqueda, haga clic en **Siguiente**.

Tal y como se ha mencionado, los informes de supervisión ofrecen únicamente las funciones de búsqueda más básicas; así, por ejemplo, no se puede especificar el campo en el que buscar el valor, sino que se buscan automáticamente los valores coincidentes en todos los campos de todos los registros. Tampoco se pueden usar caracteres comodín en las búsquedas y en todos los casos se buscarán valores parciales. Esto quiere decir que, si se busca 111, la búsqueda detectará no solo el valor 111, sino también los valores 11100, 811, 3112, 611A5B y cualquier otro campo que incluya el valor 111.

Cada informe está configurado para mostrar un número de registros predeterminado. Por ejemplo, el informe de registro de usuario refleja de manera predeterminada las actividades de registro del usuario de la última semana. Algunas veces esto se traduce en un informe que no muestra registros, lo que significa que no se han producido registros de usuario en la última semana. Si se muestra el mensaje “Ningún resultado coincide con los filtros del informe”, pruebe a cambiar los valores de filtro (por ejemplo, cambie el período de tiempo al mes pasado, en lugar de a la semana pasada) y vuelva a ejecutar la consulta. Para obtener información detallada, consulte "Filtrar datos" más adelante en esta sección.

</div>

<div>

## <a name="filtering-data"></a>Filtrado de datos

Probablemente en alguna ocasión quiera buscar en un subconjunto de registros únicamente (por ejemplo, solo las sesiones punto a punto frente a las sesiones punto a punto y las sesiones de conferencia juntas). De igual forma, otras veces necesitará reducir el número de registros que la búsqueda devuelve. Un informe solo puede mostrar 1.000 registros en un conjunto de datos de manera predeterminada. Para abordar esta situación, la mayoría de los informes incluye una serie de opciones de filtrado. Por ejemplo, si quiere ver únicamente los registros correspondientes al período de tiempo comprendido entre el 1 y el 15 de de enero de 2011, puede especificar la fecha 1 de enero de 2011 en el cuadro **Desde** y la fecha 15 de enero de 2011 en el cuadro **Hasta**. Si después hace clic en **Ver informe**, los datos obtenidos se limitarán a las actividades que ocurrieron entre el 1 y el 15 de enero de 2011.

Los filtros de que disponga variarán en función del informe que esté viendo. Para obtener información detallada sobre un informe en particular, consulte el tema de ayuda correspondiente.

</div>

<div>

## <a name="exporting-data"></a>Exportación de datos

Los informes de supervisión ofrecen al menos dos modos distintos de exportar los datos de un informe. Puede usar la opción **Exportar** de la barra de herramientas que aparece en la parte superior de cada informe. Para usar esta opción, seleccione el formato de exportación que desee de la lista desplegable **Seleccionar un formato**, en la que verá los siguientes formatos:

  - Archivo XML con datos de informe

  - Archivo CSV (delimitado por comas)

  - Archivo de Acrobat (PDF)

  - Archivo MHTML (archivo web)

  - Excel

  - Archivo TIFF

  - Word

Una vez seleccionado el formato, haga clic en **Exportar**. Cuando se abra el cuadro de diálogo **Descarga de archivos**, haga clic en **Guardar**. En el cuadro de diálogo **Guardar como**, seleccione una carpeta de destino, escriba un nombre de archivo y haga clic en **Guardar**.

Si tiene Microsoft OneNote instalado, también puede optar por copiar los datos del informe a OneNote. Para ello, haga clic con el botón secundario en el botón **Ver informe** en la barra de tareas. En el cuadro de diálogo **Seleccionar la ubicación en OneNote**, seleccione la sección de OneNote en la que quiera copiar los datos y, a continuación, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

