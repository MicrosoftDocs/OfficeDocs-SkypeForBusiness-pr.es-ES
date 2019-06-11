---
title: 'Lync Server 2013: eliminar un flujo de trabajo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Eliminar un flujo de trabajo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Use uno de los procedimientos siguientes para eliminar un flujo de trabajo.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Para usar el panel de control de Lync Server eliminar un flujo de trabajo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.

5.  En el campo **seleccionar una** búsqueda de servicio, escriba parte o todo el nombre del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea eliminar.

6.  En la lista de servicios, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > Se abre la Página Web de la herramienta de configuración de grupo de respuesta. También puede abrir la Página Web de la herramienta de configuración de grupos de respuesta directamente desde un explorador Web conectándose a <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.

    
    </div>

7.  En **administrar un flujo de trabajo existente**, busque el flujo de trabajo que desea eliminar y, a continuación, en **acción**, haga clic en **eliminar**.

8.  Haga clic en **Sí**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Para usar Windows PowerShell para eliminar un flujo de trabajo

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

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

