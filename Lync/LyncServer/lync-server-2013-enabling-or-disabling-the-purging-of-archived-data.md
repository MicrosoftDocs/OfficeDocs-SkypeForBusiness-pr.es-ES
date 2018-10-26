---
title: Habilitar o deshabilitar la depuración de datos archivados
TOCTitle: Habilitar o deshabilitar la depuración de datos archivados
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48274741
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar la depuración de datos archivados

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, usa las configuraciones de archivado para habilitar y deshabilitar la depuración y configurar la manera en que se implementa la depuración. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de manera predeterminada al implementar Lync Server 2013.

  - Las configuraciones de nivel de sitio opcional y nivel de grupo de servidores que puede crear y usar para especificar la manera en que se implementa el archivado para sitios o grupos de servidores específicos.

Configure inicialmente configuraciones de archivado al implementar el archivado, aunque podrá cambiar, agregar y eliminar las configuraciones después de la implementación. Para obtener información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planificación, sobre implementación o sobre operaciones.


> [!NOTE]
> Para utilizar el archivado para los usuarios hospedados en Lync Server 2013 debe configurar las directivas de Archivado para especificar si habilita el archivado para las comunicaciones internas, para las externas o para ambas. De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa. Antes de habilitar el archivado de ninguna directiva, debería especificar la configuración de archivado pertinente para su implementación y, de manera opcional, para sitios y grupos específicos, descritos en esta sección. Para obtener información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación sobre implementación.<BR>Si decide después de implementar Archivado que desea usar la integración de Microsoft Exchange para almacenar datos y archivos de archivado en servidores Exchange 2013 y todos sus usuarios están alojados en sus servidores Exchange 2013, debe quitar de su topología la configuración de la base de datos SQL Server. Deberá usar Generador de topologías para hacerlo. Para obtener más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">Cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación referente a las operaciones.



## Para habilitar o deshabilitar la depuración de archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar**, haga clic en **Mostrar detalles** y, a continuación, haga lo siguiente:
    
      - Para habilitar la depuración, active la casilla de verificación **Habilitar depuración de datos archivados** y siga uno de estos procedimientos:
        
          - Para depurar todos los registros, haga clic en **Depurar datos archivados exportados y datos archivados almacenados tras una duración máxima (días)** y luego especifique el número de días.
        
          - Para depurar solo los datos que se han exportado, haga clic en **Depurar solo datos archivados exportados**.
    
      - Para deshabilitar la depuración, desactive la casilla de verificación **Habilitar depuración de datos archivados**.

5.  Haga clic en **Confirmar**.

## Habilitar y deshabilitar la depuración de datos de archivado mediante los cmdlets de Shell de administración de Lync Server

La habilitación y la deshabilitación de la depuración automatizada de los datos de archivado también se pueden administrar mediante Windows PowerShell y el cmdlet **Set-CsArchivingConfiguration**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Habilitar la depuración de todos los datos de archivado

  - Para habilitar la depuración de todos los datos de archivado establezca la propiedad **EnablePurging** en verdadero ($True). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Una vez se ejecuta este comando, todos los días Lync Server depurará todos los registros de archivado con mayor antigüedad que el valor especificado para la propiedad **KeepArchivingDataForDays**.

## Habilitar la depuración solo de los datos de archivado exportados

  - Para limitar la depuración a los registros de archivado que se han exportado a un archivo de datos (mediante el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)) también debe establecer la propiedad PurgeExportedArchivesOnly en True ($True). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Una vez se ejecuta este comando, Lync Server solo depurará registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para la propiedad **KeepArchivingDataForDays**; y 2) se han exportado mediante el cmdlet **Export-CsArchivingData**.

## Deshabilitar la depuración de todos los datos de archivado

  - Para deshabilitar la depuración automatizada de los registros de archivados, establezca la propiedad **EnablePurging** en False ($False). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

Para obtener más información, incluyendo opciones adicionales para la depuración de datos de archivado, vea el tema de la Ayuda para el cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration).

## Vea también

#### Conceptos

[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Otros recursos

[Configurar y asignar directivas de archivado](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

