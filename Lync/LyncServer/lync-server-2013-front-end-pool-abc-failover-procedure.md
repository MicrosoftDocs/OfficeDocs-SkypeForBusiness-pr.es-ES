---
title: 'Lync Server 2013: procedimiento de conmutación por error ABC del grupo de servidores front-end'
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
ms.openlocfilehash: f60ded6539f6d984662449562d0f978e98dc3078
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedimiento de conmutación por error ABC del grupo de servidores front-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-22_

Siga estos pasos para realizar el procedimiento de conmutación por error ABC. Este procedimiento contiene una descripción de alto nivel de cada paso, seguido de los comandos y los cmdlets que se van a ejecutar en cada paso.

Para ejecutar los cmdlets, abra un shell de administración de Lync Server con ejecutar como administrador.

<div>

## <a name="to-perform-an-abc-failover"></a>Para realizar una conmutación por error ABC

1.  Compruebe si el grupo de servidores es el host para el servidor de administración central (CMS).
    
      - Ejecute el siguiente cmdlet:
        
            Get-CsService -CentralManagement
        
        Si el campo identidad del CMS activo señala al nombre de dominio completo (FQDN) del grupo A, siga los pasos 2 y 3 de este procedimiento para realizar la conmutación por error primero en el servidor de administración central. De lo contrario, vaya al paso 4.

