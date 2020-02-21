---
title: 'Lync Server 2013: instalación de los archivos del agente de Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Instalar los archivos del agente Operations Manager en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Para instalar los archivos del agente Operations Manager en el equipo, complete los siguientes pasos.

1.  En los medios de configuración de System Center, haga doble clic en **SetupOM. exe**.

2.  En el programa de instalación de System Center Operations Manager, haga clic en **instalar agente de Operations Manager**.

3.  En el Asistente para la instalación de System Center, en la página **éste es el Asistente para la instalación de System Center Operations Manager** , haga clic en **siguiente**.

4.  En la página **carpeta de destino** , seleccione la carpeta en la que se instalarán los archivos del agente de Operations Manager y, a continuación, haga clic en **siguiente**.

5.  En la página **configuración del grupo de administración** , seleccione **especificar información del grupo de administración**y, a continuación, haga clic en **siguiente**.

6.  En la página **configuración del grupo** de administración, escriba el nombre del grupo de administración de Operations Manager en el cuadro Nombre del grupo de **Administración** y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, ATL-SCOM-001) en el cuadro servidor de **Administración** . Si ha cambiado el número de puerto que usa Operations Manager, escriba el nuevo número de puerto en el cuadro puerto del servidor de administración. En caso contrario, deje el puerto en el valor predeterminado de 5723 y haga clic en **siguiente**.

7.  En la página **cuenta de acción del agente** , seleccione **sistema local**y, a continuación, haga clic en **siguiente**.

8.  En la página **Microsoft Update** , seleccione **no quiero usar Microsoft Update**y, a continuación, haga clic en **siguiente**.

9.  En la página **listo para instalar** , haga clic en **instalar**.

10. En la página **finalización del Asistente para la instalación de System Center Operations Manager** , haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Si usa System Center 2007 R2, puede comprobar que el agente se ha creado haciendo clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2007 R2**y, a continuación, en **Shell de Operations Manager**. En el shell de Operations Manager, escriba el siguiente comando de Windows PowerShell y, a continuación, presione ENTRAR:

    Get-Agent 

Una lista de todos los agentes de Operations Manager aparecerá en pantalla.

Si usa System Center 2012, ejecute este comando desde el shell Operations 2012 Manager:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

