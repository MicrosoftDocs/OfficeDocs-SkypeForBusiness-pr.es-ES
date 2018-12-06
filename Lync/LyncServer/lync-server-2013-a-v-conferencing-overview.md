---
title: Descripción general de conferencias de A/V en Lync Server 2013
TOCTitle: Descripción general de conferencias de A/V en Lync Server 2013
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49115301
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Descripción general de conferencias de A/V en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Las conferencias A/V permiten las comunicaciones de audio y vídeo en tiempo real entre los usuarios. Cuando se implementan conferencias, puede optarse por habilitar y usar conferencia web y conferencia A/V, o únicamente conferencia web.

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico.

Antes de permitir que los usuarios realicen conferencias A/V, asegúrese de que la red pueda administrar la carga resultante. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida. Puede usar control de admisión de llamadas (CAC) para administrar el ancho de banda de red que usan las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitado entre los sitios central y de sucursal. Para obtener información adicional, consulte [Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Para obtener más información sobre los requisitos de ancho de banda de medios, consulte [Requisitos de ancho de banda de red para el tráfico multimedia de Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si implementa una conferencia de audio en la red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en ella. Si implemente una conferencia de vídeo, necesitará implementar dispositivos de vídeo, como cámaras web para los usuarios. Se recomienda usar dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivo con el fin de garantizar una experiencia óptima para el usuario. Para obtener más información acerca de los dispositivos certificados para UC, consulte "Teléfonos y dispositivos para Lync" en [http://go.microsoft.com/fwlink/?linkid=263861\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=263861%26clcid=0xc0a). Tanto para los dispositivos de audio como los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta y planear.

En las secciones siguientes se describen las características de las conferencias de audio y vídeo, incluida información sobre cómo administrar el ancho de banda y seleccionar los clientes apropiados.

## Características de las conferencias de audio

Lync Server 2013 dispone de varias características que puede usar para configurar la experiencia de las conferencias de audio para el usuario, entre las que se incluyen las siguientes:

  - **Desactivación del audio de la audiencia**   El moderador puede usar esta opción para desactivar el audio de todos los participantes en la conferencia y poner la conferencia en un estado en el que los participantes que no son moderadores no puedan activar su audio.

  - **Anuncios de entrada y salida de las conferencias**   Si ha habilitado las conferencias de acceso telefónico, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada para minimizar las distracciones cuando una conferencia está en curso.

  - **Agregar un usuario mediante llamadas de salida**   Los moderadores y asistentes a los que se haya concedido permiso pueden agregar números RTC a las conferencias y hacer que la conferencia realice llamadas de salida a esos números.

## Características de las conferencias de vídeo

Lync Server 2013 dispone de varias características que puede usar para configurar la experiencia de las conferencias de vídeo para el usuario, entre las que se incluyen las siguientes:

  - **Vista de galería**   En las videoconferencias con más de dos personas, los usuarios se ven entre sí automáticamente. Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes. De forma predeterminada, el vídeo entre varias partes está activado. Para obtener más información sobre cómo configurar o desactivar el vídeo entre varias partes, consulte [Configuración de ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vídeo panorámico**   Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista de 360 grados de la sala de conferencias. La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.

  - **Modo de vídeo solo para moderador**   Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador. Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.

  - **Vídeo HD**   Los usuarios pueden disfrutar de resoluciones de hasta HD 1080P en llamadas a dos y conferencias entre varias partes.

  - **Primer plano de vídeo**   Los moderadores pueden configurar la reunión para que los participantes de la conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo. Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.

