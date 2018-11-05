---
title: Visualización de informes en el Analizador de procedimientos recomendados
TOCTitle: Visualización de informes en el Analizador de procedimientos recomendados
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48275635
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de informes en el Analizador de procedimientos recomendados

 

_**Última modificación del tema:** 2012-09-21_

Cuando utiliza el Analizador de procedimientos recomendados para examinar su entorno, debe especificar un nombre para el análisis. Una vez finalizado un análisis, el Analizador de procedimientos recomendados almacena los resultados en informes que guarda con el nombre del análisis. Tras el análisis, puede consultar los informes generados haciendo clic en **Ver un informe de este análisis BPA** directamente desde la página **Análisis completado**, aunque también es posible verlos en un momento posterior. Puede ver los informes en el equipo local en el que se ejecutaron los análisis, importar los resultados del análisis desde otro equipo o bien exportar los resultados para visualizar los informes en otro equipo en que el Analizador de procedimientos recomendados esté instalado.

Los resultados del análisis se presentan en estos tipos de informes:

  - Informes de lista

  - Informes ramificados

  - Otros informes

En estos informes se incluye información sobre los errores y las advertencias, entre otros. Para más información sobre estos aspectos y sobre los tipos de informes, vea [Descripción general de los informes creados por el Analizador de procedimientos recomendados](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Use este procedimiento para visualizar los resultados de análisis que el Analizador de procedimientos recomendados generó previamente.

## Para ver los informes de un análisis anterior

1.  Inicie sesión en un equipo en que el Analizador de procedimientos recomendados esté instalado con una cuenta que pertenezca a la cuenta de usuario local.
    

    > [!NOTE]
    > Se pueden ver los resultados de un análisis con una cuenta que pertenezca al grupo Administradores local, pero no se podrá ejecutar un análisis a menos que se disponga de los permisos y derechos adecuados para hacerlo. Para más información, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Requisitos de pertenencias a grupo y de derechos de usuario para el Analizador de procedimientos recomendados</A>.



2.  Haga clic en **Inicio**, apunte a **Todos los programas**, haga clic en **Microsoft Lync Server 2013** y, después, en **Analizador de procedimientos recomendados**.

3.  En la pantalla **Bienvenida**, haga clic en **Seleccionar los resultados de análisis para mostrar**.

4.  En la página **Seleccionar un nuevo análisis BPA para mostrar**, realice uno de estos procedimientos:
    
      - Para ver informes desde la lista de resultados de análisis almacenados localmente, haga clic en el nombre del análisis y, después, en **Ver un informe de este análisis**.
        

        > [!NOTE]
        > El Analizador de procedimientos recomendados crea la lista de archivos locales de la carpeta <EM>&lt;systemDrive&gt;</EM>\Documents and Settings\\<EM>&lt;user&gt;</EM>\Application Data\Microsoft\RtcBPA.

    
      - Para ver los informes de resultados de un análisis que están almacenados en otra ubicación, haga clic en **Importar análisis**, busque el archivo que contiene los resultados del análisis y haga clic en **Abrir**.
        

        > [!NOTE]
        > Si la versión del Analizador de procedimientos recomendados del equipo no es la misma que la que se utilizó para recopilar los datos en el archivo importado, es posible que la herramienta del equipo con el que está trabajando vuelva a analizar el archivo después de importarlo.



5.  En la página **Ver informe del Analizador de procedimientos recomendados**, siga uno de estos procedimientos:
    
      - Para ver los informes en una lista organizada según el componente del servidor, haga clic en **Informes de lista** y, después, en la pestaña **Todos los problemas** o **Información detallada**.
    
      - Para ver los informes como una lista jerárquica organizada según los tipos de resultados, haga clic en **Informes ramificados** y, después, en la pestaña **Vista detallada** o **Vista de resumen**.
    
      - Para ver otro tipo de informes, haga clic en **Otros informes**.
    

    > [!NOTE]
    > Para más información sobre los informes del Analizador de procedimientos recomendados y sobre los problemas que identifican, vea <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Visualización y uso de informes creados por el Analizador de procedimientos recomendados</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Análisis y resolución de problemas identificados por el Analizador de procedimientos recomendados</A>.


