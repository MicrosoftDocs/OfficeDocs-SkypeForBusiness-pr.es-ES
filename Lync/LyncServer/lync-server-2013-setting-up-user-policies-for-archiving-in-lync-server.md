---
title: Configurar directivas de usuario para archivado en Lync Server
TOCTitle: Configurar directivas de usuario para archivado en Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48274676
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar directivas de usuario para archivado en Lync Server

 

_**Última modificación del tema:** 2012-10-10_

Para la habilitación o inhabilitación del archivado para usuarios concretos ubicados enLync Server 2013 es necesaria la creación y configuración de una o más directivas de usuarios y, a continuación, la aplicación de la directiva pertinente a los usuarios o grupos de usuarios concretos. Las directivas de usuario invalidan las directivas globales y de sitio, pero solo para usuarios hospedados en Lync Server 2013.

Los usuarios siempre se hospedan en Lync Server. Si la integración de Microsoft Exchange está habilitada, no es necesario que los usuarios cuyos buzones se encuentran en Microsoft Exchange Server 2013 tengan sus directivas de archivado en Lync Server administradas. Estos usuarios con archivado se administrarán por la conservación local de Exchange.

Para obtener más información acerca de cómo funcionan las directivas de archivado, incluyendo la jerarquía de las directivas globales, de sitio y de usuario, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación relativa a la planeación, en la documentación relativa a la implementación o la referente a las operaciones.


> [!NOTE]
> Si ha habilitado la integración con Microsoft Exchange para su implementación, las directivas de conservación local de Exchange controlan si se habilita el archivado para los usuarios que están hospedados en Exchange 2013. El archivado para estos usuarios requiere que tengan sus buzones colocados en conservación local. Para más información, vea <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuración de directivas para el archivado al usar la integración de Exchange Server</A> en la documentación relativa a la implementación.<BR>Debe especificar todas las opciones pertinentes para la configuración de archivado antes de habilitar el archivado. Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">Configurar opciones de archivado</A> en la documentación referente a la implementación.



## En esta sección

  - [Crear y configurar las directivas de usuarios para el archivado en Lync Server](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Aplicación de una directiva de archivado de Lync Server a un usuario](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

