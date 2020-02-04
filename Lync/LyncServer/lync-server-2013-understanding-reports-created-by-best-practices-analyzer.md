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
ms.openlocfilehash: 2262c490d84ec6f93ff395a9c8ec38d81c82e7de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Información sobre los informes creados por Best Practices Analyzer en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

El analizador de procedimientos recomendados proporciona varios tipos de informes organizados para facilitar el análisis y la resolución de problemas. El analizador de procedimientos recomendados identifica problemas como errores, advertencias y otra información.

<div>

## <a name="reports"></a>Informar

Puede acceder a los resultados de un análisis viendo cada uno de los siguientes informes:

  - ****   Lista de informes lista los informes se organizan según criterios específicos. Puede organizar los resultados por clase, gravedad o problema. Por ejemplo, si se organizan los resultados por clase, los problemas relacionados con los directores se incluyen en la sección directores del informe. Puede ver todos los problemas o solo los elementos informativos. Puede buscar elementos específicos en un informe de lista, como la memoria. También puede imprimir el informe o exportarlo.

  - **Informes de árbol**   los informes de árbol se organizan según las reglas que se usan para ejecutar el examen y otras opciones que especificó en el momento en que se ejecutó el análisis. Por ejemplo, los problemas relacionados con las reglas de topología de prueba se incluyen en la sección topología de prueba del informe. Puede ver los detalles de todos los problemas o solo un resumen de los problemas. Puede buscar elementos específicos en un informe de árbol, como la memoria. También puede imprimir el informe o exportarlo.

  - **Otros informes**   elementos en otros informes incluyen el registro en tiempo de ejecución de las tareas que se incluyeron en el examen. Puede buscar elementos específicos en los elementos de otros informes, como la memoria. También puede imprimir el informe o exportarlo.

</div>

<div>

## <a name="issues"></a>Problemas

Los informes generados por Best Practices Analyzer indican problemas específicos que se identifican durante el análisis de su entorno, incluidos los siguientes tipos de problemas:

  - **Errores**   críticos que requieren que se realice un cambio en su entorno. Por ejemplo, si los componentes principales de Lync Server 2013 no están instalados, se registra un error.
    
    Los problemas que se clasifican como errores se identifican en el informe mediante un símbolo X de color rojo. Se muestran errores en la pestaña **todos los problemas** de la vista **informes de lista** y en la pestaña **vista detallada** y la pestaña vista de **Resumen** de la vista informes de **árbol** . Si no desea ver un error específico en un informe, puede especificar que el error no se muestre para una única instancia o para todas las instancias de ese error en el informe. El error se muestra solo en la pestaña **elementos ocultos** de la vista **otros informes** , a menos que cambie la configuración y especifique que el error se muestre en el informe.

  - **ADVERTENCIAS**   problemas que no son coherentes con la implementación de un procedimiento recomendado. Esto puede indicar o no la necesidad de un cambio en su entorno. El problema podría ser un problema conocido con una configuración específica que no necesita cambiar. Por ejemplo, los servicios que no se inician en un servidor se registran como advertencias.
    
    Los problemas que se clasifican como advertencias se identifican en el informe mediante un símbolo de advertencia de color amarillo triangular. Las advertencias se muestran en la pestaña **todos los problemas** de la vista **informes de lista** , así como en la pestaña **vista detallada** y la pestaña **vista de Resumen** de la vista informes de **árbol** . Si no desea ver un error específico en un informe, puede especificar que el error no se muestre para una única instancia o para todas las instancias de ese error en el informe. La advertencia se muestra solo en la pestaña **elementos ocultos** de la vista **otros informes** , a menos que cambie la configuración y especifique que la advertencia se muestre en el informe.

  - **La información**   incluye todos los problemas que no se clasifican como errores o advertencias. Por ejemplo, el número de objetos de servidor de Lync Server 2013 Standard Edition en servicios de dominio de Active Directory se clasifica como un problema de información.
    
    Se muestran problemas de información en la pestaña **todos los problemas** de la vista **informes de lista** y en la pestaña **vista detallada** de la vista **informes de árbol** .

Lync Server 2013, analizador de procedimientos recomendados, no realiza cambios en su entorno para resolver problemas. El examen solo detecta posibles problemas y proporciona informes que contienen información sobre cómo resolver cada problema.

Si hace clic en un problema, se muestra una explicación y algunas opciones para problemas específicos. Después, puede realizar cualquiera de las siguientes acciones:

  - Obtenga más información detallada sobre el problema y cómo resolverlo.

  - Dejar de mostrar problemas en los informes:
    
      - Dejar de mostrar los problemas de la instancia seleccionada.
    
      - Dejar de mostrar problemas en todas las instancias de ese problema.
    
    Para ver los problemas que se han dejado de mostrar en los informes, vaya a la pestaña **elementos ocultos** de la vista **otros informes** . Desde allí, puede especificar que empiece a mostrar los problemas en los informes.

Para obtener más información sobre cómo resolver problemas específicos, consulte [analizar y resolver problemas identificados por Best Practices Analyzer en Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

