---
title: Configurar opciones de archivado
TOCTitle: Configurar opciones de archivado
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48276399
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar opciones de archivado

 

_**Última modificación del tema:** 2012-10-10_

En el Panel de control de Lync Server 2013, use las configuraciones de archivado para especificar cómo se implementa el archivado. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global creada de manera predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de nivel de sitio y de grupo que puede crear y usar para especificar cómo se implementa el archivado para sitios o grupos específicos.

Las configuraciones de archivado se definen inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar configuraciones después de la implementación. En el Panel de control de Lync Server 2013, puede usar la página **Configuración de archivado** del grupo **Archivado y supervisión** para administrar configuraciones en el nivel global, de sitio y de grupo. Para más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de configuraciones de archivado, vea [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre planeación, implementación u operaciones. Para más información sobre cómo administrar configuraciones después de la implementación, vea [Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) en la documentación sobre operaciones.


> [!NOTE]
> Para usar el archivado, debe configurar directivas de archivado para especificar si desea habilitar el archivado para comunicaciones internas, para comunicaciones externas o para ambas, para usuarios hospedados en Lync Server 2013. De manera predeterminada, el archivado no está habilitado ni para las comunicaciones internas ni para las externas. Antes de habilitar el archivado en una directiva, debe especificar las configuraciones de archivado adecuadas para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección. Para más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación sobre implementación.<BR>Si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación, debe configurar directivas de archivado para especificar si desea habilitar el archivado para comunicaciones internas, para comunicaciones externas o para ambas. De manera predeterminada, el archivado no está habilitado ni para las comunicaciones internas ni para las externas para el archivado de datos cuando se usan las bases de datos de archivado de Lync Server 2013. Antes de habilitar el archivado en una directiva, debe especificar las configuraciones de archivado adecuadas para su implementación y, de manera opcional, para sitios y grupos específicos, como se describe en esta sección. Para más información sobre cómo habilitar el archivado para usarlo con las bases de datos de archivado de Lync Server 2013, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurar y asignar directivas de archivado</A> en la documentación sobre implementación.



## En esta sección

  - [Configurar opciones de archivado a nivel global](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [Configurar opciones de archivado para un sitio](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [Configurar opciones de archivado para un grupo de servidores](lync-server-2013-configuring-archiving-options-for-a-pool.md)

