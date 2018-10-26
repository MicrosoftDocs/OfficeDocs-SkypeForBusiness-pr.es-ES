---
title: "Configuración de archivado de Lync Server 2013 para organización, sitios y servidores"
TOCTitle: "Gest. des opt. de conf. de l’arch. ds LS 2013 pr vos org., sites et pools"
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48274949
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores

 

_**Última modificación del tema:** 2012-11-01_

En Panel de control de Lync Server 2013, la configuración de archivado se usa para especificar cómo se implementa el archivado. Esto incluye las configuraciones de archivado siguientes:

  - Configuración global creada de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de nivel de sitio y de grupo que se crean y utilizan para especificar el modo en que se implementa el archivado en sitios o grupos específicos.

Inicialmente establece las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones tras la implementación. En Panel de control de Lync Server 2013, puede usar la página de **configuración de archivado** del grupo **de archivado y supervisión** para administrar las configuraciones en el nivel global, el nivel de sitio y el nivel de grupo. Para obtener más información acerca de cómo se implementan las configuraciones de archivado, incluyendo qué opciones puede especificar y la jerarquía de las configuraciones de archivado, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planificación, la documentación sobre implementación o documentación sobre operaciones.


> [!NOTE]
> Para utilizar el archivado debe configurar las directivas de archivado para especificar si habilita el archivado para las comunicaciones internas, para las externas o para ambas para todos los usuarios hospedados en Lync Server 2013. De forma predeterminada, el archivado no está habilitado ni para la comunicación interna ni para la externa. Si utiliza la integración con Microsoft Exchange, debe habilitar y configurar Exchange 2013 para que admita el archivado para todos los usuarios hospedados en Exchange 2013 cuyos buzones se hayan puesto en espera.<BR>Antes de habilitar el archivado, especifique la configuración de archivado adecuada para su implementación y, de forma opcional, para determinas grupos y sitios, tal como se describe en esta sección. Para obtener más detalles sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación sobre implementación.



**Para ver la información de configuración de archivado usando los cmdlets del Shell de administración de Lync Server**

  - También puede ver la información de configuración de archivado usando el Windows PowerShell de Lync Server y el cmdlet **Get-CsArchivingConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    En el Shell de administración de Lync Server, use el comando siguiente para ver la información de la configuración de archivado:
    
        Get-CsArchivingConfiguration

## En esta sección

  - [Crear una configuración de archivado para administrar el archivado para sitios o grupos de servidores específicos](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Habilitar y deshabilitar el archivado de sesiones de mensajería instantánea (MI) o de conferencia](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Habilitar o deshabilitar la depuración de datos archivados](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Habilitación o deshabilitación del modo crítico para bloquear o permitir mensajería instantánea y sesiones de conferencia web si hay errores de archivado](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Habilitar y deshabilitar la integración con Exchange Storage](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Eliminar una configuración de archivado](lync-server-2013-deleting-an-archiving-configuration.md)

## Vea también

#### Otros recursos

[Administración de archivado en Lync Server 2013](lync-server-2013-managing-archiving.md)

