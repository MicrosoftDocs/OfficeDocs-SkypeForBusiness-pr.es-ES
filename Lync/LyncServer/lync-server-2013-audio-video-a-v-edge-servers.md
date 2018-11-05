---
title: Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013
TOCTitle: Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49889538
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V permite que los usuarios internos (usuarios conectados a la red de la organización) compartan audio y vídeo con usuarios externos (usuarios no conectados a la red de la organización). Además de audio y vídeo, el servicio perimetral A/V permite compartir el escritorio y transferir archivos, entre otras tareas.

El servicio perimetral A/V se administra principalmente con la configuración del servidor perimetral A/V. Estas opciones permiten administrar la cantidad máxima de ancho de banda que se asignará por puerto y por usuario, y especificar el tiempo durante el que se puede usar un token de autenticación antes de que se deba renovar. Las opciones de configuración del servidor perimetral A/V se pueden aplicar a sitios o a servidores perimetrales A/V individuales. Cuando determine qué colección de opciones tendrá prioridad, use la siguiente guía:

  - Las opciones configuradas en el ámbito de servicio (es decir, en un servidor individual) tienen prioridad sobre todo lo demás.

  - Las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones configuradas en el ámbito global. Pero las opciones del ámbito de servicio tienen prioridad sobre las opciones del ámbito de sitio.

  - Las opciones configuradas en el ámbito global se usarán solo si no hay opciones de servicio configuradas en el servidor individual y si no hay opciones de sitio configuradas para el sitio en el que se encuentra el servidor.

El servicio perimetral A/V solo se puede administrar con Lync Server PowerShell y los cmdlets CsAVEdgeConfiguration.

## En esta sección

  - [Devolución de información de configuración del servidor perimetral de A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Creación o modificación de conjuntos de opciones de configuración del servidor perimetral A/V](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Eliminación de un conjunto existente de opciones de configuración del servidor perimetral A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

