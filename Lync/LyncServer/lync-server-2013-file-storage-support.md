---
title: 'Lync Server 2013: Compatibilidad con el almacenamiento de archivos'
TOCTitle: Compatibilidad con el almacenamiento de archivos
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48277082
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con el almacenamiento de archivos en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 usa el mismo almacén de archivos para todo el almacenamiento de archivos. La compatibilidad del almacenamiento de archivos incluye lo siguiente:

  - Un recurso compartido de archivos, ya sea en almacenamiento conectado directamente (DAS) o en una red de área de almacenamiento (SAN), incluido el Sistema de archivos distribuido (DFS), y en una matriz redundante de discos independientes (RAID) de almacenes de archivos. Para más información sobre los requisitos de almacenamiento, consulte [Requisitos técnicos para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) y [Requisitos de hardware y software para el director en Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) en la documentación sobre planificación. Para más información sobre los sistemas de archivos distribuidos en Sistema operativo Windows Server 2008, consulte la Guía paso a paso de los sistemas de archivos distribuidos en Windows Server 2008, en [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).

  - Un clúster compartido para un recurso compartido de archivos. Si usa un clúster compartido, debe usar servidores de clústeres que ejecuten Windows Server 2008 o Windows Server 2008 R2. Es posible que al usar servidores de clústeres que ejecutan una versión anterior de Windows se produzcan errores con los permisos que deshabiliten algunas funciones. Use el Administrador de clústeres para crear los recursos compartidos de archivos. Para más información sobre cómo utilizar el Administrador de clústeres, vea el artículo 284838 de Microsoft Knowledge Base sobre la creación de un recurso compartido de archivos de clúster de servidores con Cluster.exe en [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).

