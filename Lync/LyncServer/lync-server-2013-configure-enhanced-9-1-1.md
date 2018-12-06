---
title: 'Lync Server 2013: Configurar 9-1-1 mejorado'
TOCTitle: Configurar 9-1-1 mejorado
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48275354
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar 9-1-1 mejorado en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-24_

9-1-1 mejorado (E9-1-1) es una característica de notificación de emergencia que asocia el número de teléfono de la persona que llama con una dirección postal o una calle. Mediante esta información, el PSAP (punto de respuesta de seguridad pública) puede enviar servicios de emergencia de forma inmediata a la persona que llama y tiene dificultades.

Para admitir E9-1-1, Lync Server 2013 debe poder asociar correctamente una ubicación a un cliente y asegurarse de que se usa esta información para enrutar la llamada de emergencia al PSAP más cercano.

Para obtener detalles sobre la planificación de una implementación de E9-1-1, vea [Planeación de los servicios de emergencia (E9-1-1) en Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

> [!IMPORTANT]  
> Lync Server 2013 solo admite el uso de E9-1-1 dentro de los Estados Unidos. Para implementar E9-1-1 tendrá que configurar una conexión SIP para un proveedor de servicios E9-1-1 certificado o implementar una puerta de enlace del número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC). Para información, vea <a href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">9-1-1 mejorado (E9-1-1) y servidor de mediación en Lync Server 2013</a>. Para detalles sobre cómo configurar conexiones de tronco, vea <a href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configurar un tronco con omisión de medios en Lync Server 2013</a>.



## En esta sección

  - [Configurar una ruta de voz de E9-1-1 en Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurar la información del sitio para E9-1-1 en Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurar características avanzadas de E9-1-1 en Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

