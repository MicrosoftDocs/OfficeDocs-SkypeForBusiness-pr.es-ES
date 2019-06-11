---
title: 'Lync Server 2013: mover grupos de respuesta a un grupo nuevo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Mover grupos de respuesta a un grupo nuevo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Lync Server 2013 introduce nuevos cmdlets que permiten mover grupos de respuesta de un grupo a otro, incluso cuando el nombre de dominio completo (FQDN) es diferente.

Siga los pasos que se indican en el siguiente procedimiento para mover grupos de respuesta de un grupo de servidores front-end a otro grupo de servidores front-end con un FQDN diferente.

<div>


> [!NOTE]  
> En un entorno de coexistencia, solo puede mover grupos de respuesta entre grupos&nbsp;front-end de Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Para mover grupos de respuesta a un grupo con un FQDN diferente

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Exporte los grupos de respuesta en el grupo de origen. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Para quitar los grupos de respuesta del grupo de origen durante la exportación, incluya el parámetro – RemoveExportedConfiguration. Por ejemplo:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importe los grupos de respuesta al grupo de destino y asigne el grupo de destino como nuevo propietario. En la línea de comandos, escriba:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Si también desea copiar la configuración del nivel de aplicación del grupo de respuesta del grupo de origen al grupo de destino, incluya el parámetro – ReplaceExistingRgsSettings. Solo puede definir un conjunto de opciones de configuración de la aplicación por grupo. Si copia la configuración de nivel de aplicación del grupo de origen en el grupo de destino, la configuración del grupo de origen reemplaza la configuración del grupo de destino. Si no copia la configuración de nivel de aplicación del grupo de origen, la configuración existente del grupo de destino se aplicará a los grupos de respuesta importados.
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > La configuración de nivel de aplicación incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada. Para ver estas opciones de configuración, ejecute el cmdlet <STRONG>Get-CsRgsConfiguration</STRONG> . Para obtener más información sobre este cmdlet, vea <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Para comprobar que la importación se ha realizado correctamente, muestre la configuración del grupo de respuesta importado de la siguiente manera:
    
      - Compruebe que se importaron todos los flujos de trabajo. En la línea de comandos, escriba:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Compruebe que se han importado todas las colas. En la línea de comandos, escriba:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verifique que se hayan importado todos los grupos de agentes. En la línea de comandos, escriba:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verifique que se hayan importado todas las horas de trabajo. En la línea de comandos, escriba:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Verifique que se hayan importado todos los conjuntos de días festivos. En la línea de comandos, escriba:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Verifique que la importación se haya realizado correctamente colocando una llamada a uno de los grupos de respuesta y verificando que la llamada se controla correctamente.

6.  Solicitar agentes que sean miembros de grupos de agentes formales para iniciar sesión en sus grupos de agentes en el grupo de servidores de destino.

7.  Si no ha quitado previamente grupos de respuesta del grupo de origen, quite los grupos de respuesta del grupo de origen. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

