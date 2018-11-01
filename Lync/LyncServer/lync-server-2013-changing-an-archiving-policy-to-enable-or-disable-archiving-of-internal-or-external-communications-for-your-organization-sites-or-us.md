---
title: "Cambiar directiva archivado para hab/deshab. archivado comunics. internas/externas"
TOCTitle: "Mod. strat. arch. pr ac./dés. arch. des com. int./ext. pr vos org., sites, ut."
ms:assetid: b85dc3fb-8ebd-4e3c-ac90-fc79270ac867
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182576(v=OCS.15)
ms:contentKeyID: 48276447
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambiar una directiva de archivado para habilitar o deshabilitar el archivado de comunicaciones internas o externas para sus organizaciones, sitios usuarios

 

_**Última modificación del tema:** 2013-02-23_

En Lync Server 2013, se usan directivas para habilitar y deshabilitar el archivado para las comunicaciones internas y externas de los usuarios hospedados en Lync Server 2013. Esto incluye las siguientes directivas de archivado:

  - Una directiva global creada de manera predeterminada al implementar Lync Server 2013.

  - Directivas opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para sitios o usuarios específicos.

Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación. En Panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **Archivado y supervisión** para administrar directivas en el nivel global, de sitio y de usuario. Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tendrán prioridad sobre las directivas de archivado de Lync Server 2013.

Para más información sobre cómo se implementan las directivas, incluida la jerarquía de las directivas, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, implementación u operaciones.


> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para la implementación, las directivas de Exchange controlan si el archivado se habilita para los usuarios que están hospedados en Exchange 2013 y que tienen sus buzones definidos en Conservación local. Para más información, vea <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Debe especificar todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado. Para más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores</A> en la documentación sobre operaciones.



## Para cambiar una directiva de archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  En la lista de directivas, siga uno de estos pasos:
    
      - Para cambiar la directiva de toda la implementación, haga clic en **Global** en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
      - Para cambiar la directiva de un solo sitio, haga clic en el nombre del sitio en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.
    
      - Para cambiar la directiva de solo usuario o grupo de usuarios, haga clic en el nombre del usuario o del grupo de usuarios en la lista de directivas, y luego haga clic en **Editar** y en **Mostrar detalles**.

5.  En la página **Editar directiva de archivado**, haga lo siguiente:
    
      - Para habilitar o deshabilitar el archivado interno para la directiva, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para habilitar o deshabilitar el archivado externo para la directiva, active o desactiva la casilla **Archivar comunicaciones externas**.

6.  Haga clic en **Confirmar**.
    
    > [!IMPORTANT]  
    > La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva. Para más información, vea <a href="lync-server-2013-applying-an-archiving-policy-to-users.md">Aplicación de una directiva de archivado a los usuarios</a>.
    


## Habilitar y deshabilitar el archivado con los cmdlets de Lync Server PowerShell

El archivado también se puede habilitar y deshabilitar (para las sesiones de comunicación internas y externas) con el cmdlet **Set-CsArchivingPolicy**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Habilitar el archivado de sesiones de comunicación internas

  - Para habilitar el archivado de sesiones de comunicación internas, establezca el valor de la propiedad **ArchiveInternal** en True ($True). Por ejemplo:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

## Habilitar el archivado de sesiones de comunicación externas

  - Para habilitar el archivado de sesiones de comunicación externas, establezca el valor de la propiedad **ArchiveExternal** en True ($True). Por ejemplo:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

## Habilitar el archivado de sesiones de comunicación internas y externas

  - Para habilitar el archivado de sesiones de comunicación internas y externas, establezca el valor de las propiedades **ArchiveInternal** y **ArchiveExternal** en True:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

## Deshabilitar el archivado

  - Para deshabilitar el archivado por completo, establezca el valor de las propiedades **ArchiveInternal** y **ArchiveExternal** en False ($False). Por ejemplo:
    
        Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

Para más información, vea el tema de ayuda del cmdlet [Set-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingPolicy).

## Vea también

#### Otros recursos

[Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

