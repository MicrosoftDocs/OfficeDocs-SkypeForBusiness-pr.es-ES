---
title: Quitar un servidor front-end de un grupo de servidores
TOCTitle: Quitar un servidor front-end de un grupo de servidores
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49889232
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar un servidor front-end de un grupo de servidores

 

_**Última modificación del tema:** 2012-10-04_

El Servidor front-end de Microsoft Lync Server 2010 Enterprise Edition no puede existir como equipo independiente. Es necesario que se defina como un Grupo de servidores front-end, incluso si en el grupo de servidores solo hay un equipo.

Este tema sirve de orientación por el proceso de eliminación de un Servidor front-end individual de un Grupo de servidores front-end existente. Si el Servidor front-end es el último servidor del grupo o si está eliminando el grupo por completo, consulte [Quitar un grupo de servidores front-end o un servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). No es necesario quitar los Servidores front-end uno a uno para quitar el Grupo de servidores front-end: al quitar el grupo, cada Servidor front-end se eliminará con él.

## Para quitar un servidor front-end de un grupo

1.  Abra el servidor front-end de Lync Server 2013, abra el Generador de topologías.

2.  Desplácese hasta el nodo de Lync Server 2010.

3.  Expanda **Grupos de servidores front-end Enterprise Edition** , expanda el Grupo de servidores front-end con el Servidor front-end que quiera quitar, haga clic con el botón secundario en dicho Servidor front-end y, por último, haga clic en **Eliminar** .

