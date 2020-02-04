---
title: 'Lync Server 2013: alta disponibilidad del uso compartido de archivos'
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
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Alta disponibilidad del uso compartido de archivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-03-30_

Para garantizar la alta disponibilidad del uso compartido de archivos de Lync Server en un solo centro de datos, puede usar el sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro dentro del mismo centro de datos. Para una implementación de gran escala, te recomendamos usar servidores de archivos dedicados que se emparejan con DFS.

Según el tamaño de la red y la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos en un sitio o usar un par por grupo de servidores front-end.

DFS es un mecanismo de replicación de archivos de mejor esfuerzo, sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. La conmutación por error entre los servidores DFS debe completarse rápidamente, pero el retraso de replicación de datos puede evitar que los usuarios puedan continuar trabajando en curso cuando se produzca la conmutación por error.

Si utiliza DFS y el almacén de datos en el recurso compartido es esencial, debe realizar una copia de seguridad de los recursos compartidos de archivos con frecuencia, como cada 4 a 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.

</div>

<span> </span>

</div>

</div>

</div>