2.  Conmute por error el CMS al grupo B en modo de recuperación ante desastres, para ello, ejecute el siguiente cmdlet:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Después de hacerlo, le recomendamos que mueva el CMS del grupo B a otro grupo emparejado existente para obtener resistencia adicional. Para obtener más información, consulte [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Si el grupo A contiene CMS, importe la configuración de LIS del grupo A en la base de datos LIS del grupo B (LIS. MDF). Esto sólo funcionará si ha realizado una copia de seguridad de los datos de LIS de manera regular. Para importar la configuración de LIS, ejecute los siguientes cmdlets:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importación de copias de seguridad de los flujos de trabajo del servicio de grupo de respuesta de Lync Server del grupo A en el grupo B.
    
    <div>
    

    > [!NOTE]  
    > Actualmente, el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> requiere que los nombres de la cola y del flujo de trabajo del grupo a sean distintos de los nombres de la cola y del flujo de trabajo del grupo B. Si los nombres no son distintos, se producirá un error al ejecutar el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> y será necesario cambiar el nombre de las colas y flujos de trabajo en el grupo B antes de continuar con el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Tiene dos opciones para importar la configuración del grupo de respuesta del grupo A al grupo B. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo de servidores B con la configuración de nivel de aplicación en el grupo A.
    
      - Si desea sobrescribir la configuración del grupo B, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no desea sobrescribir la configuración del grupo B, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo de copia de seguridad (grupo B) con la configuración del grupo principal (grupo A), la configuración de nivel de aplicación del grupo A se perderá si se pierde el grupo A, ya que la aplicación del grupo de respuesta puede Almacene solo un conjunto de opciones de configuración de nivel de aplicación por grupo de servidores. Cuando se implementa el grupo C para reemplazar el grupo A, se debe volver a configurar la configuración del nivel de la aplicación, incluido el archivo de audio de música en espera predeterminado.

    
    </div>

5.  Compruebe que la importación de configuración del grupo de respuesta se haya realizado correctamente mediante la ejecución de los siguientes cmdlets para mostrar los grupos de respuesta importados. Tenga en cuenta que los grupos de respuesta importados todavía son propiedad del grupo A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Para los números sin asignar, mueva los intervalos de números sin asignar que usan "anuncio" como servicio de anuncio seleccionado del grupo A al grupo B. Para hacerlo:
    
      - Vuelva a crear todos los anuncios que se implementaron en el grupo A del grupo B. Si se usaron archivos de audio al implementar los anuncios en el grupo A, estos archivos serán necesarios para volver a crear los anuncios en el grupo B. Para volver a crear los anuncios en el grupo B, use los cmdlets **New-CsAnnouncement** con el grupo b como servicio primario.
    
      - Redestinar todos los intervalos de números sin asignar dirigidos a un anuncio del grupo A a los anuncios recién implementados en el grupo B. Ejecute el siguiente cmdlet para cada intervalo numérico sin asignar destinado a un anuncio del grupo A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Este paso no es necesario para los intervalos de números sin asignar que usan "mensajería unificada de Exchange" como servicio de anuncio seleccionado.

    
    </div>

7.  Conmute por error el grupo a al grupo B en modo de recuperación ante desastres (DR), ejecutando el siguiente cmdlet:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Cree el grupo de servidores C, pero no inicie ningún servicio en el grupo C.
    
    Tenga en cuenta que este paso se puede llevar a cabo simultáneamente con los pasos 5 y 6.

9.  Fuerce a los usuarios hospedados en el grupo A para que se muevan al grupo C ejecutando el siguiente cmdlet:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    En este momento, los usuarios hospedados en el grupo A empezarán a experimentar una interrupción del servicio. Esta interrupción continuará hasta el paso 16, momento en el que se inician los servicios en el grupo C.

10. Fuerce el directorio de conferencia del grupo a para que se mueva al grupo C ejecutando el siguiente cmdlet:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Fuerce el objeto de contacto operador automático de conferencia (CAA) para que desplace del grupo A al grupo C mediante la ejecución del siguiente cmdlet:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copie el contenido de la Conferencia del grupo B al grupo C.

13. Exportar datos de usuario desde el grupo B e importar los datos de usuario en el grupo de servidores C ejecutando los siguientes cmdlets:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaure la copia de seguridad de los datos de la aplicación de estacionamiento de llamadas del grupo a en el grupo C y asigne los intervalos de órbita de estacionamiento de llamadas del grupo a al grupo C.
    
      - Puede reasignar un intervalo de órbitas de estacionamiento de llamadas del grupo a al grupo C a través del panel de control de Lync Server o del shell de administración de Lync Server. Para el shell de administración de Lync Server, ejecute el siguiente cmdlet para cada intervalo de órbitas de estacionamiento de llamadas asignado al grupo a (tenga en cuenta que el parámetro Identity hace referencia a los intervalos de órbita de estacionamiento de llamadas que pertenecen al grupo a):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si se ha configurado una música en espera personalizada para el estacionamiento de llamadas en el grupo A, restaure el archivo de música en espera personalizado para el estacionamiento de llamadas en el grupo C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Por ejemplo:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Por último, vuelva a configurar las opciones de estacionamiento de llamadas en el grupo C mediante el cmdlet **set-CsCpsConfiguration** . La aplicación estacionamiento de llamadas solo puede almacenar un conjunto de opciones de configuración y un archivo de audio de música en espera personalizado por grupo de servidores, y no se realiza una copia de seguridad ni se conservan en el caso de un desastre.

15. Si el grupo del próximo salto del chat persistente apunta al grupo a, realice y publique los cambios de la topología para que el servidor del próximo salto apunte al grupo C.
    
      - En el generador de topologías, cambie el grupo de chat persistente para que apunte a grupo C como su próximo salto. Para ello, haga clic con el botón secundario en el grupo de chat persistente, haga clic en la pestaña **General** y, a continuación, escriba el nombre de grupo C en el grupo de servidores del **próximo salto**.
    
      - Inicie los servicios en el grupo de servidores C ejecutando el siguiente cmdlet:
        
            Start-csWindowsService
    
    En este punto, la interrupción del servicio finaliza para los usuarios hospedados originalmente en el grupo A.

16. Exporte los flujos de trabajo del servicio de grupo de respuesta de Lync Server del grupo B al que pertenece el grupo A para importarlos en el grupo C ejecutando el siguiente cmdlet:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importe los flujos de trabajo del servicio del grupo de respuesta de Lync Server en el grupo C del grupo B.
    
    Tiene dos opciones para importar la configuración del grupo de respuesta del grupo B al grupo C. La opción que use dependerá de si desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración de nivel de aplicación del grupo B.
    
      - Si desea sobrescribir la configuración C del grupo de servidores, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no desea sobrescribir la configuración C del grupo de servidores, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenga en cuenta que si no desea sobrescribir la configuración de nivel de aplicación del grupo C con la configuración del grupo de copia de seguridad (grupo B), la configuración del nivel de aplicación del grupo B se perderá porque la aplicación grupo de respuesta solo puede almacenar un conjunto de nivel de aplicación. configuración por grupo de servidores.

    
    </div>

18. Compruebe que la importación de configuración del grupo de respuesta se haya realizado correctamente mediante la ejecución de los siguientes cmdlets para mostrar los grupos de respuesta que se han importado al grupo de servidores C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Cuando se haya comprobado la configuración importada en el grupo C, quite los grupos de respuesta que pertenecen al grupo de servidores principal del grupo B. Esto reducirá el tiempo de inactividad de los grupos de respuesta.
    
    En este paso se crea un archivo nuevo con la configuración exportada y, a continuación, se quita el archivo del grupo B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Mover a grupo C los intervalos de números sin asignar que se movieron del grupo A al grupo B.
    
      - Vuelva a crear en el grupo C todos los anuncios que se han vuelto a crear a partir del grupo A en el grupo B. Si se usaron archivos de audio al implementar los anuncios que se moverán, tendrá que usar estos archivos para volver a crear los anuncios en el grupo de servidores C. Para volver a crear los anuncios en el grupo C, use los cmdlets **New-CsAnnouncement** , con el grupo c como servicio primario.
    
      - Redestinar al grupo C todos los intervalos de números sin asignar que se redestinaron del grupo A al grupo B. Ejecute el siguiente cmdlet para cada intervalo de números sin asignar que deba redestinarse:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Opcional Quite del grupo B los anuncios que se han vuelto a crear en el grupo C si ya no se usan en el grupo B. Para quitar anuncios, use el cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Este paso no es necesario para los intervalos de números sin asignar que usan "mensajería unificada de Exchange" como servicio de anuncio.

        
        </div>

21. Limpie los datos de usuario del grupo A en el grupo B ejecutando el siguiente cmdlet:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Haga lo siguiente en el generador de topologías:
    
      - Desemparejar el grupo A y el grupo B. emparejar grupo B y grupo C. A continuación, quite el grupo A de la topología y publíquelo. Para ello:
        
          - En el generador de topologías, haga clic con el botón secundario en grupo B y, a continuación, haga clic en **Editar propiedades**.
        
          - Haga clic en **resistencia** en el panel izquierdo.
        
          - En el cuadro que se encuentra a continuación del **grupo de copia de seguridad asociado**, seleccione grupo C. tenga en cuenta que el cuadro de selección del grupo de copia de seguridad asociado mostrará inicialmente el grupo a, porque el grupo B estaba asociado anteriormente a este grupo.
        
          - Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y haga clic en **Aceptar**.
            
            Cuando visualice los detalles sobre este grupo, el grupo asociado aparecerá en el panel derecho bajo **Resistencia**.
        
          - En el árbol de consola, haga clic con el botón secundario en Pool A y, a continuación, haga clic en eliminar.
        
          - Publique la topología.

23. Ejecute la aplicación de programa previo en el grupo C para instalar la aplicación de servicio de copia de seguridad y, a continuación, inicie la aplicación de servicio de copia de seguridad ejecutando lo siguiente desde la carpeta de implementación en un equipo local en el grupo C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Reinicie la aplicación de servicio de copia de seguridad en el grupo B; para ello, ejecute los siguientes cmdlets:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Si el grupo C es un grupo de servidores Standard Edition (SE) y el grupo B tiene CMS, instale la base de datos de CMS manualmente en el grupo C ejecutando el siguiente cmdlet:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Invocar el servicio de copia de seguridad para sincronizar el contenido de conferencia antiguo del grupo B al grupo C que se generó antes de emparejar B y C, y para sincronizar el nuevo contenido de conferencia desde el grupo C al grupo B que se generó después de iniciar el grupo C y antes de que se emparejaran los dos. Para ello, ejecute los siguientes cmdlets:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Para cada aplicación de sucursal con funciones de supervivencia asociada con el grupo A:
    
      - Para apagar SBA X, ejecute el siguiente cmdlet:
        
            Stop-CsWindowsService
    
      - Cree un archivo que contenga una lista de usuarios hospedados en SBA X. La lista será necesaria cuando los usuarios se muevan de nuevo a SBA X en el paso 30. Para ello, ejecute el siguiente cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Fuerce que los usuarios hospedados en SBA X se muevan al grupo C ejecutando el siguiente cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Actualice los datos de estos usuarios ejecutando primero los siguientes cmdlets:
        
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
        > Se producirá una interrupción del servicio para los usuarios hospedados en las asociados al grupo A hasta que estos usuarios se muevan al grupo C.

        
        </div>

28. En el generador de topologías, para cada X de SBA asociada anteriormente con el grupo A, haga lo siguiente:
    
      - Cambie la asociación al grupo C. Para ello, haga clic en el sitio de sucursal, expanda el nodo servidores y aplicaciones de sucursal con funciones de supervivencia y haga clic en **aplicación de sucursal**con funciones de supervivencia. A continuación, seleccione el grupo de **servidores front-end, el grupo de servicios de usuario** al que se conectará esta aplicación de sucursal con funciones de supervivencia como grupo C y haga clic en **siguiente**.
    
      - Publique la topología. Para ello, en el árbol de la consola, haga clic con el botón secundario en la nueva **aplicación de sucursal**con funciones de supervivencia, haga clic en **topología**y, a continuación, en **publicar**.

29. Para cada X de SBA ahora asociada con el grupo de servidores C:
    
      - Inicie SBA X ejecutando el siguiente cmdlet en la aplicación de sucursal con funciones de supervivencia:
        
            Start-CsWindowsService
    
      - Mueva los usuarios que se hospedaban originalmente en SBA X del grupo C a SBA X ejecutando el siguiente cmdlet.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

