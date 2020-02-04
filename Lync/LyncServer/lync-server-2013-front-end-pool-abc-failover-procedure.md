---
title: 'Lync Server 2013: Procedimiento de conmutación por error de ABC del grupo de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedimiento de conmutación por error de ABC del grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-22_

Siga estos pasos para realizar el procedimiento de conmutación por error ABC. Este procedimiento contiene una descripción de alto nivel de cada paso seguida de comandos y cmdlets para cada paso.

Para ejecutar los cmdlets, abra un shell de administración de Lync Server con ejecutar como administrador.

<div>

## <a name="to-perform-an-abc-failover"></a>Para realizar una conmutación por error ABC

1.  Compruebe si el grupo A es el host del servidor de administración central (CMS).
    
      - Ejecute el siguiente cmdlet:
        
            Get-CsService -CentralManagement
        
        Si el campo Identity del CMS activo apunta al nombre de dominio completo (FQDN) del grupo A, siga los pasos 2 y 3 de este procedimiento para realizar la conmutación por error primero en el servidor de administración central. En caso contrario, vaya al paso 4.

2.  Conmutar por error el CMS al grupo B en modo de recuperación de desastres ejecutando el siguiente cmdlet:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Después de hacerlo, le recomendamos que mueva el CMS del grupo B a otro grupo emparejado existente para obtener resistencia adicional. Para obtener más información, consulte [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Si el grupo A contiene CMS, importe la configuración de LIS del grupo A en la base de datos LIS del grupo B (LIS. MDF). Esto funcionará solo si ha realizado una copia de seguridad de los datos de LIS de forma regular. Para importar la configuración de LIS, ejecute los siguientes cmdlets:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importar flujos de trabajo de copia de seguridad del servicio del grupo de respuesta de Lync Server del grupo A al grupo B.
    
    <div>
    

    > [!NOTE]  
    > En este momento, el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> requiere que los nombres de la cola y del flujo de trabajo del grupo a sean distintos de los nombres de la cola y del flujo de trabajo del grupo B. Si los nombres no son distintos, recibirá un error al ejecutar el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> y las colas y los flujos de trabajo deberán cambiar de nombre en el grupo B antes de continuar con el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Tiene dos opciones para importar la configuración del grupo de respuesta desde el grupo A al grupo B. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo de servidores B con la configuración de nivel de aplicación en el grupo A.
    
      - Si desea sobrescribir la configuración del grupo B, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no desea sobrescribir la configuración del grupo B, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo de copias de seguridad (grupo B) con la configuración del grupo principal (grupo A), la configuración de nivel de aplicación del grupo A se perderá si se pierde el grupo A, porque la aplicación de grupo de respuesta puede Almacene solo un conjunto de opciones de configuración de nivel de aplicación por grupo. Cuando se implementa el grupo C para reemplazar el grupo A, se debe volver a configurar la configuración del nivel de aplicación, incluido el archivo de audio de música en espera predeterminado.

    
    </div>

5.  Compruebe que la importación de configuración del grupo de respuesta se ha realizado correctamente ejecutando los siguientes cmdlets para mostrar los grupos de respuesta importados. Observe que los grupos de respuesta importados siguen siendo propiedad del grupo A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  En el caso de números no asignados, mueva los rangos de números sin asignar que usan "anuncio" como el servicio de anuncios seleccionado del grupo A al grupo B. Para ello, haga lo siguiente:
    
      - Vuelva a crear todos los anuncios que se han implementado en el grupo A del grupo B. Si se usaron archivos de audio al implementar los anuncios en el grupo A, se necesitarán estos archivos para volver a crear los anuncios en el grupo B. Para volver a crear los anuncios en el grupo B, use los cmdlets **New-CsAnnouncement** con el grupo b como servicio principal.
    
      - Redestinar todos los intervalos de números no asignados dirigidos a un anuncio en el grupo A para los anuncios recién implementados en el grupo B. Ejecute el siguiente cmdlet para cada intervalo de números no asignado dirigido a un anuncio del grupo A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Este paso no es necesario para intervalos de números no asignados que usan "mensajería unificada de Exchange" como servicio de anuncios seleccionado.

    
    </div>

7.  Conmuta por error al grupo B en el modo de recuperación ante desastres (DR) ejecutando el siguiente cmdlet:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Cree el grupo C, pero no inicie ningún servicio en el grupo C.
    
    Tenga en cuenta que este paso se puede llevar a cabo de forma simultánea con los pasos 5 y 6.

9.  Forzar a los usuarios alojados en el grupo a para que se muevan al grupo C ejecutando el siguiente cmdlet:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    En este momento, los usuarios alojados en el grupo A comenzarán a experimentar una interrupción del servicio. Esta interrupción continuará hasta el paso 16, a la que se inician los servicios en el pool C.

10. Fuerce el directorio de la Conferencia del grupo a para que se mueva al grupo C ejecutando el siguiente cmdlet:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Haga que el objeto de contacto operador automático de la Conferencia (CAA) se mueva del grupo a al grupo C ejecutando el siguiente cmdlet:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copie el contenido de la Conferencia desde el grupo B al grupo C.

13. Exportar los datos de usuario del grupo B e importar los datos de usuario en el grupo C ejecutando los siguientes cmdlets:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaure la copia de seguridad de los datos de la aplicación de estacionamiento desde el grupo A en el grupo C y asigne los intervalos órbita de la llamada estacionamiento de la cola a al grupo C.
    
      - Puede reasignar un rango de llamada estacionamiento orbital de la agrupación a en el grupo C a través del panel de control de Lync Server o del shell de administración de Lync Server. Para el shell de administración de Lync Server, ejecute el siguiente cmdlet para cada rango de la órbita de la llamada que se asigna al grupo a (tenga en cuenta que el parámetro Identity hace referencia a los intervalos de las llamadas en la órbita que pertenecen al grupo a):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si se ha configurado una música en espera personalizada para el servicio de estacionamiento en el grupo A, restaure el archivo de música en espera personalizado de la llamada en el pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Por ejemplo:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Por último, vuelva a configurar la configuración de estacionamiento de llamadas en el grupo C mediante el cmdlet **set-CsCpsConfiguration** . La aplicación de estacionamiento de llamadas solo puede almacenar un conjunto de opciones de configuración y un archivo de audio de música activada en espera personalizado por grupo, y no se hace una copia de seguridad de estos valores ni se conservan en el caso de un desastre.

15. Si el siguiente grupo de saltos de chat persistente apunta al grupo A, realice y publique cambios de topología para que el servidor del próximo salto apunte al grupo C.
    
      - En el generador de topología, cambie el grupo de chats persistentes para que apunte a la sección C como su próximo salto. Para ello, haga clic con el botón secundario en el grupo de chats persistentes, luego haga clic en la pestaña **General** y, por último, escriba el nombre del grupo C en el **grupo de siguiente saltos**.
    
      - Inicie los servicios en el conjunto de servidores C ejecutando el siguiente cmdlet:
        
            Start-csWindowsService
    
    En este punto, finaliza la interrupción del servicio para los usuarios alojados originalmente en el grupo A.

16. Exportar los flujos de trabajo del servicio de grupo de respuesta de Lync Server desde el grupo B al que pertenece el grupo A para importarlos en el grupo C ejecutando el siguiente cmdlet:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importar los flujos de trabajo del servicio del grupo de respuesta de Lync Server en el grupo C del grupo B.
    
    Tiene dos opciones para importar la configuración del grupo de respuesta del grupo B al grupo C. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración de nivel de la aplicación en el grupo de servidores B.
    
      - Si desea sobrescribir la configuración del grupo C, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no desea sobrescribir la configuración del grupo C, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración del grupo de copias de seguridad (grupo B), la configuración de nivel de aplicación del grupo B se perderá porque la aplicación de grupo de respuesta solo puede almacenar un conjunto de nivel de aplicación. configuración por grupo.

    
    </div>

18. Compruebe que la importación de configuración del grupo de respuesta se ha realizado correctamente ejecutando los siguientes cmdlets para mostrar los grupos de respuesta que se han importado al grupo de servidores C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Cuando se haya comprobado la configuración importada en el grupo C, quite los grupos de respuesta que pertenecen al grupo principal del grupo B. Esto minimizará el tiempo de inactividad de los grupos de respuesta.
    
    En este paso se crea un nuevo archivo con la configuración exportada y, a continuación, se quita el archivo del grupo B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Mover a la sección C los intervalos de números sin asignar que se movieron del grupo A al grupo B.
    
      - Vuelva a crear en el grupo C todos los anuncios que se han vuelto a crear a partir del grupo A en el grupo B. Si se usaron archivos de audio al implementar los anuncios que se van a mover, tendrá que usar estos archivos para volver a crear los anuncios en el grupo C. Para volver a crear los anuncios en el grupo C, use los cmdlets **New-CsAnnouncement** , con el grupo c como servicio principal.
    
      - Redestinar al grupo C todos los intervalos de números no asignados que se han redestinado del grupo A al grupo B. Ejecute el siguiente cmdlet para cada intervalo de números no asignado que deba redestinarse:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Faculta Quitar del grupo de servidores B los anuncios que se han vuelto a crear en el grupo C si ya no se usan en el grupo B. Para quitar anuncios, use el cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Este paso no es necesario para intervalos de números no asignados que usan "mensajería unificada de Exchange" como servicio de anuncios.

        
        </div>

21. Limpie los datos de usuario del grupo A en el grupo B ejecutando el siguiente cmdlet:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Haga lo siguiente en el generador de topología:
    
      - Desemparejar el grupo A y el grupo B. emparejar grupo B y grupo C. A continuación, quite el grupo A de la topología y publíquelo. Para ello, realice lo siguiente:
        
          - En el generador de topología, haga clic con el botón secundario en Pool B y, a continuación, haga clic en **Editar propiedades**.
        
          - Haga clic en **resistencia** en el panel de la izquierda.
        
          - En el cuadro que se encuentra debajo de **grupo de copia de seguridad asociado**, seleccione Pool C. Observe que el cuadro de selección de grupo de copia de seguridad asociado mostrará inicialmente el grupo a, porque el grupo B se asoció previamente con este grupo.
        
          - Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y después haga clic en **Aceptar**.
            
            Cuando vea los detalles de este grupo, el grupo asociado aparecerá en el panel derecho debajo de **Resistencia**. 
        
          - En el árbol de consola, haga clic con el botón secundario en Pool A y, a continuación, haga clic en eliminar.
        
          - Publique la topología.

23. Ejecute la aplicación de programa previo en el pool C para instalar la aplicación de servicio de copia de seguridad y, a continuación, inicie la aplicación de servicio de copia de seguridad ejecutando lo siguiente desde la carpeta de implementación en un equipo local en el grupo C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Ejecute los siguientes cmdlets para reiniciar la aplicación de servicio de copia de seguridad en el grupo B:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Si el grupo C es un grupo de servidores Standard Edition (SE) y el grupo B tiene CMS, instale la base de datos de CMS manualmente en el grupo C ejecutando el siguiente cmdlet:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Invocar el servicio de copia de seguridad para sincronizar el contenido de las conferencias antiguas del grupo B al C generado antes de emparejar B y C, y para sincronizar el nuevo contenido de la Conferencia desde el grupo C al grupo B que se generó después de iniciar el grupo C y antes de que se emparejaran B y C. Para ello, ejecute los siguientes cmdlets:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Para cada rama de equipo de la aplicación X asociada con el grupo A:
    
      - Para apagar SBA X, ejecute el siguiente cmdlet:
        
            Stop-CsWindowsService
    
      - Cree un archivo que contenga una lista de usuarios alojados en SBA X. La lista será necesaria cuando los usuarios vuelvan a pasar a SBA X en el paso 30. Para ello, ejecute el siguiente cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Fuerce que los usuarios alojados en SBA X se muevan a la sección C ejecutando el siguiente cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Actualice los datos de estos usuarios ejecutando primero los cmdlets siguientes:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Y, a continuación, ejecute este script:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Se producirá una interrupción del servicio para los usuarios que estén alojados en SBAs asociados al grupo A hasta que estos usuarios se muevan al grupo C.

        
        </div>

28. En el generador de topologías, para cada X de SBA asociada previamente al grupo A, haga lo siguiente:
    
      - Cambie la asociación al grupo C. Para ello, haga clic en el sitio de la sucursal, expanda el nodo de las sucursales o servidores supervivientes y haga clic en **aplicación de rama superviviente**. A continuación, seleccione el **grupo de servidores front-end, el grupo de servicios de usuario** al que se conectará este equipo con el grupo C y, a continuación, haga clic en **siguiente**.
    
      - Publique la topología. Para ello, en el árbol de consola, haga clic con el botón secundario del ratón en el nuevo **equipo de sucursal con supervivencia**, haga clic en **topología**y, a continuación, haga clic en **publicar**.

29. Para cada X de SBA asociada ahora con el grupo C:
    
      - Inicie SBA X ejecutando el siguiente cmdlet en el dispositivo de rama superviviente:
        
            Start-CsWindowsService
    
      - Mueva los usuarios que hayan alojado originalmente en SBA X del bloque C a SBA X ejecutando el siguiente cmdlet.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

