---
title: 'Lync Server 2013: Procedimientos de recuperación ante desastres del grupo de respuesta'
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
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procedimientos de recuperación ante desastres del grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Durante la fase de conmutación por error de recuperación ante desastres, los grupos de respuesta residen en varios grupos: en el grupo primario (que no está disponible) y en el grupo de copias de seguridad. Los grupos de respuesta de ambos grupos tienen el mismo nombre y el mismo propietario (el grupo principal), pero tienen diferentes padres. Durante este tiempo, los cmdlets del grupo de respuesta funcionan de manera algo diferente. Asegúrese de usar parámetros según se especifica en el procedimiento siguiente. Para más información sobre cómo funcionan los cmdlets durante la fase de conmutación por error, vea el artículo del blog de NextHop "Lync Server 2013: [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)recuperación de grupos de respuesta durante la recuperación ante desastres" en. Este artículo del blog también se aplica a la versión de lanzamiento de Lync Server 2013.

Siga los pasos que se indican en el siguiente procedimiento para preparar y realizar la recuperación de desastres para el servicio de grupo de respuesta de Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Para deshacer la conmutación por error y el grupo de respuesta failback

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Realizar copias de seguridad rutinariamente. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Durante una interrupción, después de la conmutación por error en el grupo de copias de seguridad, importe los grupos de respuesta al grupo de copia de seguridad. En la línea de comandos, escriba:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Si desea reemplazar la configuración de nivel de aplicación del grupo de copias de seguridad por la configuración del grupo principal, incluya el parámetro – ReplaceExistingSettings. Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Si no reemplaza la configuración del grupo de copias de seguridad y no se puede recuperar el repositorio principal, se perderá la configuración de la agrupación principal. Para obtener más información, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planeación de la recuperación ante desastres de grupos de respuesta en Lync Server 2013</A>.

    
    </div>

4.  Compruebe que la importación se ha realizado correctamente; para ello, muestra los grupos de respuesta importados. Los grupos de respuesta importados siguen siendo propiedad del grupo primario. Siga este procedimiento:
    
      - Mostrar todos los flujos de trabajo del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los flujos de trabajo de grupo primario. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Muestre todas las colas del grupo de copia de seguridad que pertenecen al grupo principal y compruebe que se incluyen todas las colas de grupo principales. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Mostrar todos los grupos de agentes del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los grupos de agentes de grupo principales. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Mostrar todas las horas de actividad en el grupo de copia de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los horarios de negocio principales de la agrupación. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Mostrar todos los conjuntos de días no laborables del grupo de copias de seguridad que pertenecen al grupo principal y comprobar que se incluyen todos los conjuntos de días no laborables de la agrupación principal. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por ejemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Como alternativa, puede mostrar todos los grupos de respuesta en el grupo de copias de seguridad, incluidos los que pertenecen al grupo principal y los que pertenecen al grupo de copias de seguridad, con el parámetro – ShowAll en lugar del parámetro – Owner. Por ejemplo:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Debe usar el parámetro – ShowAll o el parámetro-Owner. Si no usa ninguno de estos parámetros, los grupos de respuesta que importó al grupo de copias de seguridad no se mostrarán en los resultados devueltos por los cmdlets.

    
    </div>

5.  Verifique que la importación se haya realizado correctamente colocando una llamada a un grupo de respuesta importado y verificando que la llamada se controla correctamente.

6.  Solicitar agentes que sean miembros de grupos de agentes formales para iniciar sesión en sus grupos de agentes en el grupo de copias de seguridad.

7.  Administrar y modificar los grupos de respuesta importados de la forma habitual.
    
    <div>
    

    > [!IMPORTANT]  
    > Mientras los grupos de respuesta están en el grupo de copia de seguridad, necesita usar el shell de administración de Lync Server para administrarlos. No puede usar el panel de control de Lync Server para administrar los grupos de respuesta que importó al grupo de copias de seguridad.

    
    </div>

8.  Una vez que se haya restaurado el grupo principal y se haya completado la conmutación por recuperación, exporte los grupos de respuesta del grupo principal que se importaron al grupo de copias de seguridad. En la línea de comandos, escriba:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Vuelva a importar los grupos de respuesta al grupo primario. En la línea de comandos, escriba lo siguiente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Si reconstruye un grupo durante la recuperación, ya sea con el mismo nombre de dominio completo (FQDN) u otro diferente, debe usar el parámetro – OverwriteOwner. Como regla general, siempre puede usar el parámetro – OverwriteOwner al importar grupos de respuesta al grupo primario.

    
    </div>
    
    Si implementó un nuevo grupo (con el mismo FQDN u otro diferente) para reemplazar el grupo primario y desea usar la configuración de nivel de aplicación del grupo de copias de seguridad para el nuevo grupo, incluya el parámetro – ReplaceExistingSettings. En la línea de comandos, escriba lo siguiente:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Si no quiere reemplazar la configuración de nivel de aplicación y el archivo de audio de música en espera predeterminado para el nuevo grupo con la configuración del grupo de copias de seguridad, el nuevo grupo usará la configuración predeterminada de nivel de aplicación.

    
    </div>

10. Compruebe que la importación al grupo primario se ha realizado correctamente mostrando la configuración del grupo de respuesta importado. Siga este procedimiento:
    
      - Mostrar todos los flujos de trabajo del grupo principal y comprobar que se incluyen todos los flujos de trabajo importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Muestre todas las colas del grupo principal y compruebe que todas las colas importadas están incluidas. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Mostrar todos los grupos de agentes en el repositorio principal y comprobar que se incluyen todos los grupos de agentes importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Mostrar todas las horas de actividad en el grupo primario y comprobar que se incluyen todos los horarios de negocios importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Mostrar todos los conjuntos de días no laborables del repositorio principal y comprobar que están incluidos todos los conjuntos de festividades importados. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por ejemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Verifique que la importación se haya realizado correctamente colocando una llamada a un grupo de respuesta importado y verificando que la llamada se controla correctamente.

12. Si lo desea, puede quitar los grupos de respuesta que pertenecen al grupo principal del grupo de copias de seguridad. En la línea de comandos, escriba lo siguiente:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Este paso crea un nuevo archivo con la configuración exportada y, a continuación, lo quita del grupo de copia de seguridad.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

