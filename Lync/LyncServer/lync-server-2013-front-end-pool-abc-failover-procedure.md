---
title: 'Lync Server 2013: Procedimiento conmut. error de ABC de grupo de servidores front-end'
TOCTitle: Procedimiento de conmutación por error de ABC del grupo de servidores front-end
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945635(v=OCS.15)
ms:contentKeyID: 52061696
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procedimiento de conmutación por error de ABC del grupo de servidores front-end en Lync Server 2013

 

_**Última modificación del tema:** 2014-05-22_

Haga lo siguiente para llevar a cabo un procedimiento de conmutación por error de ABC. Este procedimiento contiene una descripción detallada de cada paso, así como de los comandos y cmdlets que hay que ejecutar en cada paso.

Para ejecutar los cmdlets, use Ejecutar como administrador y abra un Shell de administración de Lync Server.

## Para hacer una conmutación por error de ABC

1.  Compruebe si el grupo A es el host del servidor de administración central (CMS).
    
      - Ejecute el siguiente cmdlet:
        
            Get-CsService -CentralManagement
        
        Si el campo de identidad del CMS activo apunta al nombre de dominio completo (FQDN) del grupo A, siga los pasos 2 y 3 de este procedimiento para conmutar por error el servidor de administración central en primer lugar. De lo contrario, vaya al paso 4.

2.  Conmute por error el CMS al grupo B en modo de recuperación ante desastres con el siguiente cmdlet:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Una vez hecho, le recomendamos que mueva el CMS desde el grupo B a otro grupo asociado existente a fin de lograr mayor resistencia. Para más información, consulte [Move-CsManagementServer](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsManagementServer).

3.  Si el grupo A contiene el CMS, importe la configuración LIS desde el grupo A a la base de datos LIS del grupo B (Lis.mdf). Esto solo funcionará si ha hecho copias de seguridad de los datos de LIS periódicamente. Para importar la configuración de LIS, ejecute los siguientes cmdlets:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importe los flujos de trabajo del servicio Grupo de respuesta de Lync Server (de los que se ha hecho una copia de seguridad) desde el grupo A al grupo B.
    

    > [!NOTE]
    > Actualmente, el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> exige que la cola y el flujo de trabajo del grupo A tengan unos nombres distintos a los de la cola y el flujo de trabajo del grupo B. Si los nombres son iguales, se producirá un error al ejecutar el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> y habrá que cambiar los nombres del grupo B antes de poder continuar con el cmdlet <STRONG>Import-CsRgsConfiguration</STRONG>.

    
    Hay dos opciones para importar la configuración del grupo de respuesta desde el grupo A al grupo B. La opción que elija dependerá de si quiere sobrescribir la configuración de nivel de aplicación del grupo B con la configuración de nivel de aplicación del grupo A.
    
      - Si quiere sobrescribir la configuración del grupo B, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings**:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no quiere sobrescribir la configuración del grupo B, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings**.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]  
    > Tenga en cuenta que si no quiere sobrescribir la configuración de nivel de aplicación del grupo de copia de seguridad (grupo B) con la configuración del grupo principal (grupo A), la configuración del grupo A se perderá si se pierde el grupo. Esto se debe a que la aplicación Grupo de respuesta solo puede almacenar una configuración de nivel de aplicación por grupo. Al implementar el grupo C para sustituir al grupo A, es necesario reconfigurar la configuración de nivel de aplicación, incluido el archivo de audio predeterminado de música en espera.
    


5.  Verifique que la configuración del grupo de respuesta se importó correctamente: ejecute los siguientes cmdlets para ver los grupos de respuesta importados. Tenga en cuenta que los grupos de respuesta importados todavía pertenecen al grupo A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Para números no asignados, mueva desde al grupo A al grupo B los intervalos de números no asignados que usen “Anuncio” como el servicio de anuncio seleccionado. Para ello:
    
      - Vuelva a crear en el grupo B todos los anuncios que se implementaron en el grupo A. Si al implementar los anuncios en el grupo A se usaron archivos de audio, estos archivos serán necesarios para volver a crear los anuncios en el grupo B. Para crear los anuncios en el grupo B, use los cmdlets **New-CsAnnouncement**, con el grupo B como servicio principal.
    
      - Redestine todos los intervalos de números no asignados que estén destinados a un anuncio del grupo A y destínelos a los anuncios que se acaban de implementar en el grupo B. Ejecute el cmdlet siguiente para cada intervalo de números no asignados que esté destinado a un anuncio del grupo A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    

    > [!NOTE]
    > Este paso no es necesario con intervalos de números no asignados cuyo servicio de anuncio seleccionado sea “Mensajería unificada de Exchange”.



