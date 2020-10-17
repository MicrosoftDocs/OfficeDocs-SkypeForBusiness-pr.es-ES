---
title: Lync Server 2013 conmutación por error del almacén de administración central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508047"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Conmutación por error del almacén de administración central en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

El almacén de administración central contiene datos de configuración sobre los servidores y los servicios de la implementación de Lync 2013. Proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y usar una implementación de Lync 2013. También valida los datos para garantizar la coherencia de la configuración.

Cada implementación de Lync incluye un almacén de administración central, hospedado por el servidor back-end de un grupo de servidores front-end.

Cuando establece un emparejamiento de grupo de servidores que incluye el grupo que hospeda el almacén de administración central, se configura una base de datos de almacén de administración central de copia de seguridad en el grupo de copia de seguridad y los servicios de almacén de administración central se instalan en ambos grupos. En cualquier momento, una de las dos bases de datos del almacén de administración central es Active Master y la otra es un modo de espera. El contenido se replica por parte del servicio de copia de seguridad desde el maestro activo a la base de datos en espera.

Durante una conmutación por error de un grupo de servidores que implica a los grupos que hospedan el almacén de administración central, el administrador debe conmutar por error el almacén de administración central antes de realizar la conmutación por error del grupo

Una vez reparado el desastre, no es necesario realizar una conmutación por recuperación del almacén de administración central. Después de la reparación, el almacén de administración central del grupo de copia de seguridad original puede permanecer como maestro activo.

Los objetivos de ingeniería para la conmutación por error del almacén de administración central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para el objetivo de punto de recuperación (RPO).

</div>

<span> </span>

</div>

</div>

</div>

