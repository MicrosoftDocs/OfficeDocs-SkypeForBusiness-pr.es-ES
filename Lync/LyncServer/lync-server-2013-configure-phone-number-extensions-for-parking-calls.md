---
title: Configurar extensiones de números de teléfono para estacionar llamadas
TOCTitle: Configurar extensiones de números de teléfono para estacionar llamadas
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48277287
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar extensiones de números de teléfono para estacionar llamadas

 

_**Última modificación del tema:** 2012-09-10_

La Aplicación de estacionamiento de llamadas utiliza números de extensión en la tabla de órbitas del Estacionamiento de llamadas para estacionar las llamadas. Deberá configurar la tabla de órbitas del Estacionamiento de llamadas con los intervalos de números de extensión reservados por su organización para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores de Lync Server donde se implemente y se configure una Aplicación de estacionamiento de llamadas puede tener uno o más intervalos de órbitas. Los intervalos de órbitas deben ser únicos en el nivel global en toda la implementación de Lync Server.

> [!IMPORTANT]  
> Debe seleccionar la casilla <strong>Habilitar estacionamiento de llamadas</strong> en la directiva de voz antes poder utilizar el estacionamiento de llamadas. De forma predeterminada, esta opción no está seleccionada.



## En esta sección

  - [Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [Eliminar un intervalo de órbitas para estacionamiento de llamadas en Lync Server 2013](lync-server-2013-delete-a-call-park-orbit-range.md)

