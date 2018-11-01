---
title: 'Lync Server 2013: Consideraciones sobre coexistencia y migración para IPv6'
TOCTitle: Consideraciones sobre coexistencia y migración para IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48275953
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consideraciones sobre coexistencia y migración para IPv6 en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-14_

IP versión 6 (IPv6) no es compatible con Lync Server 2010 o Office Communications Server. Para fines de experimentación, puede probar la existencia de pila dual de Lync Server 2010 y Lync Server 2013. Se recomienda que todos los grupos de un sitio central determinado se actualicen a Lync Server 2013antes de habilitar IPv6 (red de doble pila) para cualquiera de los grupos. Si necesita configurar un grupo solo para IPv6, se recomienda configurar un grupo de servidores solo IPv6 en su entorno de prueba.

Se admiten los siguientes escenarios durante la migración y coexistencia:

  - Los grupos de servidores Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2 en el modo IPv4, coexisten con Lync Server 2013 en el modo de pila dual.

  - grupo de Lync Server 2013 en modo de solo IPv6, si el grupo solo IPv6 se encuentra aislado.

