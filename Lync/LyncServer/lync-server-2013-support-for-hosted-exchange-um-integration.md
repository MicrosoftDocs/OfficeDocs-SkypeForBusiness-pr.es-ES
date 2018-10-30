---
title: " Compatibilidad con la integración de mensajería unificada de Exchange hospedada"
TOCTitle: Compatibilidad con la integración de mensajería unificada de Exchange hospedada
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48276636
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

La aplicación sw Lync Server 2013 ExUM Routing es compatible con la integración con Mensajería unificada de Exchange (UM) en un entorno local, donde Lync Server 2013 y Mensajería unificada de Exchange se instalan ambas localmente en el entorno empresarial o bien, con Mensajería unificada de Exchange que hospeda un proveedor de servicios, tal como se muestra en el diagrama siguiente.

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

Se admiten los siguientes modos:

  - **Modo local**    Lync Server 2013 y Mensajería unificada de Exchange se implementan ambos en servidores locales en la empresa.

  - **Modo externo**    Lync Server 2013 se implementa en servidores locales en la empresa y Mensajería unificada de Exchange se hospeda en las instalaciones de un proveedor de servicios en línea, como un centro de datos de Microsoft Exchange Online.

  - **Modo mixto**   La implementación de Lync Server 2013 tiene algunos buzones de usuario ubicados en servidores locales que se ejecutan en Microsoft Exchange Server en la empresa y otros buzones de usuario en un centro de datos de servicio de Exchange hospedado.
    

    > [!NOTE]
    > El modo mixto se puede usar a modo de solución transitoria durante la evaluación y migración paso a paso de usuarios a Mensajería unificada de Exchange hospedado o bien, como solución permanente si opta por mantener algunos servicios de Mensajería unificada de Exchange de los usuarios de forma local tras haber migrado otros.



Para integrar Lync Server 2013 con Mensajería unificada de Exchange hospedada, debe configurar un *espacio de direcciones SIP compartido* (también denominado *dominio dividido* ). En esta configuración, Lync Server 2013 y el proveedor de servicios de Mensajería unificada de Exchange hospedada por un tercero pueden tener acceso al mismo espacio de dirección de dominio SIP. Para obtener información detallada, consulte [Arquitectura de integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) en la documentación referente a la planeación.

