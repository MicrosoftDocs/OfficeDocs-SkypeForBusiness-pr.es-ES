---
title: 'Lync Server 2013: Requisitos técnicos para IPv6'
TOCTitle: Requisitos técnicos para IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48276680
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para IPv6 en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Si planea configurar Lync Server 2013 para IPv6, recuerde los siguientes requisitos:

  - Para usar direcciones IPv6 con Lync Server, tiene que crear registros de sistema de nombres de dominio (DNS) para los registros que deben detectarse y resolverse en una dirección IPv6. El DNS de IPv6 usa registros AAAA de host (A cuádruple). Si usa IPv4 e IPv6 en la implementación, es mejor configurar y guardar los registros A de host para IPv4 y los registros AAAA de host para IPv6. Aun cuando pase completamente la implementación a IPv6, pueden ser necesarios registros de host DNS IPv4 para los usuarios externos que todavía usen IPv4.
    
    Puede implementar los registros de host DNS IPv6 antes de empezar a usar IPv6. Si el cliente o el servidor no usan IPv6, el registro no será referenciado. Las tecnologías de transición tomarán la decisión sobre qué registro usar, sobre la base de las directivas y la configuración de la tecnología de transición.

  - Cada dirección de IPv6 tiene un ámbito. Los tres ámbitos que puede usar para el direccionamiento de IPv6 son las direcciones globales de IPv6 (similares a las direcciones de IPv4 públicas), las direcciones locales únicas de IPv6 (similares a los intervalos de direcciones de IPv4 privadas) y las direcciones locales de vínculo de IPv6 (similares a las direcciones IP privadas automáticas en Windows Server para IPv4). Todos los servidores de un grupo deben tener direcciones IPv6 con el mismo ámbito.

> [!IMPORTANT]  
> IPv6 es un tema complejo y requiere una cuidadosa planeación con el equipo de conexión de redes y el proveedor de servicios de internet para que las direcciones que se asignen en el nivel de Windows Server y en el nivel de Lync Server 2013 funcionen correctamente. Vea los vínculos del final de este tema para conocer otros recursos sobre la planeación y el direccionamiento de IPv6.



## Vea también

#### Otros recursos

[Arquitectura de direccionamiento de IP Versión 6](http://tools.ietf.org/html/rfc4291)  
[Formato de dirección de unidifusión global de IPv6](http://tools.ietf.org/html/rfc3587)  
[Direcciones de unidifusión IPv6 locales únicas](http://tools.ietf.org/html/rfc4193)

