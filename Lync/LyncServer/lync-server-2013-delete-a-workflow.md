---
title: Eliminación de un flujo de trabajo
TOCTitle: Eliminación de un flujo de trabajo
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48274288
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de un flujo de trabajo

 

_**Última modificación del tema:** 2012-11-01_

Utilice uno de los procedimientos siguientes para eliminar flujos de trabajo.

## Para usar eliminar flujos de trabajo Panel de control de Lync Server

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Flujo de trabajo**.

4.  En la página **Flujo de trabajo**, haga clic en **Crear o editar flujo de trabajo**.

5.  En el campo de búsqueda **Seleccionar un servicio**, escriba parte del nombre, o el nombre completo, del servicio **ApplicationServer** que hospeda el flujo de trabajo que desea eliminar.

6.  En la lista de servicios, haga clic en el servicio que desee y, a continuación, en **Aceptar**.
    

    > [!NOTE]
    > Se abrirá la página de Herramienta de configuración de grupo de respuesta. También puede abrir la página web de Herramienta de configuración de grupo de respuesta directamente desde un explorador web si se conecta a <STRONG>https://<EM>&lt;webPoolFqdn&gt;</EM>/RgsConfig</STRONG>.



7.  En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea eliminar y, a continuación, en **Acción**, haga clic en **Eliminar**.

8.  Haga clic en **Yes** (Sí).

## Para eliminar flujos de trabajo mediante cmdlets

1.  Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  En la línea de comandos, ejecute:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Por ejemplo:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

