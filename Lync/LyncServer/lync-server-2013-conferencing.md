---
title: Lync Server 2013 conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3f2a27e252a3e152958a45d53794216308be68e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Con las conferencias unificadas en Lync Server 2013, los usuarios pueden colaborar, compartir información y coordinar sus esfuerzos en tiempo real. Los usuarios pueden usar todas las herramientas de reuniones, reuniones programadas y colaboración espontánea. Las capacidades de conferencia de voz y vídeo se pueden usar desde cualquier ubicación con conexión a Internet; además, los usuarios que estén lejos de su equipo pueden participar en las conferencias de audio mediante un teléfono de red telefónica conmutada (RTC).

Herramientas de reunión integradas en Outlook habilite los organizadores para programar una reunión o para iniciar una conferencia improvisada con un solo clic y hacer que sea tan fácil unirse a los asistentes. Un cliente web amplía características de conferencia enriquecidas a los participantes que no ejecutan la versión de escritorio de Lync.

<div>

## <a name="audio-and-video-conferencing"></a>Conferencia de audio y vídeo

Lync Server proporciona una experiencia de usuario que está familiarizada con los usuarios de los servicios de puente de audio tradicionales, incluidos los servicios de acceso telefónico RTC con comandos de control de llamadas de tonos. Al mismo tiempo, incorpora potentes funciones de programación, unión y administración disponibles únicamente con una plataforma integrada de comunicaciones unificadas.

Con un solo clic, los usuarios pueden programar una reunión desde Outlook. Los detalles, como la hora de la reunión, la ubicación y los asistentes, siguen la conocida plantilla de Outlook. Además, la información específica de la llamada de conferencia como, por ejemplo, el número de acceso telefónico, los Id. de la reunión y los recordatorios del número de identificación personal (PIN) se rellenan automáticamente.

Para ayudar a garantizar que solo las personas autorizadas participen en una llamada, Lync Server proporciona varios niveles de autenticación a los participantes. Los usuarios que se unen a través de Lync ya están autenticados por los servicios de dominio de Active Directory y no necesitan especificar un PIN, un código de acceso o un identificador de reunión.

Lync simplifica la experiencia de usuario de videoconferencia mediante la incorporación de vídeo en el cliente unificado, de modo que la programación de una reunión con vídeo o el aumento de la escalabilidad del vídeo de forma espontánea es sencilla y sencilla.

Lync Server facilita la tarea de agregar vídeo a una llamada de teléfono estándar con tan solo un clic. Si una llamada de vídeo o una conferencia tiene varios participantes, cada usuario podrá ver vídeos de hasta cinco usuarios distintos al mismo tiempo, o el moderador podrá decidir que todo el mundo vea un único origen de vídeo.

Vídeo de alta definición (resolución 1270 x 720; relación de aspecto 16:9) y vídeo VGA (resolución 640 x 480; relación de aspecto 4:3) se admiten para las llamadas punto a punto entre usuarios que ejecutan Lync en equipos high-end. La resolución captada por cada participante en una conversación única puede diferir, dependiendo de las características de vídeo del hardware de cada usuario.

Los administradores de TI pueden establecer directivas para restringir o deshabilitar vídeo de alta definición o vídeo VGA en clientes, dependiendo de la capacidad del equipo, del ancho de banda de red y de la presencia de una cámara con características para proporcionar la resolución requerida. Estas directivas se exigen a través del aprovisionamiento en banda.

</div>

<div>

## <a name="web-conferencing"></a>Conferencia web

Lync Server integra características de uso compartido de conferencias como escritorio, aplicación, datos adjuntos, pizarra, sondeo y PowerPoint en el Lync simplificado. En combinación con las conferencias de audio y vídeo, el resultado es una sesión de gran inmersión y colaboración que se pone a disposición muy fácilmente.

Para mejorar la experiencia general de los usuarios que presentan o ven presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps para controlar las presentaciones de PowerPoint. Los usuarios pueden compartir una imagen, o copiar y pegar texto mediante una pizarra en la reunión de Lync. Los moderadores pueden realizar sondeos en la reunión de Lync para solicitar comentarios de los asistentes.

El uso compartido de escritorio permite a los moderadores difundir los elementos visuales, las aplicaciones, las páginas web, los documentos, el software o parte de sus escritorios a los participantes remotos en tiempo real, directamente desde Lync. La audiencia puede realizar el seguimiento junto con los movimientos del ratón y las entradas del teclado. Los moderadores pueden elegir entre compartir toda su pantalla o solo una parte. Al compartir sus escritorios, los moderadores pueden integrar a la audiencia en demostraciones interactivas de productos o software desde cualquier ubicación.

El uso compartido de aplicaciones permite a los moderadores compartir el control del software de sus escritorios sin perder de vista los comentarios de los participantes o las preguntas de texto. Asimismo, también pueden delegar el control de la aplicación a los participantes en la reunión.

</div>

<div>

## <a name="dial-in-conferencing"></a>Conferencia de acceso telefónico local

Para los usuarios que no usan un equipo personal, hay varios métodos disponibles para unirse a una llamada de conferencia de Lync Server. Un usuario de RTC puede marcar un número de acceso, obtener acceso al puente de la reunión y, a continuación, introducir el Id. de reunión. Para reuniones más seguras, puede que el usuario también tenga que introducir su PIN para autenticarse en Active Directory. Lync Server también admite dispositivos de Lync Phone Edition, que son dispositivos de telefonía IP independientes proporcionados por los socios de Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

