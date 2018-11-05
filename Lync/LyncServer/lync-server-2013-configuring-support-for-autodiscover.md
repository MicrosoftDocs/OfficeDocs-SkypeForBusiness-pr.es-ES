---
title: Configurar la compatibilidad con la detección automática
TOCTitle: Configurar la compatibilidad con la detección automática
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945622(v=OCS.15)
ms:contentKeyID: 52061626
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la compatibilidad con la detección automática

 

_**Última modificación del tema:** 2016-12-08_

El **servicio Detección automática** de los servicios web de Lync Server apareció por primera vez en la actualización acumulativa de Lync Server 2010 de noviembre de 2011. En esta actualización, también se lanzó la versión inicial de los clientes de Lync Mobile. El servicio Detección automática presentó los servicios de movilidad, también llamados "servicio Mcx".

El servicio Detección automática constituye una única ubicación para que todos los clientes puedan solicitar información sobre los servicios y las características que se encuentran disponibles y acerca de cómo ponerse en contacto con los servicios, ya sea mediante un nombre de dominio completo o una referencia web de Localizador uniforme de recursos. La Detección automática proporciona una gran cantidad de características y cada cliente puede realizar solicitudes en función de las características que puede usar. Por ejemplo, un cliente de Lync 2013 de escritorio usará la Detección automática para determinar los servicios web externos, pero no usará los servicios de movilidad (Mcx). Para definir correctamente las características que estarán disponibles para los clientes y para habilitar su uso, deben definirse los escenarios que permiten a los clientes encontrar y usar las entradas de Detección automática de forma eficaz. Para usar la Detección automática, la implementación requiere que un proxy inverso publique los servicios web de Lync Server, que los registros DNS se configuren para resolver las consultas DNS del servicio Detección automática de Lync Server y de los servicios web de Lync Server, y que se configuren correctamente los servicios de certificado para los distintos escenarios.

> [!TIP]  
> Para obtener información técnica detallada sobre la función de los elementos de la respuesta o solicitud de Detección automática, consulte <a href="lync-server-2013-understanding-autodiscover.md">Comprender la detección automática</a>.



La información y las tablas siguientes definen las configuraciones (en caso de que sean necesarias) que debe implementar para proporcionar un uso completo y eficaz del servicio Detección automática en cada escenario específico. La información de los siguientes temas es específica de Microsoft Lync Server 2013. Si busca información sobre cómo planear la movilidad para Lync Server 2010, consulte <http://go.microsoft.com/fwlink/?linkid=275113>. Para implementar la movilidad para Lync Server 2010, consulte <http://go.microsoft.com/fwlink/?linkid=275114>

## En esta sección

  - [Configurar DNS para la detección automática](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configurar certificados para la detección automática](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configurar un proxy inverso para la detección automática](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configurar la detección automática para implementaciones híbridas](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

