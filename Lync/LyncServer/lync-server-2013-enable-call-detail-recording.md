---
title: 'Lync Server 2013: habilitar el registro detallado de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309d96d6aacd5409aa285ddeb4b95837ca98e302
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528797"
---
# <a name="enable-call-detail-recording-in-lync-server-2013"></a>Habilitar el registro detallado de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) registra la información de uso y diagnóstico sobre actividades punto a punto, incluida la mensajería instantánea, llamadas de voz sobre IP (VoIP), uso compartido de aplicaciones, transferencia de archivos y reuniones. Los datos de uso pueden servir para calcular el retorno de la inversión y los datos de diagnóstico se pueden usar para solucionar problemas de actividades punto a punto y reuniones.

Use el procedimiento siguiente para habilitar el registro detallado de llamadas (CDR) en toda la organización o en cada sitio de la organización.

<div>


> [!NOTE]  
> Para poder habilitar el CDR debe configurar la supervisión y una base de datos de supervisión. Para obtener más información, consulte <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>Para habilitar CDR con el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, en **Registro detallado de llamadas**.

4.  En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la lista, seleccione **Acción** y, a continuación, haga clic en **Habilitar CDR**.
    
    <div>
    

    > [!NOTE]  
    > CDR habilitado de forma predeterminada.

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitación de CDR mediante cmdlets de Windows PowerShell

Puede habilitar CDR mediante Windows PowerShell y el cmdlet **set-CsCdrConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar CDR para una única ubicación

  - Para deshabilitar CDR, establezca el parámetro EnableCDR en True ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>Para deshabilitar CDR para una única ubicación

  - Para deshabilitar CDR, establezca el parámetro EnableCDR en False ($False). La deshabilitación de CDR no desinstala la supervisión. Pausa la recopilación y el almacenamiento de datos de CDR.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Utilizar un único comando para habilitar CDR en varias ubicaciones

  - Este comando habilita CDR para todos los parámetros de CDR que se encuentran actualmente en uso en su organización.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación de la supervisión en Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

