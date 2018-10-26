---
title: "Lync Server 2013: Funciones no compatibles con enrutamiento basado en ubicación"
TOCTitle: Capacidades no compatibles con el enrutamiento basado en ubicación
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994071(v=OCS.15)
ms:contentKeyID: 52061738
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-12_

El enrutamiento basado en ubicación no se aplica a los siguientes tipos de interacciones. Este método de enrutamiento no se lleva a cabo cuando los extremos de Lync interactúan con los extremos RTC que utilizan estas capacidades.

  - Marcación RTC para conferencias

  - Llamadas RTC entrantes y salientes a través del Grupo de respuesta

  - Estacionamiento o recuperación de llamadas RTC mediante Estacionamiento de llamadas

  - Llamadas RTC entrantes al servicio de anuncio

  - Llamadas RTC entrantes recuperadas mediante la atención de llamadas de grupo

Para aplicar las reglas de enrutamiento basado en ubicación a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento basado en ubicación para conferencias:

  - Iniciar llamadas RTC desde una conferencia

  - Escalaciones desde conversaciones de punto a punto a conferencias en las que haya extremos RTC

  - Consultas de transferencia con extremos RTC

Para activar el enrutamiento basado en ubicación para las conferencias, consulte [Enrutamiento basado en ubicación para las conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

## Vea también

#### Otros recursos

[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

