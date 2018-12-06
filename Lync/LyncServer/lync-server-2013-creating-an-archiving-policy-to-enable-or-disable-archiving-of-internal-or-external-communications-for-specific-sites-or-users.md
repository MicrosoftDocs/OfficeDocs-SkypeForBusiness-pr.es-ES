---
title: "Directiva para habilitar/deshabilitar archivado de comunicaciones internas/externas"
TOCTitle: "Créa. strat. arch. pr act/dés. arch. des comm. int/ext pr sites ou ut. part."
ms:assetid: 5864793a-ba72-470c-bb5b-9fb41e968896
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398385(v=OCS.15)
ms:contentKeyID: 48275321
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear una directiva de archivado para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para sitios o usuarios específicos

 

_**Última modificación del tema:** 2013-02-23_

En Lync Server 2013, usa directivas para habilitar y deshabilitar el archivado de comunicaciones internas y externas para los usuarios alojados en Lync Server 2013. Esto incluye las siguientes directivas de archivado:

  - De forma predeterminada, se crea una directiva global que al implementar Lync Server 2013.

  - Puede crear y usar directivas opcionales a nivel de sitio y a nivel de usuario para especificar cómo se implementará el archivado de usuarios o sitios específicos.

Inicialmente se configuran las directivas de archivado al implementar el archivado. No obstante, es posible cambiar, agregar y eliminar directivas después de la implementación. En Panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo de servidores de **archivado y supervisión** para administrar directivas a nivel global, de sitio y de usuario. Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tiene prioridad sobre las directivas de archivado de Lync Server 2013.

Para obtener información detallada acerca de las directivas implementadas incluida la jerarquía de directivas, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación referente a la planificación, la implementación o las operaciones.


> [!NOTE]
> Para controlar la implementación del archivado, debe especificar opciones en las configuraciones del archivado, como si se archivarán mensajes instantáneos o conferencias, el uso del modo crítico y las opciones de depuración. De forma predeterminada, en la configuración de archivado global o en la configuración de archivado del grupo no se habilitan opciones. Se deben especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado para comunicaciones internas o externas en las directivas de archivado. Para más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores</A> en la documentación de operaciones.<BR>Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están alojados en Exchange 2013 y que tienen sus buzones de correo colocados en Conservación local. Para información, vea <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación referente a la implementación.



## Para crear una directiva de archivado para un sitio o usuarios

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  Haga clic en **Nuevo**, y, a continuación, siga uno de estos procedimientos:
    
      - Para crear una directiva de archivado de nivel de sitio, haga clic en **Directiva de sitio**, en **Seleccionar un sitio** y, a continuación, haga clic en el sitio al que se va a aplicar la directiva.
    
      - Para crear una directiva de archivado de nivel de usuario, haga clic en **Directiva de usuario**.

5.  En **Directiva de archivado nueva**, haga lo siguiente:
    
      - En **Nombre**, especifique un nombre para la nueva directiva (por ejemplo, externalContoso).
    
      - En **Descripción**, proporcione información detallada sobre la función de la directiva (por ejemplo, directiva de archivado de usuarios externos para Contoso).
    
      - Para controlar el archivado de comunicaciones con usuarios internos, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de comunicaciones externas, active o desactive la casilla **Archivar comunicaciones externas**.

6.  Haga clic en **Confirmar**.
    
    > [!IMPORTANT]  
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para obtener información detallada, consulte <a href="lync-server-2013-applying-an-archiving-policy-to-users.md">Aplicación de una directiva de archivado a los usuarios</a>
    


## Creación de una directiva de archivado con los cmdlets de Shell de administración de Lync Server

Las directivas de archivado también pueden eliminarse con Windows PowerShell y el cmdlet **Remove-CsArchivingPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Creación de una nueva directiva de archivado en el ámbito del sitio

  - Este comando crea una nueva directiva de archivado para el sitio Redmond:
    
        New-CsArchivingPolicy -Identity "site:Redmond"

## Creación de una nueva directiva de archivado en el ámbito por usuario

  - Para crear una nueva directiva de archivado en el ámbito por usuario, simplemente especifique una identidad única al crear la directiva:
    
        New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"

## Creación de una nueva directiva de archivado que permita el archivado de sesiones de comunicaciones internas

  - Ya que no se especifican parámetros (excepto el parámetro obligatorio de identidad) en los comandos anteriores, las nuevas directivas usarán los valores predeterminados para todas sus propiedades. Para crear directivas que usen otros valores de propiedades, basta con incluir el parámetro y el valor de parámetro. Por ejemplo, para crear un archivo que permita archivar sesiones de mensajes instantáneos internos use un comando como este:
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True

## Creación de una nueva directiva de archivado que permita el archivado de sesiones de comunicaciones externas e internas

  - Mediante la inclusión de varios parámetros se pueden cambiar varios valores de propiedad. Por ejemplo, este comando configura la nueva directiva de archivado de sesiones de mensajes instantáneos internos y externos:
    
        New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True

Para más información, vea el tema de ayuda del cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingPolicy).

## Vea también

#### Otros recursos

[Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

