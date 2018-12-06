---
title: 'Lync Server 2013: Nuevas características de archivado'
TOCTitle: Nuevas características de archivado
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48276541
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nuevas características de archivado en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El archivado de Lync Server 2013 puede archivar los tipos de contenido siguientes:

  - Mensajes instantáneos de punto a punto

  - Conferencias (reuniones) que incluyen mensajes instantáneos de varios participantes.

  - Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y cambios en la visibilidad)

Asimismo, el archivado de Lync Server 2013 proporciona nuevas características que mejoran la eficacia de la implementación y las operaciones. Estas nuevas características son:

  - **Colocación de archivado en servidores front-end.**    Lync Server 2013 no tiene un rol independiente de servidor de archivado. El archivado es una característica opcional disponible en todos los servidores front-end de una implementación Enterprise Edition y en servidores Standard Edition, que pueden implementarse configurados para un grupo o un sitio.

  - **Integración de Microsoft Exchange**.   Al implementar el archivado, puede integrar el almacenamiento de datos para archivado con su almacenamiento de Exchange 2013 actual para todos los usuarios que se encuentran hospedados en Exchange 2013 y tienen sus buzones definidos como Conservación local, de modo que no tiene que implementar bases de datos de SQL Server independientes para archivar datos de Lync. Si no tiene una implementación de Exchange 2013 o prefiere no realizar la integración, o si tiene usuarios de Lync 2013 que no estén hospedados en Exchange 2013, con sus buzones definidos como Conservación local, puede implementar bases de datos de archivado independientes con SQL Server para almacenar datos archivados de comunicaciones de Lync. Puede usar tanto la integración de Microsoft Exchange como las bases de datos de archivado de Lync Server 2013 si desea usar la integración de Microsoft Exchange solo para algunos usuarios de la implementación. Para obtener información detallada sobre la Conservación local, vea "Retención en contexto" en [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Creación de reflejo del almacén SQL.**   En el momento en que implemente el archivado, podrá habilitar la creación de reflejo de base de datos de SQL Server para la base de datos de archivado.

  - **Archivado de pizarras y sondeos.**   El contenido de conferencias archivado ahora incluye las pizarras y los sondeos que se comparten durante la reunión.

No se almacenan los tipos de contenido siguientes:

  - Transferencias de archivos de punto a punto

  - Audio y vídeo para conferencias y mensajes instantáneos de punto a punto

  - Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto

## Vea también

#### Otros recursos

[Planificar el archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md)

