---
title: "Configuración de directivas de voz, registros de uso de RTC y rutas de voz"
TOCTitle: Configuración de directivas de voz, registros de uso de RTC y rutas de voz
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48274618
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-10_

Las directivas de voz, los registros de uso de RTC y las rutas de voz son aspecto totalmente relacionados. Para configurar las directivas de voz debe seleccionar un grupo de características de llamada y luego asignar a la directiva un grupo de registros de uso de RTC, que especifican los derechos que se otorgarán a los usuarios o grupos a los que se les asigne la directiva de voz. A las rutas de voz también se les asignan registros de uso de RTC, que sirven para asociar las rutas con los usuarios autorizados para usarlas. Es decir, los usuarios solo pueden realizar llamadas que usan rutas para las que tienen registros de uso de RTC coincidentes.

El flujo de trabajo recomendado para una nueva implementación de Enterprise Voice es comenzar configurando una directiva de voz que incluya los registros de uso de RTC adecuados y, a continuación, asociar las rutas apropiadas para cada registro de uso de RTC.


> [!NOTE]
> También puede crear directivas de voz con ámbito de <EM>usuario</EM> y asignarlas a usuarios individuales o grupos.



Para consultar los pasos detallados que se deben seguir para realizar cada una de estas tareas, consulte los procedimientos que se explican en esta sección.

## En esta sección

  - [Configurar directivas de voz y registros de uso de la RTC para autorizar características y privilegios de llamada en Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Ver registros de uso de la RTC en Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configuración de rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Exportar e importar la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)

