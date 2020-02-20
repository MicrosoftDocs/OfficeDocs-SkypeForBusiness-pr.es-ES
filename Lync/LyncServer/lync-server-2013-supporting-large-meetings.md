---
title: 'Lync Server 2013: compatibilidad con reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d1ba298ea35c177eb51191c230ea51a50d6c3e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Compatibilidad con reuniones grandes con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Las reuniones grandes no siguen el modelo de prueba descrito en la sección anterior porque tienen las siguientes características:


  - El formato de la reunión es una presentación de uno a varios.

  - Uno o unos pocos usuarios son presentadores y todo el mundo participa solo como asistentes.

  - El uso compartido de una presentación de PowerPoint es la actividad principal de colaboración de datos.

  - Se necesita audio y también se puede usar vídeo.

  - Una persona dedicada, generalmente el organizador de la reunión o un asistente del organizador, configura la reunión con suficiente antelación.

  - El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y el salón de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.

La compatibilidad con grandes reuniones de hasta 1.000 usuarios requiere abordar problemas relacionados con el modelo de hardware compartidos y el modelo sin reserva.

Para disponer de suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end de hospedaje no deben hospedar otras cargas de trabajo de mensajería instantánea (mi) y presencia o de telefonía IP empresarial. Tampoco debe alojar otras reuniones, independientemente de su tamaño. Esto significa que para hospedar reuniones de hasta 1000 usuarios es necesario configurar un grupo de Lync Server independiente dedicado a hospedar grandes reuniones de hasta 1000 usuarios.

Un grupo de servidores de Lync Server dedicado a hospedar reuniones grandes debe hospedar una sola reunión de hasta 1000 usuarios al mismo tiempo, por lo que las horas de reunión deben reservarse por adelantado a través de un proceso de programación fuera de banda para garantizar el soporte dedicado desde el serv front-end ers. Para admitir más de una gran reunión al mismo tiempo, recomendamos configurar varios grupos de grandes reuniones dedicados.

Recomendamos que una persona dedicada ejecute y supervise la parte en línea de una gran reunión. Esta persona podría ser el organizador, el delegado del organizador o presentador, o un miembro del equipo de soporte técnico de la gran reunión, dependiendo de las preferencias de la organización.

En las secciones siguientes, se describe cómo implementar un grupo dedicado para reuniones grandes, incluidos los procedimientos recomendados para usar Lync Server 2013 para admitir escenarios de reuniones grandes.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configuración de la compatibilidad para reuniones grandes en Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Administración de reuniones grandes en Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

