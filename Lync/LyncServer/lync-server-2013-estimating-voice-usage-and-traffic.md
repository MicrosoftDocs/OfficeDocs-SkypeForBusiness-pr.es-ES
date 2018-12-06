---
title: 'Lync Server 2013: Estimar el uso de voz y el tráfico'
TOCTitle: Estimar el uso de voz y el tráfico
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48275452
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Estimar el uso de voz y el tráfico para Lync Server 2013

 

_**Última modificación del tema:** 2012-08-07_

Microsoft Lync Server 2013, herramienta de planeación usa la siguiente métrica para calcular el tráfico de usuarios de cada sitio y el número de puertos necesarios para admitir dicho tráfico.

  - Para **Tráfico reducido** (una llamada de RTC por usuario y hora) calcula 15 usuarios por puerto.

  - Para **Tráfico medio** (dos llamadas de RTC por usuario y hora) calcula 10 usuarios por puerto.

  - Para **Tráfico denso** (tres llamadas o más de RTC por usuario y hora) calcula 5 usuarios por puerto.

El número de puertos sucesivos determina el número de Servidores de mediación y puertas de enlace que serán necesarios. El tamaño de las puertas de enlace RTC que la mayoría de las organizaciones considerarán implementar varía entre 2 y 960 puertos (hay puertas de enlace incluso más grandes, pero se destinan principalmente a los proveedores de servicios de telefonía).

Por ejemplo, una organización con 10 000 usuarios y un tráfico medio necesitará 1000 puertos. El número de puertas de enlace requeridas equivaldría al número total de puertos requeridos determinado por la capacidad total de las puertas de enlace.

