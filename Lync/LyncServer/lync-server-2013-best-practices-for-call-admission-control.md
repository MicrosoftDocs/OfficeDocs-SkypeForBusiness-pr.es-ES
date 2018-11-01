---
title: "Procedimientos recomendados para el servicio de control de admisión de llamadas"
TOCTitle: Procedimientos recomendados para el servicio de control de admisión de llamadas
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48276096
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

Para mejorar el rendimiento y facilitar la implementación, siga los procedimientos recomendados descritos a continuación a la hora de implementar el control de admisión de llamadas:

  - Compruebe que las redes WAN estén correctamente aprovisionadas para el tráfico de medios actual y previsto.
    

    > [!NOTE]
    > Se recomienda tener en cuenta un búfer además de los límites de ancho de banda. Existen escenarios, como condiciones de carrera, que afectan al ancho de banda total usado y pueden dar lugar a situaciones en que se supera el límite de ancho de banda. Por ejemplo, si se intentan iniciar dos llamadas cuando el tráfico de medios está alcanzando un límite de ancho de banda, es posible que una de ellas sea denegada porque la otra intentó iniciarse primero.



  - Supervise el uso de red y los registros de detalles de llamadas para que pueda elegir una configuración óptima de control de admisión de llamadas y actualizarla conforme el uso de la red va cambiando.

  - Use directivas de ancho de banda de control de admisión de llamadas para complementar la configuración de QoS.

  - Si desea volver a enrutar llamadas bloqueados a la RTC, compruebe la capacidad y las funciones de la RTC. Para obtener información detallada, consulte [Planeación del enrutamiento de voz saliente en Lync Server 2013](lync-server-2013-planning-outbound-voice-routing.md).
    

    > [!NOTE]
    > La capacidad hace referencia al número de puertos que necesita abrir para poder volver a enrutar la RTC.


