---
title: 'Lync Server 2013: eliminar un flujo de trabajo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91326023357df0903ab506217c6abb53babcdf66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Eliminar un flujo de trabajo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Utilice uno de los procedimientos siguientes para eliminar flujos de trabajo.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Para usar el panel de control de Lync Server eliminar un flujo de trabajo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar flujo de trabajo**.

5.  En el campo de búsqueda **Seleccionar un servicio**, escriba parte del nombre, o el nombre completo, del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea eliminar.

6.  En la lista de servicios, haga clic en el servicio que desee y, a continuación, en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Se abre la página web herramienta de configuración del grupo de respuesta. También puede abrir la Página Web de la herramienta de configuración del grupo de respuesta directamente desde un explorador Web conectándose a <STRONG>&lt;https://fqdngrupoweb&gt;/RgsConfig</STRONG>.

    
    </div>

7.  En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea eliminar y, a continuación, en **Acción**, haga clic en **Eliminar**.

8.  Haga clic en **Yes** (Sí).

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Para usar Windows PowerShell para eliminar un flujo de trabajo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Por ejemplo:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

