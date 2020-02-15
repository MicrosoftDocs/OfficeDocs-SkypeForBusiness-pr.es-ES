---
title: 'Lync Server 2013: alta disponibilidad de uso compartido de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453b4c63f58f6153092dae0259155dbfa72b5eca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Alta disponibilidad de uso compartido de archivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-03-30_

Para garantizar la alta disponibilidad para el uso compartido de archivos de Lync Server en un solo centro de datos, puede usar el sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro del mismo centro de datos. Para una implementación a gran escala, recomendamos que use servidores de archivos dedicados que se emparejen mediante DFS.

En función del tamaño de la red y de la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos de un sitio o usar un par por grupo de servidores front-end.

DFS es un mecanismo de replicación de archivos de tipo “mejor esfuerzo” (best effort), sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. La conmutación por error entre los servidores DFS debe realizarse rápidamente, pero el retraso en la replicación de datos puede impedir que los usuarios continúen el trabajo en curso cuando tenga lugar la conmutación por error.

Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, debe realizar una copia de seguridad de los usos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.

</div>

<span> </span>

</div>

</div>

</div>

