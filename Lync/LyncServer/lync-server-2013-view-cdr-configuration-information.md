---
title: 'Lync Server 2013: ver la información de configuración de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60ea87c488c84f76e60d3a4ad1815e8cfcb3d078
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506637"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Ver la información de configuración de CDR en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas en conferencia. Estos datos de uso abarcan información sobre quién llamó a quién, cuándo se llamó y la duración de la llamada.

Al instalar Microsoft Lync Server 2013, se creará una única colección global de opciones de configuración de CDR. Los administradores también tienen la opción de crear colecciones de opciones de configuración personalizadas que se pueden aplicar a sitios individuales. Puede ver las opciones de configuración de CDR que se usan en la organización mediante el panel de control de Lync Server o el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Para ver la información de configuración de CDR mediante el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **supervisión y archivado**.

2.  En la pestaña **Registro detallado de llamadas**, se mostrará una lista de todas las opciones de configuración de CDR. En cada colección de opciones verá la colección **Nombre**, con independencia de si se habilitó CDR (la propiedad **CDR**) y el purgado (la propiedad **Purgado de CDR**). Para ver información detallada sobre una colección en concreto, haga doble clic sobre la colección o selecciónela, haga clic en **Editar** y, luego, en **Mostrar detalles**. Tenga en cuenta que solo puede ver información detallada de una única colección de opciones de configuración al mismo tiempo.

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de CDR mediante los cmdlets de Windows PowerShell

Puede ver las opciones de configuración de CDR con Windows PowerShell y el cmdlet Get-CsCdrConfiguration. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-cdr-configuration-information"></a>Para ver la información de configuración de CDR

  - Para ver información sobre todas las opciones de configuración de CDR, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsCdrConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

