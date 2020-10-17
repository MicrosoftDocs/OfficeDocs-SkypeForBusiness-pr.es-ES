---
title: Uso del analizador de procedimientos recomendados para analizar la implementación en busca de posibles problemas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a7b43056071ddc2322ff5147de72d818548b86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535887"
---
# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Uso del analizador de procedimientos recomendados para examinar la implementación de Lync Server 2013 para detectar posibles problemas

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

Para ejecutar un examen del Analizador de procedimientos recomendados, debe especificar lo siguiente:

  - **Credenciales**     Para ejecutar un examen, debe iniciar sesión en un equipo en el que se instale Best Practices Analyzer con una cuenta que sea miembro del grupo de administradores locales. Además, tiene que iniciar sesión usando una cuenta de usuario que tenga los derechos de usuario y los permisos necesarios para ejecutar los exámenes adecuados o bien, debe especificar credenciales que tengan los derechos de usuario y permisos adecuados al ejecutar el Analizador de procedimientos recomendados. Para obtener más información, consulte [pertenencias a grupos y requisitos de derechos de usuario para el analizador de procedimientos recomendados en Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Ámbito del examen**     Para especificar el ámbito del análisis, seleccione las categorías y los servidores que desee analizar. Puede seleccionar todas las categorías, una o varias categorías, o uno o más servidores dentro de una categoría específica en su entorno de Lync Server.

  - **Tipo de examen**     Actualmente, el análisis de comprobación de estado es el único tipo de examen disponible (seleccionado de forma predeterminada). El análisis de comprobación de estado genera un informe que incluye errores, advertencias y otra información para todos los servidores especificados en el ámbito.

  - **Velocidad**     de red Las opciones de velocidad de la red incluyen Fast LAN (100 Mbps o más), LAN (10 Mbps), WAN rápida (1,5 Mbps) o WAN (64 kbps). El tiempo estimado para completar el análisis se basa en esta configuración. Esta configuración también se usa para establecer el período de tiempo de espera. Durante el análisis, el Analizador de procedimientos recomendados espera una respuesta de un servidor durante un tiempo especificado. Si no recibe una respuesta dentro del período de tiempo de espera especificado, pasa al siguiente servidor en el examen. En redes más lentas, este período de tiempo especificado es superior para latencias de red de mayor duración. Se recomienda que seleccione el vínculo más lento en su topología para este parámetro de manera que la herramienta no supere el tiempo de espera tan rápidamente.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Para examinar su implementación de Lync Server 2013

1.  Inicie sesión en un equipo en el que el Analizador de procedimientos recomendados está instalado usando una cuenta que es miembro del grupo Administradores local y tiene otros derechos de usuario y permisos requeridos.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, en **analizador de procedimientos recomendados**.

3.  En la pantalla de**** bienvenida, haga clic en **Seleccionar opciones para un nuevo análisis**.

4.  En la página **Conectar con Active Directory**, compruebe el nombre especificado en **Servidor de Active Directory** y, a continuación, lleve a cabo una de las siguientes acciones:
    
      - Para ejecutar un examen usando las credenciales que ha usado para iniciar sesión en el equipo, haga clic en **Conectar al servidor de Active Directory**.
    
      - Para especificar diferentes credenciales que desea usar para Servicios de dominio de Active Directory, servidor perimetral o Exchange Server, haga clic en **Mostrar opciones de inicio de sesión avanzadas**, active cada casilla para la que se requieren credenciales independientes, especifique las credenciales para cada casilla seleccionada y, a continuación, haga clic en **Conectar al servidor de Active Directory**.
    
    <div>
    

    > [!NOTE]
    > Antes de comenzar el examen, el Analizador de procedimientos recomendados lleva a cabo una comprobación de red y permisos para asegurarse de que las credenciales de la cuenta especificada son válidos y que el Analizador de procedimientos recomendados se puede conectar a Servicios de dominio de Active Directory. Si la herramienta se ejecuta en un servidor de grupo de trabajo, la herramienta también comprueba que se puede conectar a servidores perimetrales en la red perimetral (es decir, si se incluyen en el examen).

    
    </div>

5.  En la página **Iniciar un nuevo análisis de Best Practices**, seleccione las opciones que desea incluir en el examen, especifique la velocidad de la red y, a continuación, haga clic en **Iniciar análisis**.

6.  En la página **Análisis completado**, haga clic en **Ver un informe de este análisis de Best Practices**.

7.  En la página **Ver informe de Best Practices**, realice una de las operaciones siguientes:
    
      - Para ver los informes en una lista organizada según el componente del servidor, haga clic en **Informes de lista** y, después, en la pestaña **Todos los problemas** o **Información detallada**.
    
      - Para ver los informes como una lista jerárquica organizada según los tipos de resultados, haga clic en **Informes ramificados** y, después, en la pestaña **Vista detallada** o **Vista de resumen**.
    
      - Para ver otro tipo de informes, haga clic en **Otros informes**.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and Working with Reports Created by Best Practices Analyzer in Lync server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">análisis y resolución de problemas identificados por Best Practices Analyzer en Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

