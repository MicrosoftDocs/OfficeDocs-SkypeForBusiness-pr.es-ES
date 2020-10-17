---
title: Lync Server 2013 información general sobre conferencias A/V
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
ms.openlocfilehash: f35ef9adaf4f19023ebe2220494fdb315c782515
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523267"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Información general sobre la conferencia A/V en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-13_

Las conferencias A/V permiten las comunicaciones de audio y vídeo en tiempo real entre los usuarios. Cuando se implementan conferencias, puede optarse por habilitar y usar conferencia web y conferencia A/V, o únicamente conferencia web.

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico.

Antes de permitir que los usuarios realicen conferencias A/V, asegúrese de que la red pueda administrar la carga resultante. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida. Puede usar control de admisión de llamadas (CAC) para administrar el ancho de banda de red que usan las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitado entre los sitios central y de sucursal. Para obtener más información, consulte [información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Para obtener más información sobre los requisitos de ancho de banda de medios, consulte [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si implementa una conferencia de audio en la red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en ella. Si implemente una conferencia de vídeo, necesitará implementar dispositivos de vídeo, como cámaras web para los usuarios. Le recomendamos que use dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, para garantizar una experiencia de usuario óptima. Para obtener más información sobre los dispositivos certificados para UC, consulte "teléfonos y dispositivos para Lync" en [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) . Tanto para los dispositivos de audio como los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta y planear.

En las secciones siguientes se describen las características de las conferencias de audio y vídeo, incluida información sobre cómo administrar el ancho de banda y seleccionar los clientes apropiados.

<div>

## <a name="audio-conferencing-features"></a>Características de las conferencias de audio

Lync Server 2013 proporciona varias características que puede usar para configurar la experiencia de audioconferencia del usuario, entre las que se incluyen las siguientes:

  - Silencio de la **audiencia**     El moderador puede usar esta configuración para silenciar a todos los participantes de audio de la Conferencia y poner la Conferencia en un estado en el que no los moderadores no puedan reactivarse.

  - Anuncios de entrada **y salida de conferencia**     Si ha habilitado las conferencias de acceso telefónico local, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada y salida para minimizar las distracciones mientras una conferencia está en curso.

  - **Adición de un usuario mediante llamadas salientes**     Los moderadores y asistentes a los que se haya concedido permiso pueden agregar números RTC a las conferencias y hacer que la Conferencia realice llamadas de salida a esos números.

</div>

<div>

## <a name="video-conferencing-features"></a>Características de las conferencias de vídeo

Lync Server 2013 proporciona varias características que puede usar para configurar la experiencia de las conferencias de vídeo del usuario, entre las que se incluyen las siguientes:

  - **Vista**     de Galería En las conferencias de vídeo que tienen más de dos personas, los usuarios ven automáticamente a todos los usuarios de la Conferencia. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado. Para obtener información detallada acerca de la configuración o desactivación de vídeo entre varias partes, consulte [configuración del ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vídeo panorámico**     Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista completa de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.

  - Modo de vídeo **solo Presenter**     Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.

  - **Vídeo HD**     Los usuarios pueden experimentar resoluciones de hasta HD 1080P en llamadas de dos participantes y conferencias con varios participantes.

  - **Foco**     de vídeo Los moderadores pueden configurar la reunión para que los otros participantes de la Conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

