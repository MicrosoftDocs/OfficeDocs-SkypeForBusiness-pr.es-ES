---
title: "Configurar Lync Server para el administrador de System Center Operations Manager"
TOCTitle: "Conf. de Lync Server pour le fonct. avec System Center Operations Manager"
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48276426
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Lync Server para funcionar con el administrador de System Center Operations Manager

 

_**Última modificación del tema:** 2012-10-22_

Si desea configurar la infraestructura de Microsoft Lync Server 2013 para que funcione con System Center Operations Manager, debe seguir estos tres pasos:

  - Identificar y configurar el servidor de administración principal de System Center Operations Manager. La configuración del servidor de administración implica instalar System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, además de configurar una base de datos back-end con SQL Server. La versión real de SQL Server que debe usar depende de qué versión de System Center Operations Manager usa. Para más información, vea [Configuración del servicio de administración principal](lync-server-2013-configuring-the-primary-management-server.md).

  - Identificar y configurar los equipos con Lync Server que desea supervisar. Para supervisar un equipo con Lync Server por medio de System Center Operations Manager, debe instalar los archivos de agente de System Center Operations Manager y configurar cada servidor para que actúe como proxy.

  - Identificar y configurar los equipos que desea que actúen como *nodos de monitor* de Lync Server. Los nodos de monitor son equipos que periódicamente ejecutan transacciones sintéticas de Lync Server, que son cmdlets de Windows PowerShell que comprueban que los componentes clave de Lync Server, como la capacidad de iniciar sesión en el sistema o de intercambiar mensajes instantáneos, funcionen del modo esperado.

Los temas de esta sección contienen instrucciones para llevar a cabo cada una de estas tareas.

## En esta sección

  - [Configuración del servicio de administración principal](lync-server-2013-configuring-the-primary-management-server.md)

  - [Instalación de los paquetes de administración de Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configuración de los equipos Lync Server sometidos a supervisión](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Instalación y configuración de nodos de monitor](lync-server-2013-installing-and-configuring-watcher-nodes.md)

