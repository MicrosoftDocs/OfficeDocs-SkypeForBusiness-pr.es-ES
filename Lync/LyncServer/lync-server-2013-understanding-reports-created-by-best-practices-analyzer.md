---
title: Descripción de los informes creados por el Analizador de procedimientos recomendados
TOCTitle: Descripción general de los informes creados por el Analizador de procedimientos recomendados
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48274495
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Descripción general de los informes creados por el Analizador de procedimientos recomendados

 

_**Última modificación del tema:** 2012-10-10_

El Analizador de procedimientos recomendados ofrece varios tipos de informes organizados que se organizan para facilitar el análisis y la resolución de problemas. El Analizador de procedimientos recomendados identifica problemas como, por ejemplo, errores o advertencias, entre otros.

## Informes

Puede tener acceso a los resultados del análisis viendo consultando cada uno de los informes siguientes:

  - **Informes de la lista**   Los informes de la lista están organizados según criterios específicos. Puede organizar los resultados por clase, gravedad o problema. Por ejemplo, si organiza los resultados por clase, los problemas relacionados con los Directivos se incluyen en la sección Directivos del informe. Puede ver todos los problemas o solo los elementos informativos. Puede ver un informe de la lista con elementos específicos como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

  - **Informes ramificados**   Los informes ramificados están organizados según las reglas que se usan para ejecutar el análisis y el resto de opciones especificadas en el momento en el que se ejecutó el informe. Por ejemplo, los problemas relacionados con la topología de pruebas se incluyen en la sección Topología de pruebas del informe. Puede ver los detalles de todos los problemas o solo un resumen de los problemas. Puede buscar un informe ramificado con elementos específicos como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

  - **Otros informes**   Los elementos incluidos en Otros informes incluyen el registro de tiempo de ejecución de tareas que se incluyeron en el análisis. Puede buscar elementos específicos de otros informes como, por ejemplo, la memoria. También puede imprimir el informe o exportarlo.

## Problemas

Los informes que genera el Analizador de procedimientos recomendados indican que existen problemas específicos identificados durante el análisis del entorno, entre los que se incluyen los siguientes:

  - **Errores**   Problemas graves que requieren hacer un cambio en el entorno. Por ejemplo, se registrará un error si los componentes principales de Lync Server 2013 no están instalados.
    
    Los problemas clasificados como errores se identifican en el informe con una X de color rojo. Los errores se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, el error solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.

  - **Advertencias**   Las advertencias son problemas que no están en línea con la implementación de un procedimiento recomendado. Esto puede indicar que es necesario realizar un cambio en el entorno, o no. El problema puede ser un problema conocido con una configuración específica que no es necesario cambiar. Por ejemplo, los servicios que no se inician en un servidor se registran como advertencias.
    
    Los problemas clasificados como advertencias se identifican en el informe con un signo de advertencia triangular de color amarillo. Las advertencias se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista**, así como en la pestaña **Vista detallada** y **Vista reducida** de la vista **Informes ramificados**. Si desea que no se muestre un error específico en un informe, puede especificar que no se muestre una instancia o todas las instancias de dicho error en el informe. De este modo, la advertencia solo se mostrará en la pestaña **Elementos ocultos** de la vista **Otros informes** a menos que modifique la configuración y especifique que se muestre el error en el informe.

  - **Información**   Incluye todos los problemas que no pueden clasificarse como errores o advertencias. Por ejemplo, el número de objetos del servidor Lync Server 2013 Standard Edition en Servicios de dominio de Active Directory se clasifica como un problema informativo.
    
    Los problemas informativos se muestran en la pestaña **Todos los problemas** de la vista **Informes de la lista** y en la pestaña **Vista detallada** de la vista **Informes ramificados**.

En Lync Server 2013, el Analizador de procedimientos recomendados no realiza cambios en el entorno para resolver los problemas. El análisis solo detecta problemas potenciales y ofrece informes que contienen información sobre cómo resolver cada uno de los problemas.

Si hace clic en un problema, se mostrarán explicaciones y opciones para dicho problema. A continuación, podrá llevar a cabo uno de los procedimientos siguientes:

  - Buscar información detallada sobre el problema y sobre cómo resolverlo.

  - Detener la visualización de problemas en los informes:
    
      - Detener la visualización de problemas para la instancia seleccionada.
    
      - Detener la visualización de problemas para todas las instancias del problema.
    
    Para ver los problemas cuya visualización en los informes haya detenido, vaya a la pestaña **Elementos ocultos** de la vista **Otros informes**. Desde ahí podrá especificar que se vuelvan a mostrar dichos problemas en los informes.

Para obtener más detalles sobre la resolución de problemas específicos, vea [Análisis y resolución de problemas identificados por el Analizador de procedimientos recomendados](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

