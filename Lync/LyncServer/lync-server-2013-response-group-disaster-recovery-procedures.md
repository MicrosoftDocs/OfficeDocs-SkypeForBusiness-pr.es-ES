---
title: Procedimientos de recuperación ante desastres del grupo de respuesta 2013 de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea967dc717f36b8ab5951fa758e7c78d6130dc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511667"
---
# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Durante la fase de conmutación por error de la recuperación ante desastres, los grupos de respuesta residen en varios grupos de servidores: en el grupo de servidores principal (que no está disponible) y en el grupo de servidores de reserva. Los grupos de respuesta de ambos grupos de servidores tienen el mismo nombre y el mismo propietario (el grupo de servidores principal), pero diferentes elementos primarios. Durante este tiempo, los cmdlets del grupo de respuesta funcionan de manera ligeramente distinta. Asegúrese de usar los parámetros como se especifica en el procedimiento siguiente. Para obtener más información sobre cómo funcionan los cmdlets durante la fase de conmutación por error, vea el artículo del blog NextHop "Lync Server 2013: recuperación de grupos de respuesta durante la recuperación ante desastres" en [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) . Este artículo del blog también se aplica a la versión publicada de Lync Server 2013.

Siga los pasos descritos en el siguiente procedimiento para preparar y realizar la recuperación ante desastres para el servicio de grupo de respuesta de Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Para la conmutación por error y conmutación por recuperación del grupo de respuesta

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Haga copias de seguridad periódicamente. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Durante una interrupción, después de la conmutación por error en el grupo de servidores de reserva, importe los grupos de respuesta al grupo de servidores de reserva. En la línea de comandos, escriba lo siguiente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Si desea reemplazar la configuración de nivel de aplicación del grupo de servidores de reserva por la configuración del grupo de servidores principal, incluya el parámetro ReplaceExistingSettings. Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Si no reemplaza la configuración del grupo de servidores de reserva y no se puede recuperar el grupo de servidores principal, se perderá la configuración del grupo de servidores principal. Para obtener más información, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planeación de la recuperación ante desastres del grupo de respuesta en Lync Server 2013</A>.

    
    </div>

4.  Compruebe que la importación se haya realizado correctamente. Para ello, muestre los grupos de respuesta importados. Los grupos de respuesta importados siguen siendo propiedad del grupo de servidores principal. Haga lo siguiente:
    
      - Muestre todos los flujos de trabajo del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los flujos de trabajo del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Muestre todas las colas del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todas las colas del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Muestre todos los grupos de agentes del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los grupos de agentes del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Muestre todo el horario comercial del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se haya incluido todo el horario comercial del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Muestre todos los conjuntos de vacaciones del grupo de servidores de reserva que son propiedad del grupo de servidores principal y compruebe que se hayan incluido todos los conjuntos de vacaciones del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    También puede mostrar todos los grupos de respuesta del grupo de servidores de reserva, incluidos los que son propiedad del grupo de servidores principal y los que son propiedad del grupo de servidores de reserva, con el parámetro –ShowAll en lugar del parámetro –Owner. Por ejemplo:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Debe usar el parámetro –ShowAll o el parámetro –Owner. Si no usa ninguno de estos parámetros, los grupos de respuesta importados al grupo de servidores de reserva no aparecerán en los resultados que devuelven los cmdlets.

    
    </div>

5.  Compruebe que la importación se haya realizado correctamente. Para ello, realice una llamada a un grupo de respuesta importado y compruebe que la llamada se atienda correctamente.

6.  Pida a los agentes que son miembros de grupos de agentes formales que inicien sesión en sus grupos de agentes en el grupo de servidores de reserva.

7.  Administre y modifique los grupos de respuesta importados de la manera habitual.
    
    <div>
    

    > [!IMPORTANT]  
    > Mientras los grupos de respuesta se encuentran en el grupo de copia de seguridad, debe usar el shell de administración de Lync Server para administrarlos. No puede usar el panel de control de Lync Server para administrar los grupos de respuesta que importó al grupo de copia de seguridad.

    
    </div>

8.  Una vez que se ha restaurado el grupo de servidores principal y se ha completado la conmutación por recuperación, exporte los grupos de respuesta del grupo de servidores principal que se importaron al grupo de servidores de reserva. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importe los grupos de respuesta nuevamente al grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Si vuelve a generar un grupo de servidores durante la recuperación, ya sea con el mismo nombre de dominio completo (FQDN) o con uno diferente, debe usar el parámetro –OverwriteOwner. Como regla general, siempre puede usar el parámetro –OverwriteOwner al importar grupos de respuesta nuevamente al grupo de servidores principal.

    
    </div>
    
    Si implementó un nuevo grupo de servidores (con el mismo FQDN o con uno diferente) para reemplazar el grupo de servidores principal, y desea usar la configuración de nivel de aplicación del grupo de servidores de reserva para el nuevo grupo, incluya el parámetro –ReplaceExistingSettings. En la línea de comandos, escriba lo siguiente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Si no desea reemplazar la configuración de nivel de aplicación ni el archivo de audio de música en espera predeterminado del nuevo grupo de servidores por la configuración del grupo de servidores de reserva, el nuevo grupo usará la configuración de nivel de aplicación predeterminada.

    
    </div>

10. Compruebe que la importación al grupo de servidores principal se haya realizado correctamente. Para ello, muestre la configuración del grupo de respuesta importado. Haga lo siguiente:
    
      - Muestre todos los flujos de trabajo del grupo de servidores principal y compruebe que se hayan incluido todos los flujos de trabajo importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Muestre todas las colas del grupo de servidores principal y compruebe que se hayan incluido todas las colas importadas. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Muestre todos los grupos de agentes del grupo de servidores principal y compruebe que se hayan incluido todos los grupos de agentes importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Muestre todo el horario comercial del grupo de servidores principal y compruebe que se haya incluido todo el horario comercial importado. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Muestre todos los conjuntos de vacaciones del grupo de servidores principal y compruebe que se hayan incluido todos los conjuntos de vacaciones importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Compruebe que la importación se haya realizado correctamente. Para ello, realice una llamada a un grupo de respuesta importado y compruebe que la llamada se atienda correctamente.

12. También puede quitar del grupo de servidores de reserva los grupos de respuesta que son propiedad del grupo de servidores principal. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Este paso crea un nuevo archivo con la configuración exportada y luego lo elimina del grupo de servidores de reserva.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

