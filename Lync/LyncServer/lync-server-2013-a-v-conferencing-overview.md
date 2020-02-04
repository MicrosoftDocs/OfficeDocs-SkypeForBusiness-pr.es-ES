---
title: Información general de conferencia de Lync Server 2013 A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Información general sobre las conferencias A/V en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-13_

La conferencia A/V permite comunicaciones de audio y vídeo en tiempo real entre los usuarios. Al implementar las conferencias, puede elegir entre habilitar y usar conferencias web y conferencias A/V, o simplemente conferencias web.

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico.

Antes de habilitar a los usuarios para conferencias de A/V, asegúrese de que su red puede controlar la carga resultante. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida. Puede usar control de admisión de llamadas (CAC) para administrar el ancho de banda de red usado por conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitados entre los sitios centrales y de sucursal. Para obtener más información, vea [información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Para obtener más información sobre los requisitos de ancho de banda de multimedia, consulte [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si implementa las audioconferencias en su red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en las audioconferencias. Si implementa las videoconferencias, necesita implementar dispositivos de vídeo, como cámaras web para los usuarios. Le recomendamos que use dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, para garantizar una experiencia de usuario óptima. Para obtener más información sobre los dispositivos certificados por UC, consulte "teléfonos y dispositivos para [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)Lync" en. Para los dispositivos de audio o vídeo, la implementación de dispositivos y el aprendizaje del usuario, es importante tener en cuenta y planear.

En las siguientes secciones se describen las características de las conferencias de audio y vídeo, incluida la información sobre la administración del ancho de banda y la selección de los clientes apropiados.

<div>

## <a name="audio-conferencing-features"></a>Características de las conferencias de audio

Lync Server 2013 ofrece varias características que puede usar para configurar la experiencia de audioconferencia para el usuario, entre las que se incluyen las siguientes:

  - **Silencio**   de la audiencia el moderador puede usar esta configuración para silenciar a todos los participantes de audio de la Conferencia y poner la Conferencia en un estado en el que los usuarios no pueden reactivar el micrófono.

  - **Entrada de conferencia/salida de anuncios**   si ha habilitado las conferencias de acceso telefónico local, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada y salida a fin de minimizar las distracciones mientras una conferencia está en curso.

  - **Agregar un usuario marcando**   los moderadores y los asistentes a los que se le ha concedido permiso pueden agregar números de RTC a las conferencias y hacer que la Conferencia se llame a esos números.

</div>

<div>

## <a name="video-conferencing-features"></a>Características de videoconferencias

Lync Server 2013 ofrece varias características que puede usar para configurar la experiencia de videoconferencia para el usuario, entre las que se incluyen las siguientes:

  - **Vista de Galería**   en las videoconferencias que tengan más de dos personas, los usuarios verán automáticamente a todos los participantes de la Conferencia. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado. Para obtener detalles sobre la configuración o desactivación del vídeo de varias partes, vea [configurar el ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vídeo panorámico si**   un dispositivo de videoconferencia Roundtable está instalado en el salón de conferencias, esta característica proporciona una vista completa de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.

  - **Moderador solo**   los moderadores de modo de vídeo pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.

  - ****   Los usuarios de video de alta definición pueden experimentar resoluciones de hasta 1080p HD en llamadas de dos participantes y en conferencias de varias partes.

  - ****   Los moderadores de Spotlight de vídeo pueden configurar la reunión para que los demás participantes de la Conferencia solo vean el vídeo de un participante seleccionado que sea una fuente de video. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

