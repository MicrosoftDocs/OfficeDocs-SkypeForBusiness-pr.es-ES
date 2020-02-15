---
title: Migrar el servidor de mediación
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
ms.openlocfilehash: 581ce96b0c0a6ad0e4edd68eddbfacb160bf13f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Migrar el servidor de mediación

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

El servidor de mediación se combina en su topología piloto de Lync Server 2013 al ejecutar el Asistente de combinación. No obstante, puede configurar el servidor de mediación de Lync Server 2013 después de migrar todos los usuarios porque un grupo de servidores de Office Communications Server 2007 R2 no puede comunicarse con un servidor de mediación de Lync Server 2013. Durante la migración en paralelo, el grupo de servidores de Lync Server 2013 se comunica con el servidor de mediación de Office Communications Server 2007 R2.

Cuando configure el servidor de mediación de Lync Server 2013, también debe actualizar o reemplazar las puertas de enlace de Office Communications Server 2007 R2. Las puertas de enlace de Office Communications Server 2007 R2 no admiten el servidor de mediación de Lync Server 2013. Debe implementar puertas de enlace que estén certificadas para Lync Server 2013 y asociarlas con el servidor de mediación de Lync Server 2013. Este paso es necesario para poder retirar por completo la implementación de Office Communications Server 2007 R2.

En los temas de esta sección se describen las tareas de configuración que debe realizar una vez que haya completado la migración del servidor de mediación de Lync Server 2013. La transición del servidor de mediación combinado a un servidor de mediación independiente es una tarea opcional.

  - [Configurar el servidor de mediación](configure-mediation-server.md)

  - [Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Transición de un servidor de mediación combinado a un servidor de mediación independiente (opcional)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

