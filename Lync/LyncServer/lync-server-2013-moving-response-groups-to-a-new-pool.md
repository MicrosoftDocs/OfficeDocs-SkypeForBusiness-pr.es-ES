﻿---
title: Desplazamiento de grupos de respuesta a un grupo nuevo de servidores
TOCTitle: Desplazamiento de grupos de respuesta a un grupo nuevo de servidores
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48276860
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Desplazamiento de grupos de respuesta a un grupo nuevo de servidores

 

_**Última modificación del tema:** 2012-11-01_

Lync Server 2013 introduce una nueva compatibilidad de cmdlet para mover grupos de respuesta de un grupo de servidores a otro grupo de servidores, aunque el nombre de dominio completo (FQDN) sea diferente.

Ejecute los pasos del procedimiento siguiente para mover grupos de respuesta de de una instancia de Grupo de servidores front-end a una instancia diferente de Grupo de servidores front-end con un FQDN diferente.


> [!NOTE]
> En un entorno de coexistencia, solo puede mover grupos de respuesta entre Lync Server 2013Grupos de servidores front-end.



## Para mover grupos de respuesta a un grupo de servidores con un FQDN diferente

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Exporte los grupos de respuesta del grupo de servidores de origen. En la línea de comandos, escriba:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Para quitar los grupos de respuesta del grupo de servidores durante la exportación, incluya el parámetro –RemoveExportedConfiguration. Por ejemplo:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importe los grupos de respuesta al grupo de servidores de destino y asigne el grupo de destino como nuevo propietario. En la línea de comandos, escriba:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Si también quiere copiar la configuración de nivel de aplicación de Grupo de respuesta del grupo de servidores de origen en el grupo de servidores de destino, incluya el parámetro –ReplaceExistingSettings. Defina solo un conjunto de configuraciones de nivel de aplicación por grupo de servidores. Si copia la configuración de nivel de aplicación del grupo de servidores de origen en el grupo de servidores de destino, la configuración del grupo de servidores de origen sustituirá la configuración del grupo de servidores de destino. Si no copia la configuración de nivel de aplicación del grupo de servidores de origen, la configuración existente del grupo de servidores de destino se aplicará a los grupos de respuesta importados.
    
    Por ejemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingSettings
    

    > [!NOTE]
    > La configuración de nivel de aplicación incluye la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de la llamada. Para ver los valores de la configuración, ejecute el cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>. Para más información sobre el cmdlet, vea <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.



4.  Compruebe que la importación haya sido correcta visualizando la configuración del grupo de respuesta importado tal como indicamos a continuación:
    
      - En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Compruebe que se hayan importado todas las colas. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Compruebe que se hayan importado todos los grupos de agentes. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Compruebe que se hayan importado todos los horarios laborales. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Compruebe que se hayan importado todos los conjuntos de vacaciones. En la línea de comandos, escriba lo siguiente:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Compruebe que la importación haya tenido éxito realizando una llamada a uno de los grupos de respuesta y verificando que la llamada se ha gestionado correctamente.

6.  Solicite a los agentes que son miembros de grupos de agentes formales que inicien sesión en sus grupos de agentes en el grupo de servidores de destino.

7.  Si no ha quitado previamente grupos de respuesta del grupo de servidores de origen, hágalo ahora. En la línea de comandos, escriba:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Por ejemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

