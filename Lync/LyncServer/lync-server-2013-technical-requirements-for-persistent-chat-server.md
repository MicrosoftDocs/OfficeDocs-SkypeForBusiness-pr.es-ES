---
title: "Lync Server 2013 : Conf. tech. pour le serveur de conversation permanente"
TOCTitle: Requisitos técnicos para el servidor de chat persistente
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48275534
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Todos los equipos que hospedan un Servidor de chat persistente deben tener acceso a una topología de Lync Server 2013 existente con los siguientes componentes:

  - **Servidor front-end de Lync Server 2013.**. El Servidor front-end es la base del enrutamiento SIP (Protocolo de inicio de sesión), que hace posible las comunicaciones entre equipos que ejecutan el Servidor de chat persistente y la funcionalidad de Chat persistente. Antes de empezar a implementar el Servidor de chat persistente, compruebe que se ha implementado Lync Server 2013, Standard Edition o un Grupo de servidores front-end de Lync Server y cualquier otro equipo interno que ejecute Lync Server, según corresponda a su organización.

En las secciones siguientes se describen los requisitos específicos para el Servidor de chat persistente y la base de datos que almacena los datos de Chat persistente.

## Servidor de chat persistentefea-dialinconf-page

Para obtener más información acerca del hardware recomendado para implementar Lync Server y la versión más reciente de Servidor de chat persistente, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación referente a la compatibilidad.

Para obtener más información acerca de la compatibilidad del sistema operativo del servidor y las herramientas con Lync Server y Servidor de chat persistente, consulte [Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) en la documentación referente a la compatibilidad.

Para obtener más información acerca del software adicional requerido para implementar Servidor de chat persistente, consulte la siguiente tabla.

### Requisitos previos de software del Servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Message Queue Server</p></td>
<td><p>Para uso por parte del Servidor de chat persistente y del servicio de cumplimiento de Chat persistente (si está implementado).</p></td>
</tr>
</tbody>
</table>


## Requisitos de base de datos del Servidor de chat persistente

El Servidor de chat persistente usa la base de datos de Chat persistente para almacenar el historial de conversaciones, la configuración y los datos de aprovisionamiento de usuarios. También puede usar (opcionalmente) una base de datos de cumplimiento de Chat persistente para almacenar los datos de cumplimiento.

> [!IMPORTANT]  
> La base de datos del Chat persistente (mgc) y la base de datos de cumplimiento (mgccomp) pueden estar ubicadas en la misma instancia de SQL Server o en Servidores SQL Server diferentes.



Para preparar una plataforma de servidor de bases de datos, asegúrese de que cada equipo reúne todos los requisitos de hardware y, a continuación, instale el software necesario como requisito previo.

La plataforma de servidor para los servidores de bases de datos del Chat persistente requiere el mismo hardware que el servidor de bases de datos back-end de Lync Server. Para obtener más información, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de compatibilidad.

Confirme que una de las siguientes aplicaciones de software está instalada en el servidor de bases de datos:

  - Microsoft SQL Server 2012. Para obtener información sobre cómo instalar Microsoft SQL Server 2012, vea "Instalar SQL Server 2012" en [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Para obtener información detallada sobre cómo instalar Microsoft SQL Server 2008 R2, vea "Instalación de SQL Server (SQL Server 2008 R2)" en <http://go.microsoft.com/fwlink/?linkid=275702>.

## Requisitos de certificado del Servidor de chat persistente

Para más información sobre la adquisición de certificados, la creación de bases de datos de SQL Server y la creación de almacenes de archivos, vea [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md)en la documentación de implementación.

