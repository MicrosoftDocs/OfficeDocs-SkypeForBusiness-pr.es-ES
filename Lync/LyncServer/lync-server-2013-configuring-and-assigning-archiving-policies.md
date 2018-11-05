---
title: Configurar y asignar directivas de archivado
TOCTitle: Configurar y asignar directivas de archivado
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48276329
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar y asignar directivas de archivado

 

_**Última modificación del tema:** 2012-10-01_

En Lync Server 2013, se usan directivas para habilitar y deshabilitar el archivado para las comunicaciones internas y externas de los usuarios hospedados en Lync Server 2013. Esto incluye las siguientes directivas de archivado:

  - Una directiva global creada de manera predeterminada al implementar Lync Server 2013.

  - Directivas opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementa el archivado para sitios o usuarios específicos.

Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación. En Panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **Archivado y supervisión** para administrar directivas en el nivel global, de sitio y de usuario.


> [!NOTE]
> Para controlar la implementación del archivado, debe especificar opciones en las configuraciones de archivado, por ejemplo, si se deben archivar las sesiones de MI o de conferencia, el uso del modo crítico y las opciones de depuración. De manera predeterminada, no hay opciones habilitadas en la configuración de archivado global ni ninguna otra configuración de archivado de nivel de grupo. Debe especificar todas las opciones correspondientes en las configuraciones de archivado antes de habilitar el archivado para las comunicaciones internas o externas en las directivas de archivado. Para más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores</A> en la documentación sobre operaciones.<BR>Si integra el almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tendrán prioridad sobre las directivas de archivado de Lync Server 2013, pero solo para los usuarios hospedados en Exchange 2013 cuyos buzones se definieron en Conservación local.



Para más información sobre cómo se implementan las directivas, incluida la jerarquía de las directivas, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, implementación u operaciones. Para más información sobre cómo administrar las directivas después de la implementación, vea [Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) en la documentación sobre operaciones.

## En esta sección

  - [Configurar las directivas globales para el archivado](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Configurar directivas de sitio para el archivado](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Configurar directivas de archivado para usuarios](lync-server-2013-setting-up-archiving-policies-for-users.md)

