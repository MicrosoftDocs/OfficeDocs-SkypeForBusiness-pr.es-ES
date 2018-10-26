---
title: "Administrar el archivado de comunicaciones internas y externas en Lync Server 2013"
TOCTitle: "Gest. de l'arch. des comm. int. et ext. dans Lync Server 2013"
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48275571
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar el archivado de las comunicaciones internas y externas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-09_

En Lync Server 2013, las directivas de archivado se usan para habilitar y deshabilitar el archivado en las comunicaciones internas y externas en caso de que no se use la integración en Microsoft Exchange, o cuando haya usuarios que no se hospeden en Exchange 2013 con sus buzones en conservación local. Esto engloba las siguientes directivas de archivado:

  - Una directiva global que se crea de manera predeterminada cuando Lync Server 2013 se implementa.

  - Directivas opcionales de nivel de sitio y usuario que se pueden crear para especificar el modo en que el archivado se implementa en relación con determinados sitios y usuarios:

En principio, las directivas de archivado se configuran cuando se implementa el archivado, pero se pueden cambiar, agregar y eliminar directivas después de la implementación. En el Panel de control de Lync Server 2013, puede usar la página **Directiva de archivado** del grupo **Archivado y supervisión** para administrar las directivas a nivel global, de sitio y de usuario. Si integra su almacenamiento de Lync Server con el almacenamiento de Exchange 2013, las directivas de usuario de Exchange tendrán prioridad frente las directivas de archivado del Lync Server 2013.

Para obtener más información acerca de cómo se implementan las directivas, incluyendo la jerarquía de directivas, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeamiento, relativa a la implementación o sobre operaciones.


> [!NOTE]
> Para controlar la implementación del archivado, debe especificar una serie de opciones en las configuraciones de archivado, como, por ejemplo, si se van a archivar los mensajes instantáneos o las conferencias, el uso del modo crítico y las opciones de purgado. De forma predeterminada, no hay ninguna opción habilitada en la configuración de archivado global ni en ninguna configuración de archivado de sitio o de grupo. Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado relativas a las comunicaciones internas y externas. Para obtener información, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Administrar las opciones de configuración de archivado de Lync Server 2013 para su organización, sitios y grupos de servidores</A> en la documentación de operaciones.<BR>Si ha habilitado la integración con Microsoft Exchange en su implementación, las directivas de Exchange controlarán si se habilita el archivado para los usuarios hospedados en Exchange 2013 cuyos buzones están en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación de implementación.



## En esta sección

  - [Crear una directiva de archivado para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para sitios o usuarios específicos](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [Cambiar una directiva de archivado para habilitar o deshabilitar el archivado de comunicaciones internas o externas para sus organizaciones, sitios usuarios](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [Aplicación de una directiva de archivado a los usuarios](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configuración de directivas para el archivado al usar la integración de Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Eliminar una directiva de archivado](lync-server-2013-deleting-an-archiving-policy.md)

