---
title: 'Lync Server 2013: Conmutación por error del almacén de administración central'
TOCTitle: Conmutación por error del almacén de administración central
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48277167
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error del almacén de administración central en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-18_

Almacén de administración central contiene datos de configuración sobre servidores y servicios en su implementación de Lync 2013. Ofrece un sistema sólido y esquematizado de almacenamiento de los datos necesarios para definir, configurar, mantener, administrar, describir y operar una implementación de Lync 2013. También valida los datos para garantizar la coherencia de la configuración.

Cada implementación de Lync incluye un Almacén de administración central, hospedado por el Servidor back-end de un Grupo de servidores front-end.

Si establece un emparejamiento de grupo de servidores que incluye el grupo que hospeda Almacén de administración central, se configura una base de datos de Almacén de administración central de copia de seguridad en el grupo de copia de seguridad y se instalan servicios de Almacén de administración central en ambos grupos de usuarios. En cualquier momento, una de las dos bases de datos de Almacén de administración central será el maestro activo y la otra estará en espera. El contenido se replica por parte del servicio de copia de seguridad desde el maestro activo a la base de datos en espera.

Durante una conmutación por error de un grupo de servidores que implique a los grupos de servidores que hospedan Almacén de administración central, el administrador deberá conmutar por error Almacén de administración central antes de conmutar por error el Grupo de servidores front-end.

Una vez reparado el desastre, no es necesario realizar la conmutación por error de Almacén de administración central. Después de la reparación, Almacén de administración central en el grupo de servidores de copia de seguridad original puede permanecer como maestro activo.

Los objetivos de ingeniería para la conmutación por error de Almacén de administración central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para el objetivo de punto de recuperación (RPO).

