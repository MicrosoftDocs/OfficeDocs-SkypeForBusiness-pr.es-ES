---
title: "Analizador de proceds. recomendados para analizar implementación y buscar problemas"
TOCTitle: "Ut. de Best Practices Analyzer pour rech. les pb éventuels ds votre déploiem."
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48274373
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Uso del Analizador de procedimientos recomendados para analizar la implementación y buscar posibles problemas

 

_**Última modificación del tema:** 2012-10-21_

Para ejecutar un examen del Analizador de procedimientos recomendados, debe especificar lo siguiente:

  - **Credenciales**   Para ejecutar un examen, debe iniciar sesión en un equipo en el que el Analizador de procedimientos recomendados se instala mediante una cuenta que es miembro del grupo Administradores local. Además, tiene que iniciar sesión usando una cuenta de usuario que tenga los derechos de usuario y los permisos necesarios para ejecutar los exámenes adecuados o bien, debe especificar credenciales que tengan los derechos de usuario y permisos adecuados al ejecutar el Analizador de procedimientos recomendados. Para obtener detalles, vea [Requisitos de pertenencias a grupo y de derechos de usuario para el Analizador de procedimientos recomendados](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Ámbito del examen**   Para especificar el ámbito del examen, seleccione las categorías y los servidores que desea examinar. Puede seleccionar todas las categorías, una o más categorías, o uno o más servidores dentro de una categoría específica en su entorno de Lync Server.

  - **Tipo de examen**   En la actualidad, el examen de comprobación de estado es el único tipo de examen disponible (seleccionado de manera predeterminada). El análisis de comprobación de estado genera un informe que incluye errores, advertencias y otra información para todos los servidores especificados en el ámbito.

  - **Velocidad de red**   Entre las opciones de velocidad de red se incluyen LAN rápida (100 Mbps o más), LAN (10 Mbps), WAN rápida (1,5 Mbps) o WAN (64 kbps). El tiempo estimado para completar el análisis se basa en esta configuración. Esta configuración también se usa para establecer el período de tiempo de espera. Durante el análisis, el Analizador de procedimientos recomendados espera una respuesta de un servidor durante un tiempo especificado. Si no recibe una respuesta dentro del período de tiempo de espera especificado, pasa al siguiente servidor en el examen. En redes más lentas, este período de tiempo especificado es superior para latencias de red de mayor duración. Se recomienda que seleccione el vínculo más lento en su topología para este parámetro de manera que la herramienta no supere el tiempo de espera tan rápidamente.

## Para examinar su implementación de Lync Server 2013

1.  Inicie sesión en un equipo en el que el Analizador de procedimientos recomendados está instalado usando una cuenta que es miembro del grupo Administradores local y tiene otros derechos de usuario y permisos requeridos.

2.  Haga clic en **Inicio**, seleccione **Todos los programas**, haga clic en **Microsoft Lync Server 2013** y, a continuación, en **Analizador de procedimientos recomendados**.

3.  En la pantalla debienvenida, haga clic en **Seleccionar opciones para un nuevo análisis**.

4.  En la página **Conectar con Active Directory**, compruebe el nombre especificado en **Servidor de Active Directory** y, a continuación, lleve a cabo una de las siguientes acciones:
    
      - Para ejecutar un examen usando las credenciales que ha usado para iniciar sesión en el equipo, haga clic en **Conectar al servidor de Active Directory**.
    
      - Para especificar diferentes credenciales que desea usar para Servicios de dominio de Active Directory, servidor perimetral o Exchange Server, haga clic en **Mostrar opciones de inicio de sesión avanzadas**, active cada casilla para la que se requieren credenciales independientes, especifique las credenciales para cada casilla seleccionada y, a continuación, haga clic en **Conectar al servidor de Active Directory**.
    

    > [!NOTE]
    > Antes de comenzar el examen, el Analizador de procedimientos recomendados lleva a cabo una comprobación de red y permisos para asegurarse de que las credenciales de la cuenta especificada son válidos y que el Analizador de procedimientos recomendados se puede conectar a Servicios de dominio de Active Directory. Si la herramienta se ejecuta en un servidor de grupo de trabajo, la herramienta también comprueba que se puede conectar a servidores perimetrales en la red perimetral (es decir, si se incluyen en el examen).



5.  En la página **Iniciar un nuevo análisis de Best Practices**, seleccione las opciones que desea incluir en el examen, especifique la velocidad de la red y, a continuación, haga clic en **Iniciar análisis**.

6.  En la página **Análisis completado**, haga clic en **Ver un informe de este análisis de Best Practices**.

7.  En la página **Ver informe de Best Practices**, realice una de las operaciones siguientes:
    
      - Para ver informes en una lista organizada por componente de servidor, haga clic en **Informes de la lista** y, a continuación, haga clic en la pestaña **Todos los problemas** o en la pestaña **Elementos informativos**.
    
      - Para ver informes en una lista jerárquica organizada por tipos de resultados, haga clic en **Informes ramificados** y, a continuación, haga clic en la pestaña **Vista detallada** o en la pestaña **Vista de resumen**.
    
      - Para ver otros informes, haga clic en **Otros informes**.
    

    > [!NOTE]
    > Para obtener detalles acerca de los informes del Analizador de procedimientos recomendados y los problemas que identifican, vea <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Visualización y uso de informes creados por el Analizador de procedimientos recomendados</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Análisis y resolución de problemas identificados por el Analizador de procedimientos recomendados</A>.


