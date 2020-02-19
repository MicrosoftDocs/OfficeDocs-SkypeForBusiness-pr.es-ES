---
title: 'Lync Server 2013: visualización y análisis de informes del servidor de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9970e4c440148cac2002088212a48283c86184eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Ver y analizar los informes del servidor de supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-19_

Los informes del servidor de supervisión proporcionan distintas medidas de calidad de voz para supervisar el QoE que se entrega a los usuarios finales. Además, el servidor de supervisión incluye varios informes integrados que su organización puede usar para ver las tendencias de calidad de medios y de uso en la red de su organización y solucionar los problemas de calidad de los medios que surjan.

Una parte principal de la conservación de informes del servidor de supervisión interesante para las operaciones diarias y semanales es ver y analizar los informes de calidad de los medios, en particular:

  - Informe de tendencias/Resumen de QoE

  - Informes de rendimiento de QoE

<div>

## <a name="view-reports-from-the-monitoring-server"></a>Ver informes desde el servidor de supervisión

1.  En un explorador Web, busque los servidores que hospedan SQL Reporting Services.

2.  Vea los informes necesarios en la pantalla del explorador.

3.  Opcional Exporte un informe seleccionando la opción de exportación y el formato de salida necesario.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>Configuración del registro de detalles de llamadas (CDR)

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga permisos equivalentes), o esté asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.

3.  En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.

4.  En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.

5.  Para activar la purga, seleccione **Habilitar depuración para los servidores de supervisión**.

6.  En **conservar grabaciones de detalles de llamadas durante un máximo de (días):,** Seleccione el número máximo de días que se conservarán los registros detallados de llamadas.

7.  En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="configure-qoe"></a>Configurar QoE

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte Delegate Setup Permissions.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.

5.  Para activar la purga, seleccione **Habilitar depuración para los servidores de supervisión**.

6.  En **conservar grabaciones de detalles de llamadas durante un máximo de (días):,** Seleccione el número máximo de días que se deben conservar los datos de QoE.

7.  Haga clic en  Confirmar .

</div>

<div>

## <a name="change-the-archiving-policy"></a>Cambiar la Directiva de archivado

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.

4.  Haga clic en **Global** en la lista de directivas, en **Editar** y, a continuación, en **Mostrar detalles**.

5.  En **Editar directiva de archivado - Global**, haga lo siguiente:

6.  Para habilitar o deshabilitar el archivado interno para la implementación, Active o desactive la casilla **archivar comunicaciones internas** .

7.  Para habilitar o deshabilitar el archivado externo para la implementación, Active o desactive la casilla de verificación **archivar comunicaciones externas** .

8.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>Aplicar una directiva de archivado a un usuario

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en  **Usuarios ** y, a continuación, busque en la cuenta de usuario que desea configurar.

4.  En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar ** y, a continuación, en  **Mostrar detalles **.

5.  En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Uso de informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
[Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md)  
[Informe de comparación de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

