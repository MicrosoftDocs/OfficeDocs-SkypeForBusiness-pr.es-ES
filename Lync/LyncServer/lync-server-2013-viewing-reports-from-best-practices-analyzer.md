---
title: 'Lync Server 2013: visualización de informes desde Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Ver informes de Best Practices Analyzer en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Al usar el analizador de procedimientos recomendados para explorar su entorno, especifica un nombre para el examen. Después de que el analizador de procedimientos recomendados complete un examen, almacena los resultados del análisis en informes y los guarda bajo el nombre de la búsqueda. Una vez finalizado el análisis, puede ver los informes generados para ese análisis haciendo clic en **ver un informe de este examen de procedimientos recomendados** directamente desde la página **análisis finalizado** . También puede ver los informes de ese análisis o análisis anteriores más adelante. Puede ver informes en el equipo local en el que se ejecutó el examen, importar resultados del examen de otro equipo o exportar resultados del examen para ver los informes en otro equipo en el que está instalado Best Practices Analyzer.

Los resultados del examen se presentan en los siguientes tipos de informes:

  - Informes de listas

  - Informes de árbol

  - Otros informes

Estos informes incluyen errores, advertencias y otra información. Para obtener más información sobre cada uno de estos tipos de informes y problemas, vea información sobre los [informes creados por Best Practices Analyzer en Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Use el procedimiento siguiente para ver los resultados del examen generados previamente por el analizador de procedimientos recomendados.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Para ver los informes de un examen anterior

1.  Inicie sesión en un equipo en el que se instale Best Practices Analyzer con una cuenta que sea miembro de la cuenta de usuario local.
    
    > [!NOTE]  
    > Puede ver los resultados de un análisis con una cuenta que sea miembro del grupo de administradores locales, pero no puede ejecutar un examen a menos que tenga los derechos de usuario y permisos adecuados. Para obtener más información, consulte pertenencias <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">a grupos y requisitos de derechos de usuario para Best Practices Analyzer en Lync Server 2013</A>.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **Best Practices Analyzer**.

3.  En la pantalla de **bienvenida** , haga clic en **seleccionar los resultados del análisis que desea ver**.

4.  En la página **seleccionar el examen de procedimientos recomendados para ver** , realice una de las siguientes acciones:
    
      - Para ver los informes de la lista de resultados de exámenes almacenados de forma local, haga clic en el nombre de la exploración y, a continuación, haga clic en **ver un informe de este examen**.
        
        > [!NOTE]  
        > El Best Practices Analyzer crea la lista de archivos locales de la &lt;carpeta&gt;\\systemDrive Documents\\&lt;and&gt;Settings usuario \Datos de Data\Microsoft\RtcBPA.
    
      - Para ver los informes de los resultados de un examen guardado en otra ubicación, haga clic en **importar examen**, busque el archivo que contiene los resultados del análisis y, a continuación, haga clic en **abrir**.
        
        > [!NOTE]  
        > Si la versión del analizador de procedimientos recomendados en este equipo no coincide con la versión que se usó para recopilar los datos en el archivo importado, es posible que la herramienta del equipo vuelva a analizar el archivo después de importarlo.

5.  En la página **Ver informe de procedimientos recomendados** , realice una de las siguientes acciones:
    
      - Para ver los informes en una lista organizada por componente de servidor, haga clic en **informes de lista**y, a continuación, haga clic en la pestaña **todos los problemas** o en la pestaña **elementos de información** .
    
      - Para ver los informes como una lista jerárquica organizada por tipos de resultados, haga clic en **informes de árbol**y, a continuación, haga clic en la pestaña **vista detallada** o en la pestaña **vista de Resumen** .
    
      - Para ver otros informes, haga clic en **otros informes**.
    
    > [!NOTE]  
    > Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">ver y trabajar con informes creados por Best Practices Analyzer en Lync Server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analizar y resolver los problemas identificados por los procedimientos recomendados. Analyzer en Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