7.  Conmute por error el grupo A al grupo B en modo de recuperación ante desastres (DR). Para ello, ejecute el siguiente cmdlet:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Compile el grupo C, pero no inicie ningún servicio en él.
    
    Tenga en cuenta que este paso se puede llevar a cabo al mismo tiempo que los pasos 5 y 6.

9.  Obligue a los usuarios alojados en el grupo A a desplazarse al grupo C con el cmdlet siguiente:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    En este momento, los usuarios alojados en el grupo A empezarán a experimentar una interrupción en el servicio que durará hasta el paso 16, momento en el que se iniciarán los servicios en el grupo C.

10. Obligue al directorio de conferencia del grupo A a desplazarse al grupo C con el cmdlet siguiente:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Obligue al objeto de contacto del operador automático de conferencia (CAA) a desplazarse del grupo A al grupo C con el cmdlet siguiente:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copie el contenido de conferencias del grupo B en el grupo C.

13. Exporte los datos de usuarios del grupo B e impórtelos en el grupo C con los siguientes cmdlets:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaure en el grupo C los datos de la aplicación Estacionamiento de llamadas del grupo A (de los que se ha hecho una copia de seguridad) y asigne al grupo C los intervalos de órbitas del Estacionamiento de llamadas del grupo A.
    
      - Los intervalos de órbitas del Estacionamiento de llamadas del grupo A pueden reasignarse al grupo C a través del Panel de control de Lync Server o del Shell de administración de Lync Server. Si usa este último, ejecute el siguiente cmdlet para cada intervalo de órbitas del Estacionamiento de llamadas asignado al grupo A (tenga en cuenta que el parámetro Identidad hace referencia a los intervalos de órbitas del Estacionamiento de llamadas que pertenecen al grupo A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Si se ha configurado un archivo personalizado de música en espera para el Estacionamiento de llamadas del grupo A, restaure el archivo en el grupo C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Por ejemplo:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Por último, vuelva a configurar el Estacionamiento de llamadas en el grupo C con el cmdlet **Set-CsCpsConfiguration**. La aplicación Estacionamiento de llamadas puede almacenar una sola configuración y un solo archivo de audio de música en espera por grupo. La configuración no puede guardarse en una copia de seguridad ni se conserva en caso de desastre.

15. Si el grupo de próximo salto de Chat persistente apunta al grupo A, cambie la topología y publique los cambios para que el servidor de próximo salto apunte al grupo C.
    
      - En el Generador de topologías, cambie el grupo Chat persistente para que apunte al grupo C como su próximo salto. Para ello, haga clic con el botón secundario en el grupo Chat persistente, haga clic en la pestaña **General** y después escriba el nombre del grupo C en **Grupo de servidores del próximo salto** .
    
      - Inicie los servicios en el grupo C con el siguiente cmdlet:
        
            Start-csWindowsService
    
    En este momento finaliza la interrupción del servicio para los usuarios que estaban alojados en un principio en el grupo A.

16. Exporte los flujos de trabajo del servicio Grupo de respuesta de Lync Server desde el grupo B propiedad del grupo A para luego importarlos al grupo C. Para ello, ejecute el siguiente cmdlet:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importe los flujos de trabajo del servicio Grupo de respuesta de Lync Server desde el grupo B al grupo C.
    
    Hay dos opciones para importar la configuración del grupo de respuesta desde el grupo B al grupo C. La opción que elija dependerá de si quiere sobrescribir la configuración de nivel de aplicación del grupo C con la configuración de nivel de aplicación del grupo B.
    
      - Si quiere sobrescribir la configuración del grupo C, ejecute el cmdlet **Import-CsRgsConfiguration** con la opción **ReplaceExistingSettings**:
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Si no quiere sobrescribir la configuración del grupo C, use el cmdlet **Import-CsRgsConfiguration** sin la opción **ReplaceExistingSettings**.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    > [!WARNING]  
    > Tenga en cuenta que si no quiere sobrescribir la configuración de nivel de aplicación del grupo C con la configuración de grupo de copia de seguridad (grupo B), la configuración del grupo B se perderá. Esto se debe a que la aplicación Grupo de respuesta solo puede almacenar una configuración de nivel de aplicación por grupo.
    


18. Verifique que la configuración del grupo de respuesta se importó correctamente: ejecute los siguientes cmdlets para ver los grupos de respuesta que se han importado al grupo C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Una vez que se haya verificado la configuración en el grupo C, quite del grupo B los grupos de respuesta pertenecientes al grupo principal. De este modo se minimizará el tiempo de inactividad de los grupos de respuesta.
    
    Este paso crea un nuevo archivo con la configuración exportada y después lo elimina del grupo B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Mueva al grupo C los intervalos de números no asignados que se movieron del grupo A al grupo B.
    
      - Vuelva a crear en el grupo C todos los anuncios que se crearon en el grupo B a partir del grupo A. Si se usó algún archivo de audio al implementar los anuncios que se van a mover, tendrá que usar esos archivos para volver a crear los anuncios en el grupo C. Para crear los anuncios en el grupo C, use los cmdlets **New-CsAnnouncement**, con el grupo C como servicio principal.
    
      - Redestine al grupo C todos los intervalos de números no asignados que se redestinaron desde el grupo A al grupo B. Ejecute el siguiente cmdlet para cada intervalo de números no asignados que haya que redestinar:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - (Opcional) Quite del grupo B los anuncios que se volvieron a crear en el grupo C y que ya no se usan en el grupo B. Para quitar los anuncios, use el cmdlet **Remove-CsAnnouncement**.
        

        > [!NOTE]
        > Este paso no es necesario con intervalos de números no asignados cuyo servicio de anuncio sea “Mensajería unificada de Exchange”.



21. Borre en el grupo B los datos de usuarios del grupo A con el siguiente cmdlet:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Haga lo siguiente en el Generador de topologías:
    
      - Desempareje el grupo A y el grupo B. Empareje el grupo B y el grupo C. Después, quite el grupo A de la topología y publíquelo. Para ello:
        
          - En el Generador de topologías, haga clic con el botón secundario en el grupo B y luego haga clic en **Editar propiedades**.
        
          - En el panel izquierdo, haga clic en **Resistencia**.
        
          - En el cuadro que está debajo de **Grupo de servidores de copia de seguridad asociado** , seleccione el grupo C. Observe que en este cuadro de selección aparecerá en un primer momento el grupo A, ya que el grupo B se asoció previamente a él.
        
          - Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y después haga clic en **Aceptar**.
            
            Cuando vea los detalles de este grupo, el grupo asociado aparecerá en el panel derecho debajo de **Resistencia**.
        
          - En el árbol de consola, haga clic con el botón secundario en el grupo A y luego haga clic en Eliminar.
        
          - Publique la topología.

23. Ejecute la aplicación de arranque en el grupo C para instalar la aplicación de servicio de copia de seguridad. Después inicie esta aplicación; para ello, ejecute lo siguiente desde la carpeta de implementación en una máquina local del grupo C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Reinicie la aplicación de servicio de copia de seguridad en el grupo B. Para ello, ejecute los siguientes cmdlets:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Si el grupo C es un grupo Standard Edition (SE) y el grupo B tiene CMS, instale manualmente la base de datos CMS en el grupo C con el siguiente cmdlet:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Invoque al servicio de copia de seguridad para que sincronice desde el grupo B al grupo C el contenido de conferencias antiguo que se generó antes de emparejar B y C, y para que sincronice desde el grupo C al grupo B el contenido de conferencias nuevo que se generó después de iniciar el grupo C y antes de que B y C se emparejaran. Para ello, ejecute los cmdlets siguientes:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Para cada aplicación de sucursal con funciones de supervivencia (SBA) X asociada al grupo A:
    
      - Cierre la SBA X con el siguiente cmdlet:
        
            Stop-CsWindowsService
    
      - Cree un archivo que contenga una lista de los usuarios alojados en la SBA X. Esta lista se necesitará en el paso 30 para devolver a los usuarios a la SBA X. Para ello, ejecute el siguiente cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Obligue a los usuarios alojados en la SBA X a desplazarse al grupo C con el cmdlet siguiente:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Ejecute primero los siguientes cmdlets para actualizar los datos de estos usuarios:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Después, ejecute este script:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        

        > [!NOTE]
        > Los usuarios que estén alojados en las SBA asociadas con el grupo A experimentarán una interrupción del servicio hasta que esos usuarios se muevan al grupo C.



28. En el Generador de topologías, haga lo siguiente para cada SBA X que estuviera asociada previamente al grupo A:
    
      - Cambie la asociación al grupo C. Para ello, haga clic en el sitio de la sucursal, expanda las aplicaciones de sucursal con funciones de supervivencia o el nodo Servidores, y haga clic en **Aplicación de sucursal con funciones de supervivencia** . Luego seleccione el **Grupo de servidores front-end, grupo Servicios del usuario** al que se conectará esta aplicación de sucursal con funciones de supervivencia como grupo C. Después, haga clic en **Siguiente** .
    
      - Publique la topología. Para ello, en el árbol de consola, haga clic con el botón secundario en la nueva **Aplicación de sucursal con funciones de supervivencia** , haga clic en **Topología** y después haga clic en **Publicar** .

29. Para cada SBA X que esté ahora asociada al grupo C:
    
      - Inicie la SBA X con el siguiente cmdlet en la aplicación de sucursal con funciones de supervivencia:
        
            Start-CsWindowsService
    
      - Mueva los usuarios que estaban alojados originalmente en la SBA X desde el grupo C a la SBA X con el siguiente cmdlet.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

