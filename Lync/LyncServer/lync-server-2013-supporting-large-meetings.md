---
title: 'Lync Server 2013: compatibilidad con reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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

  - Una persona dedicada, generalmente el organizador de la reunión o un asistente al organizador, configura la reunión con antelación.

  - El personal dedicado (no los presentadores) ejecuta la reunión, incluida la conexión a una reunión en línea, la comprobación de que el uso compartido de audio, vídeo y diapositivas funciona, la administración de roles de usuario y la sala de espera, la activación y desactivación del silencio de los participantes, la realización de preguntas y la administración de grabaciones, según sea lo adecuado.

La compatibilidad con reuniones de gran tamaño de hasta 1000 usuarios requiere resolver los problemas relacionados con el modelo de hardware compartido y el modelo sin reserva.

Para tener suficientes recursos de CPU y memoria para reuniones de hasta 1000 usuarios, los servidores front-end que hacen de host no tienen que hospedar ninguna otra carga de trabajo de mensajería instantánea (MI), de presencia o de telefonía IP empresarial. Tampoco debe hospedar otras reuniones, independientemente del tamaño de las otras. Esto significa que las reuniones de hospedaje de hasta 1000 usuarios requieren la configuración de un grupo de servidores de Lync independiente dedicado a hospedar grandes reuniones de hasta 1000 usuarios.

Un grupo de Lync Server dedicado al hospedaje de reuniones grandes debe hospedar una y solo una reunión de hasta 1000 usuarios al mismo tiempo, de modo que las horas de reunión deben reservarse por adelantado a través de un proceso de programación fuera de banda para garantizar la compatibilidad exclusiva de serv de front-end ers. Para admitir más de una reunión de gran tamaño al mismo tiempo, recomendamos configurar varias agrupaciones de reuniones dedicadas.

Recomendamos que una persona dedicada ejecute y supervise la parte en línea de una reunión de gran tamaño. Esta persona podría ser el organizador, el delegado del organizador o moderador o un miembro del equipo de soporte técnico dedicado a grandes reuniones, según las preferencias de la organización.

En las siguientes secciones, se describe cómo implementar un grupo dedicado para reuniones grandes, incluidos los procedimientos recomendados para usar Lync Server 2013 para escenarios de reuniones grandes.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar la compatibilidad para reuniones grandes en Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Administración de reuniones grandes en Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

