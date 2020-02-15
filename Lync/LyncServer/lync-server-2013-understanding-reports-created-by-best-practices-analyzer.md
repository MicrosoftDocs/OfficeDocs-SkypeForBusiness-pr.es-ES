---
title: 'Lync Server 2013: Descripción de los informes creados por el analizador de procedimientos recomendados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56556d209e073be49a6c0eb2aa30461a06930238
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Información sobre los informes creados por el analizador de procedimientos recomendados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

El Analizador de procedimientos recomendados ofrece varios tipos de informes organizados que se organizan para facilitar el análisis y la resolución de problemas. El Analizador de procedimientos recomendados identifica problemas como, por ejemplo, errores o advertencias, entre otros.

<div>

## <a name="reports"></a>Informes

Puede tener acceso a los resultados del análisis viendo consultando cada uno de los informes siguientes:

  - ****   Enumerar informes: los informes se organizan según criterios específicos. Puede organizar los resultados por clase, gravedad o problema. Por ejemplo, si organiza los resultados por clase, los problemas relacionados con los Directivos se incluyen en la sección Directivos del informe. Puede ver todos los problemas o solo los elementos informativos. Puede ver un informe de la lista con elementos específicos como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

  - ****   Los informes de árbol de informes de árbol están organizados por las reglas que se usan para ejecutar el análisis y otras opciones especificadas en el momento en que se ejecutó el análisis. Por ejemplo, los problemas relacionados con la topología de pruebas se incluyen en la sección Topología de pruebas del informe. Puede ver los detalles de todos los problemas o solo un resumen de los problemas. Puede buscar un informe ramificado con elementos específicos como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

  - **Otros**   elementos de informes en otros informes incluyen el registro de tiempo de ejecución de las tareas incluidas en el examen. Puede buscar elementos específicos de otros informes como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

</div>

<div>

## <a name="issues"></a>Problemas

Los informes que genera el Analizador de procedimientos recomendados indican que existen problemas específicos identificados durante el análisis del entorno, entre los que se incluyen los siguientes:

  - **Errores**   : problemas críticos que requieren que se realice un cambio en el entorno. Por ejemplo, si los componentes principales de Lync Server 2013 no están instalados, se registra un error.

    Los problemas clasificados como errores se identifican en el informe con una X de color rojo. Los errores se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, el error solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.

  - **ADVERTENCIAS**   problemas que no son coherentes con la implementación de un procedimiento recomendado. Esto puede indicar que es necesario realizar un cambio en el entorno, o no. El problema puede ser un problema conocido con una configuración específica que no es necesario cambiar. Por ejemplo, los servicios que no se inician en un servidor se registran como advertencias.

    Los problemas clasificados como advertencias se identifican en el informe con un signo de advertencia triangular de color amarillo. Las advertencias se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista**, así como en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, la advertencia solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.

  - **La información**   incluye todos los problemas que no se clasifican como errores o advertencias. Por ejemplo, el número de objetos de servidor de Lync Server 2013 Standard Edition en servicios de dominio de Active Directory se clasifica como un problema de información.

    Los problemas informativos se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** de la vista **Informes ramificados**.

El analizador de procedimientos recomendados de Lync Server 2013 no realiza cambios en el entorno para resolver problemas. El análisis solo detecta problemas potenciales y ofrece informes que contienen información sobre cómo resolver cada uno de los problemas.

Si hace clic en un problema, se mostrarán explicaciones y opciones para dicho problema. A continuación, podrá llevar a cabo uno de los procedimientos siguientes:

  - Buscar información detallada sobre el problema y sobre cómo resolverlo.

  - Detener la visualización de problemas en los informes:

      - Detener la visualización de problemas para la instancia seleccionada.

      - Detener la visualización de problemas para todas las instancias del problema.

    Para ver los problemas cuya visualización en los informes haya detenido, vaya a la pestaña **Elementos ocultos** de la vista **Otros informes**. Desde ahí podrá especificar que se vuelvan a mostrar dichos problemas en los informes.

Para obtener más información sobre cómo resolver problemas específicos, consulte [análisis y resolución de problemas identificados por Best Practices Analyzer en Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>
