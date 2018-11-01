---
title: "Lync Server 2013: Compatibilidad del sistema operativo con servidor y herramientas"
TOCTitle: Compatibilidad del sistema operativo con el servidor y las herramientas
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48276427
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013

 

_**Última modificación del tema:** 2016-05-19_

Lync Server 2013 solo está disponible en versiones de 64 bits, lo que requiere hardware de 64 bits y ediciones de 64 bits de Windows Server. Esto implica que todos los roles del servidor y los equipos que ejecuten las herramientas administrativas de Lync Server 2013 ejecutan un sistema operativo de 64 bits.

## Sistemas operativos para roles del servidor

Lync Server 2013 admite las ediciones de 64 bits de los siguientes sistemas operativos para todos los roles de servidor en Lync Server 2013:

  - El sistema operativo Windows Server 2008 R2 Standard con Service Pack 1 (SP1) (obligatorio) o el último Service Pack (recomendado)

  - El sistema operativo Windows Server 2008 R2 Enterprise con SP1 (obligatorio) o el último Service Pack (recomendado)

  - El sistema operativo Windows Server 2008 R2 Datacenter con SP1 (obligatorio) o el último Service Pack (recomendado)

  - El sistema operativo Windows Server 2012 Standard

  - El sistema operativo Windows Server 2012 Datacenter

  - Los sistemas operativos Windows Server 2012 R2 son compatibles con el Actualizaciones acumulativas para Lync Server 2013: octubre de 2013.

Lync Server 2013 no se admite en los siguientes sistemas operativos:

  - La opción de instalación Server Core de Windows Server 2008 R2 o Windows Server 2012

  - El sistema operativo Windows Web Server 2008 R2 o el sistema operativo Windows Web Server 2012

  - Windows Server 2008 R2 HPC Edition o Windows Server 2012 HPC Edition

## Sistemas operativos adicionales para herramientas administrativas

Las herramientas administrativas de Lync Server 2013 se instalan de manera predeterminada en los servidores que ejecutan Lync Server 2013, pero puede instalar herramientas administrativas de forma independiente en otros equipos que ejecuten sistemas operativos Windows. Esto incluye las versiones de 64 bits de los siguientes sistema operativos, además de las ediciones de 64 bits de los sistemas operativos admitidos para la implementación de roles del servidor (como se describe en la sección anterior).

  - El sistema operativo Sistema operativo Windows 7 con SP1 (obligatorio) o el último Service Pack (recomendado)

  - El sistema operativo Windows 8 o el último Service Pack (recomendado)

  - El sistema operativo Windows 8.1 o el último Service Pack (recomendado)

## Sistemas operativos para otros servidores en su implementación

  - Para obtener información detallada sobre los requisitos de los servidores back-end y otros servidores de bases de datos, vea [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).

  - Para obtener información detallada sobre los requisitos de los servidores proxy inversos (para la implementación de servidores perimetrales), vea [Compatibilidad con IIS en Lync Server 2013](lync-server-2013-iis-support.md).

  - Para obtener información detallada sobre otros requisitos de software, incluida la compatibilidad con la infraestructura y la virtualización, vea los otros temas de la sección [Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

