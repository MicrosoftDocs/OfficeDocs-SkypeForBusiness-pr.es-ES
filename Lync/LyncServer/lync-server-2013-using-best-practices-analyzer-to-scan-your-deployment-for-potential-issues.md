---
title: Uso del analizador de procedimientos recomendados para buscar problemas potenciales en la implementación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>Uso del analizador de procedimientos recomendados para examinar la implementación de Lync Server 2013 en busca de posibles problemas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

Para ejecutar un examen del analizador de procedimientos recomendados, debe especificar lo siguiente:

  - **Credenciales**   para ejecutar un examen, debe iniciar sesión en un equipo en el que se instale Best Practices Analyzer con una cuenta que sea miembro del grupo de administradores local. Además, debe iniciar sesión con una cuenta de usuario que tenga los derechos de usuario y permisos necesarios para ejecutar las exploraciones apropiadas, o debe especificar credenciales que tengan los derechos de usuario y permisos apropiados cuando ejecute Best Practices Analyzer. Para obtener más información, consulte pertenencias [a grupos y requisitos de derechos de usuario para Best Practices Analyzer en Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Ámbito de análisis**   para especificar el ámbito del análisis, seleccione las categorías y servidores que desea analizar. Puede seleccionar todas las categorías, una o varias categorías, o uno o varios servidores dentro de una categoría específica en su entorno de Lync Server.

  - **Tipo de análisis**   actualmente, el análisis de comprobación de estado es el único tipo de examen disponible (seleccionado de forma predeterminada). El examen de comprobación de estado genera un informe que incluye errores, advertencias y otra información para todos los servidores especificados en el ámbito.

  - **Velocidad de red**   las opciones de velocidad incluyen LAN rápida (100 Mbps o más), LAN (10 Mbps), WAN rápida (1,5 Mbps) o WAN (64 kbps). El tiempo estimado para completar el examen depende de esta configuración. Esta configuración también se usa para establecer el período de tiempo de espera. Durante el examen, el analizador de procedimientos recomendados espera una respuesta de un servidor durante un tiempo determinado. Si no recibe una respuesta dentro del período de tiempo de espera especificado, pasa al siguiente servidor en el examen. En redes más lentas, este período de tiempo de espera especificado es más largo para las latencias de red más largas. Le recomendamos que seleccione el vínculo más lento de su topología para este parámetro para que la herramienta no agote demasiado tiempo.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Para examinar la implementación de Lync Server 2013

1.  Inicie sesión en un equipo en el que se instale Best Practices Analyzer con una cuenta que sea miembro del grupo de administradores locales y que tenga otros derechos de usuario y permisos necesarios.

2.  Haga clic en **Inicio**, seleccione **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **Best Practices Analyzer**.

3.  En la pantalla de **bienvenida** , haga clic en **seleccionar opciones para una nueva exploración**.

4.  En la página **conectar con Active** Directory, compruebe el nombre especificado en el **servidor de Active**Directory y, a continuación, siga uno de estos procedimientos:
    
      - Para ejecutar un análisis con las credenciales que usó para iniciar sesión en el equipo, haga clic en **conectar con el servidor de Active**Directory.
    
      - Para especificar credenciales diferentes que desee usar para servicios de dominio de Active Directory, servidor perimetral o Exchange Server, haga clic en **Mostrar opciones de inicio de sesión avanzadas**, seleccione las casillas de verificación para las que se necesitan credenciales independientes y especifique las credenciales. para cada casilla seleccionada y, a continuación, haga clic en **conectar con el servidor de Active**Directory.
    
    <div>
    

    > [!NOTE]
    > Antes de comenzar el examen, el analizador de procedimientos recomendados realiza una comprobación de permisos y red para asegurarse de que las credenciales de la cuenta especificada son válidas y de que el analizador de procedimientos recomendados puede conectarse a los servicios de dominio de Active Directory. Si la herramienta se ejecuta en un servidor de grupo de trabajo, la herramienta también comprueba que puede conectarse a los servidores perimetrales de la red perimetral (es decir, si están incluidos en el examen).

    
    </div>

5.  En la página **iniciar un nuevo examen de Best Practices** , seleccione las opciones que desee incluir en el examen, especifique la velocidad de red y, a continuación, haga clic en **Iniciar búsqueda**.

6.  En la página **análisis finalizado** , haga clic en **ver un informe de este examen de procedimientos recomendados**.

7.  En la página **Ver informe de procedimientos recomendados** , realice una de las siguientes acciones:
    
      - Para ver los informes en una lista organizada por componente de servidor, haga clic en **informes de lista**y, a continuación, haga clic en la pestaña **todos los problemas** o en la pestaña **elementos de información** .
    
      - Para ver los informes como una lista jerárquica organizada por tipos de resultados, haga clic en **informes de árbol**y, a continuación, haga clic en la pestaña **vista detallada** o en la pestaña **vista de Resumen** .
    
      - Para ver otros informes, haga clic en **otros informes**.
    
    <div>
    

    > [!NOTE]
    > Para obtener más información sobre los informes del analizador de procedimientos recomendados y los problemas que identifican, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">ver y trabajar con informes creados por Best Practices Analyzer en Lync Server 2013</A> y <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analizar y resolver los problemas identificados por Best Practices Analyzer en Lync Server 2013</A>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

