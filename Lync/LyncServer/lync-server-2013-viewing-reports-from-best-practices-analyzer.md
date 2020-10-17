---
title: 'Lync Server 2013: visualización de informes desde el analizador de procedimientos recomendados'
description: 'Lync Server 2013: ver informes desde el analizador de procedimientos recomendados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44e0f1ed8d48f5c8fb7e35187ecdda2778091407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542366"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Ver informes desde el analizador de procedimientos recomendados en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Cuando utiliza el Analizador de procedimientos recomendados para examinar su entorno, debe especificar un nombre para el análisis. Una vez finalizado un análisis, el Analizador de procedimientos recomendados almacena los resultados en informes que guarda con el nombre del análisis. Tras el análisis, puede consultar los informes generados haciendo clic en **Ver un informe de este análisis BPA** directamente desde la página **Análisis completado**, aunque también es posible verlos en un momento posterior. Puede ver los informes en el equipo local en el que se ejecutaron los análisis, importar los resultados del análisis desde otro equipo o bien exportar los resultados para visualizar los informes en otro equipo en que el Analizador de procedimientos recomendados esté instalado.

Los resultados del análisis se presentan en estos tipos de informes:

  - Informes de lista

  - Informes ramificados

  - Otros informes

En estos informes se incluye información sobre los errores y las advertencias, entre otros. Para obtener más información sobre cada uno de estos tipos de informes y problemas, consulte [Understanding Reports Created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Use este procedimiento para visualizar los resultados de análisis que el Analizador de procedimientos recomendados generó previamente.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Para ver los informes de un análisis anterior

1.  Inicie sesión en un equipo en que el Analizador de procedimientos recomendados esté instalado con una cuenta que pertenezca a la cuenta de usuario local.
    
    > [!NOTE]  
    > Se pueden ver los resultados de un análisis con una cuenta que pertenezca al grupo Administradores local, pero no se podrá ejecutar un análisis a menos que se disponga de los permisos y derechos adecuados para hacerlo. Para obtener más información, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados en Lync Server 2013</A>.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, en **analizador de procedimientos recomendados**.

3.  En la pantalla **Bienvenida**, haga clic en **Seleccionar los resultados de análisis para mostrar**.

4.  En la página **Seleccionar un nuevo análisis BPA para mostrar**, realice uno de estos procedimientos:
    
      - Para ver informes desde la lista de resultados de análisis almacenados localmente, haga clic en el nombre del análisis y, después, en **Ver un informe de este análisis**.
        
        > [!NOTE]  
        > El analizador de procedimientos recomendados crea la lista de archivos locales de la carpeta &lt; unidadDelSistema &gt; \\ Documents and Settings \\ &lt; usuario &gt; \Datos de Data\Microsoft\RtcBPA.
    
      - Para ver los informes de resultados de un análisis que están almacenados en otra ubicación, haga clic en **Importar análisis**, busque el archivo que contiene los resultados del análisis y haga clic en **Abrir**.
        
        > [!NOTE]  
        > Si la versión del Analizador de procedimientos recomendados del equipo no es la misma que la que se utilizó para recopilar los datos en el archivo importado, es posible que la herramienta del equipo con el que está trabajando vuelva a analizar el archivo después de importarlo.

5.  En la página **Ver informe del Analizador de procedimientos recomendados**, siga uno de estos procedimientos:
    
      - Para ver los informes en una lista organizada según el componente del servidor, haga clic en **Informes de lista** y, después, en la pestaña **Todos los problemas** o **Información detallada**.
    
      - Para ver los informes como una lista jerárquica organizada según los tipos de resultados, haga clic en **Informes ramificados** y, después, en la pestaña **Vista detallada** o **Vista de resumen**.
    
      - Para ver otro tipo de informes, haga clic en **Otros informes**.
    
    > [!NOTE]  
    > Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and Working with Reports Created by Best Practices Analyzer in Lync server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">análisis y resolución de problemas identificados por Best Practices Analyzer en Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

