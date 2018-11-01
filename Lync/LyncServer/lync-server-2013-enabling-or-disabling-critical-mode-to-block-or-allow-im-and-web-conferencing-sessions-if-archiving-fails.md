---
title: "Hab./deshabilitar modo crítico para bloquear o permitir MI y conf. web si hay errores"
TOCTitle: "Act/dés mode crit. pr bloq./aut. sess. mess. inst. et conf. web si échec arch."
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48277236
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación o deshabilitación del modo crítico para bloquear o permitir mensajería instantánea y sesiones de conferencia web si hay errores de archivado

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, se utilizan las configuraciones de archivado para habilitar y deshabilitar el modo crítico, que incluye las siguientes configuraciones de archivo:

  - Una configuración global que se crea de manera predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de sitio y de grupo de servidores que se crean y usan para especificar cómo se realizarán las operaciones de archivado en sitios y grupos de servidores concretos.

Las configuraciones de archivado se definen inicialmente al implementar el archivado, pero posteriormente se pueden crear, agregar y eliminar. Si desea información adicional sobre las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planificación, la documentación de implementación o la documentación de operaciones.


> [!NOTE]
> Para utilizar el archivado, debe configurar las directivas de archivado con el fin de indicar si desea habilitar el archivado para las comunicaciones internas, las comunicaciones externas o ambas, para los usuarios hospedados en Lync Server 2013. De manera predeterminada, el archivado no está habilitado para las comunicaciones ni internas, ni externas. Antes de habilitar el archivado en ninguna directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, si lo desea, para sitios y grupos de servidores concretos, como se describe en este apartado. Encontrará información detalladas sobre la habilitación del archivado en <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A>, en la documentación de implementación.<BR>Si decide después de implementar el archivado que desea utilizar la integración del servidor Exchange para almacenar datos y archivos de archivo en los servidores Exchange 2013 y todos los usuarios se hospedan en sus servidores Exchange 2013, deberá eliminar de la topología la configuración de la base de datos SQL Server. Para ello, debe utilizar Generador de topologías. Encontrará más información en <A href="lync-server-2013-changing-archiving-database-options.md">Cambiar las opciones de base de datos de archivado en Lync Server 2013</A>, en la documentación de operaciones.



## Para habilitar o deshabilitar el bloqueo de las sesiones de conferencias web y MI cuando se produzca algún error en el archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo de servidores adecuada en la lista de configuraciones de archivado, haga clic en **Editar**, haga clic en **Mostrar detalles** y, a continuación, haga lo siguiente:

5.  Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.

6.  Haga clic en **Confirmar**.

## Habilitación y deshabilitación del modo crítico usando los cmdlets de Lync ServerWindows PowerShell

Puede habilitar o deshabilitar el modo crítico usando el cmdlet **Set-CsArchivingConfiguration**, que puede ejecutar desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Habilitación del modo crítico

  - Para habilitar el modo crítico, ajuste el valor de la propiedad BlockOnArchiveFailure en ($True). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

## Deshabilitación del modo crítico

  - Para deshabilitar el modo crítico, ajuste el valor de la propiedad BlockOnArchiveFailure en False ($False). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration).

## Vea también

#### Tareas

[Cambiar las opciones de base de datos de archivado en Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  

#### Conceptos

[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Otros recursos

[Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

