---
title: "Proteger datos en tránsito: DB de archivado, supervisión y cumplim. de chat en grupo"
TOCTitle: 'Proteger los datos en tránsito: bases de datos de servidor de archivado, supervisión y cumplimiento de chat en grupo en Lync Server 2013'
ms:assetid: ea219705-1015-43a7-890b-e7e67b451e7c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518336(v=OCS.15)
ms:contentKeyID: 60505980
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proteger los datos en tránsito: bases de datos de servidor de archivado, supervisión y cumplimiento de chat en grupo en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El servidor de archivado y el servidor de supervisión de Microsoft Lync Server 2013 utilizan Message Queue Server (también conocido como MSMQ) para recopilar y mover de manera confiable los mensajes de datos desde el punto de recopilación hasta los servidores de repositorio. El servicio de cumplimiento recopila datos junto con el servidor de chat en grupo, que también utiliza Message Queue Server.

En Lync Server 2013, no hay protección interna para los datos de una red por cable. Sin embargo, si es preciso proteger este tráfico, el servicio de Message Queue Server puede proporcionar cifrado para los mensajes en la cola de mensajes que realiza el envío. Para ello, se usan certificados administrados por los Servicios de dominio de Active Directory. Si quiere más información, consulte el Apéndice D: Message Queue Server y la comunicación derivada a través de Internet en Windows Server 2008, en [http://go.microsoft.com/fwlink/p/?LinkId=145238](http://go.microsoft.com/fwlink/p/?linkid=145238), o el Apéndice I: Message Queue Server y la comunicación derivada a través de Internet en Windows Server 2008 R2, en [http://go.microsoft.com/fwlink/p/?LinkId=211883](http://go.microsoft.com/fwlink/p/?linkid=211883), para Windows Server 2008 R2.

