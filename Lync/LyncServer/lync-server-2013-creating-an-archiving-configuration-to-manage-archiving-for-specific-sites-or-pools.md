---
title: "Crear configuración para el archivado de sitios o grupos de servidores específicos"
TOCTitle: "Créa. d’une conf. d’arch. pour gérer l’arch. pour des sites ou pools part."
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48276613
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una configuración de archivado para administrar el archivado para sitios o grupos de servidores específicos

 

_**Última modificación del tema:** 2013-02-23_

En Panel de control de Lync Server 2013, se usan las configuraciones de archivado para controlar cómo se aplica el archivado en la implementación. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada cuando se implementa Lync Server 2013.

  - Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.

Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación. Para más información sobre cómo implementar las configuraciones de archivado, incluidas las opciones que se pueden especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación u operaciones.


> [!NOTE]
> Para usar el archivado, debe configurar las directivas de archivado a fin de especificar si habilita el archivado para las comunicaciones internas, las externas o para ambas, para los usuarios hospedados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa. Antes de habilitar el archivado en las directivas, debe especificar la configuración de archivado pertinente para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección. Para información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación de implementación.<BR>Si decide, después de implementar el archivado, que desea usar la integración de Microsoft Exchange para almacenar datos y archivos de archivado en servidores Exchange 2013, y todos sus usuarios están hospedados en los servidores Exchange 2013, debe quitar de su topología la configuración de la base de datos de SQL Server. Deberá usar la Generador de topologías para hacerlo. Para más información, consulte <A href="lync-server-2013-changing-archiving-database-options.md">Cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.



## Para crear una configuración de archivado para un sitio o un grupo:

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y elija una de las siguientes acciones:
    
      - Para crear una configuración de archivado de sitio, haga clic en **Configuración de sitio** y, en **Seleccionar un sitio**, seleccione el sitio que se va a configurar para el archivado.
    
      - Para crear una configuración de archivado de grupo, haga clic en **Configuración del grupo de servidores** y, en **Seleccionar un grupo de servidores**, seleccione el grupo que se va a configurar para el archivado.

5.  En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
      - Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.
    
      - Para habilitar el archivado tanto para las sesiones de mensajería instantánea como para las conferencias web, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
      - Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.

6.  Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
      - Para usar Microsoft Exchange Server para almacenar los datos de archivado, haga clic en la casilla **Integración de Microsoft Exchange**.
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
        
          - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.

7.  Haga clic en **Confirmar**.

## Crear los parámetros de configuración de archivado con los cmdlets de Lync Server

Los valores de configuración de archivado se pueden crear también con Windows PowerShell de Windows PowerShell y el cmdlet New-CsArchivingConfiguration. Este cmdlet se puede ejecutar desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)..

## Crear una colección de valores de configuración de archivado para un sitio

  - El comando siguiente crea una colección de valores de configuración de archivado para el sitio de Redmond:
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

## Crear una colección de valores de configuración de archivado que solo permita el archivado de MI

  - Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de valores de configuración de archivado que, de forma predeterminada, permita el archivado de las sesiones de mensajería instantánea, use solo un comando como este:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

## Especificar varios valores de propiedad al crear los valores de configuración de archivado

  - Si lo desea, puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando define la nueva configuración para archivar las sesiones de mensajería instantánea y bloquear la mensajería instantánea del servicio de archivado no está disponible:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

Para más información, vea el tema de Ayuda del cdmlet [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration).

## Vea también

#### Conceptos

[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Otros recursos

[Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

