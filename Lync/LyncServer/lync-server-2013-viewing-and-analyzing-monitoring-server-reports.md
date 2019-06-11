---
title: 'Lync Server 2013: visualización y análisis de informes de servidor de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Ver y analizar informes del servidor de supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-19_

Los informes del servidor de supervisión proporcionan varias medidas diferentes de calidad de voz para supervisar el QoE que se envía a los usuarios finales. Además, Monitoring Server incluye varios informes integrados que su organización puede usar para vigilar las tendencias de calidad de uso y multimedia en la red de su organización y solucionar problemas de calidad de medios que surjan.

Una parte fundamental de mantener los informes del servidor de supervisión interesantes para las operaciones diarias y semanales es ver y analizar los informes de calidad de los medios, en concreto:

  - Resumen/informes de tendencias de QoE

  - Informes de rendimiento de QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Ver informes desde el servidor de supervisión

1.  Desde un explorador Web, busque los servidores que hospedan SQL Reporting Services.

2.  Ver los informes necesarios en la pantalla del explorador.

3.  Faculta Exporte un informe seleccionando la opción de exportación y el formato de salida requerido.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configurar grabación de detalles de llamadas (CDR)

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene permisos equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.

3.  En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.

4.  En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.

5.  Para activar la purga, seleccione **Habilitar purgado para supervisar servidores**.

6.  En **mantener grabaciones de detalles de llamadas para una duración máxima (días):** Seleccione el número máximo de días que deben conservarse las grabaciones de llamadas detalladas.

7.  En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="configure-qoe"></a>Configurar el QoE

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte Delegate Setup Permissions.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Datos sobre la calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, luego, en **Mostrar detalles**.

5.  Para activar la purga, seleccione **Habilitar purgado para supervisar servidores**.

6.  En **mantener grabaciones de detalles de llamadas para duración máxima (días):** Seleccione el número máximo de días que se deben conservar los datos de QoE.

7.  Haga clic en Confirmar.

</div>

<div>

## <a name="change-the-archiving-policy"></a>Cambiar la Directiva de archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar directiva de archivado: global**, haga lo siguiente:

6.  Para habilitar o deshabilitar el archivado interno para la implementación, Active o desactive la casilla de verificación **archivar comunicaciones internas** .

7.  Para habilitar o deshabilitar el archivado externo para la implementación, Active o desactive la casilla **archivar comunicaciones externas** .

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Aplicar una directiva de archivado a un usuario

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar usuario de Lync Server** , en **Directiva**de archivado, seleccione la Directiva de usuario de archivado que desea aplicar.

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Usar informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Informe de comparación de calidad multimedia en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

