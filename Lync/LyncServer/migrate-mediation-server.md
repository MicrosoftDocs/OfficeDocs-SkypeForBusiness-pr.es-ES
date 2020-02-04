---
title: Migrar servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3478bb3bb837e44ed33597f72738b181b4c67561
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrar servidor de mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

El servidor de mediación se combina en su topología piloto de Lync Server 2013 cuando ejecuta el Asistente de combinación. Puede configurar el servidor de mediación de Lync Server 2013, sin embargo, después de migrar a todos los usuarios, porque un grupo de Office Communications Server 2007 R2 no se puede comunicar con un servidor de mediación de Lync Server 2013. Durante la migración en paralelo, el grupo de Lync Server 2013 se comunica con el servidor de mediación de Office Communications Server 2007 R2.

Al configurar el servidor de mediación de Lync Server 2013, también debe actualizar o reemplazar las puertas de enlace de Office Communications Server 2007 R2. Las puertas de enlace de Office Communications Server 2007 R2 no son compatibles con el servidor de mediación de Lync Server 2013. Debe implementar puertas de enlace que estén certificadas para Lync Server 2013 y asociarlas con el servidor de mediación de Lync Server 2013. Este paso es necesario para poder retirar por completo la implementación de Office Communications Server 2007 R2.

En los temas de esta sección se describen las tareas de configuración que necesita realizar después de completar la migración del servidor de mediación de Lync Server 2013. Realizar una transición entre el servidor de mediación que se encuentra en un servidor de mediación independiente es una tarea opcional.

  - [Configurar servidor de mediación](configure-mediation-server.md)

  - [Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transición de un servidor de mediación en un servidor de mediación independiente (opcional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

