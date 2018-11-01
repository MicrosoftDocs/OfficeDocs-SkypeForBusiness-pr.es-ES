---
title: "Habilitar/deshabilitar archivado de sesiones de mensajería instantánea o conferencia"
TOCTitle: "Act. ou dés. de l’archivage de sessions de mes. instantanée ou de conférence"
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48276307
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar y deshabilitar el archivado de sesiones de mensajería instantánea (MI) o de conferencia

 

_**Última modificación del tema:** 2012-10-10_

En el Panel de control de Lync Server 2013, use las configuraciones de archivado para habilitar y deshabilitar el archivado de sesiones de MI, de conferencia o ambas. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global creada de manera predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de nivel de sitio y de grupo que puede crear y usar para especificar cómo se implementa el archivado para sitios o grupos específicos.

Las configuraciones de archivado se definen inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar configuraciones después de la implementación. Para más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de configuraciones de archivado, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, implementación u operaciones.


> [!NOTE]
> Para usar el archivado, debe configurar directivas de archivado para especificar si desea habilitar el archivado para comunicaciones internas, para comunicaciones externas o para ambas, para usuarios hospedados en Lync Server 2013. De manera predeterminada, el archivado no está habilitado ni para las comunicaciones internas ni para las externas. Antes de habilitar el archivado en una directiva, debe especificar las configuraciones de archivado adecuadas para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección. Para más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación sobre implementación.<BR>Si decide después de implementar el archivado que desea usar la integración de Microsoft Exchange para almacenar archivos y datos de archivado en servidores Exchange 2013, y todos sus usuarios están hospedados en los servidores Exchange 2013, debe quitar de su topología la configuración de la base de datos de SQL Server. Debe usar el Generador de topologías para hacerlo. Para más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">Cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación sobre operaciones.



## Procedimiento para habilitar o deshabilitar el archivado de sesiones de MI o de conferencia

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  Seleccione la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado, haga clic en **Editar** y en **Mostrar detalles**, y luego siga estos pasos:
    
      - Para habilitar el archivado solamente para las sesiones de MI, haga clic en **Archivar sesiones de mensajería instantánea**.
    
      - Para habilitar el archivado para las sesiones de MI y de conferencia, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
      - Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.

5.  Haga clic en **Confirmar**.

## Vea también

#### Otros recursos

[Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[Configurar y asignar directivas de archivado](lync-server-2013-configuring-and-assigning-archiving-policies.md)

