---
title: 'Lync Server 2013: instalar los archivos del agente de Operations Manager'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8675e6c75c288e6594e45ecdcc2f65497a047a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a>Instalación de los archivos del agente de Operations Manager en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Siga los pasos que se indican a continuación para instalar los archivos del agente Operations Manager en el equipo.

1.  En los medios de configuración de System Center, haga doble clic en **SetupOM. exe**.

2.  En el programa de instalación de System Center Operation Manager, haga clic en **instalar agente Operations Manager**.

3.  En el Asistente de configuración de System Center, en la página asistente **para la instalación de System Center Operations Manager** , haga clic en **siguiente**.

4.  En la página **carpeta de destino** , seleccione la carpeta en la que se instalarán los archivos del agente de Operations Manager y, a continuación, haga clic en **siguiente**.

5.  En la página **configuración del grupo de administración** , seleccione **especificar información del grupo de administración**y, a continuación, haga clic en **siguiente**.

6.  En la página **configuración del grupo** de administración, escriba el nombre del grupo de administración de Operations Manager en el cuadro Nombre del grupo de **Administración** y, a continuación, escriba el nombre de host del servidor de Operations Manager (por ejemplo, ATL-SCOM-001) en la ** Cuadro servidor de administración** . Si ha cambiado el número de Puerto usado por Operations Manager, escriba el nuevo número de puerto en el cuadro puerto del servidor de administración. En caso contrario, deje el puerto con el valor predeterminado de 5723 y haga clic en **siguiente**.

7.  En la página **cuenta de acción del agente** , seleccione **sistema local**y, a continuación, haga clic en **siguiente**.

8.  En la página de **Microsoft Update** , seleccione **no quiero usar Microsoft Update**y, a continuación, haga clic en **siguiente**.

9.  En la página **preparado para instalar** , haga clic en **instalar**.

10. En la página **finalización del Asistente para la instalación de System Center Operations Manager** , haga clic en **Finalizar**.

11. Haga clic en **Salir**.

Si usa System Center 2007 R2, puede comprobar que el agente se ha creado haciendo clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2007 R2**y, a continuación, en **Operations Manager Shell**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:

    Get-Agent 

Aparecerá una lista de todos tus agentes de Operations Manager en pantalla.

Si usa System Center 2012, ejecute este comando desde el shell de Operations 2012 Manager:

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

