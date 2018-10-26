---
title: Planear la detección automática en Lync Server 2013
TOCTitle: Planear la detección automática en Lync Server 2013
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945628(v=OCS.15)
ms:contentKeyID: 52061638
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear la detección automática en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-16_

La Detección automática se incorporó en Lync Server en la actualización acumulativa de Lync Server 2010 de noviembre de 2011. El objetivo principal de esta implementación inicial de la Detección automática era proporcionar a Lync Mobile un medio para encontrar el servicio de movilidad (Mcx). El servicio Detección automática de Lync Server 2013 ahora es un servicio que usan todos los clientes para encontrar servicios de usuario y de servidor. El servicio Detección automática de Microsoft Lync Server 2013 se ejecuta en Directores y en Servidores front-end.

> [!TIP]  
> Para obtener información más técnica sobre la Detección automática y lo que se comunica a los clientes, consulte <a href="lync-server-2013-understanding-autodiscover.md">Comprender la detección automática</a>.<br />
> La movilidad sigue siendo un escenario único y los servicios de movilidad aún requieren cierta planeación especial. Para obtener detalles, consulte <a href="lync-server-2013-planning-for-mobility.md">Planeación de movilidad en Lync Server 2013</a>.


Cuando se presentó la Detección automática en Lync Server 2010, fue necesario realizar ciertos compromisos a fin de implementar un servicio que requería posibles cambios de certificados en las implementaciones de servidor existentes. La Detección automática se podía usar sobre el puerto TCP 443 para HTTPS y sobre el puerto TCP 80 para HTTP. Si se decidía usar HTTPS, se debían volver a emitir los certificados de los servidores proxy inversos, los Directores y los Servidores front-end para dar cabida a los registros DNS `lyncdiscover.<dominio>` y `lyncdiscoverinternal.<dominio>` necesarios. Si se decidía usar HTTP, era posible evitar la reemisión de certificados mediante el uso de registros CNAME (o alias) de DNS a fin de usar los nombres existentes en los certificados. Si se usaba HTTP, las comunicaciones iniciales no se cifraban.

Puesto que Lync Server 2013 usa la Detección automática para todos los clientes, el escenario principal es usar exclusivamente HTTPS y crear certificados con lyncdiscover.\<dominio\> como parte de la configuración de los servidores proxy inversos, los Directores y los Servidores front-end. Si implementa la Detección automática en una implementación actualizada desde Lync Server 2010, le resultará conveniente usar HTTP para evitar la tarea de volver a emitir los certificados. En las siguientes secciones, se proporciona información sobre ambos escenarios.

> [!IMPORTANT]  
> La lista de nombres alternativos del sujeto de los certificados usados por la regla de publicación de servicios web externos debe contener una entrada <em>lyncdiscover.&lt;dominiosip&gt;</em> para cada dominio SIP de su organización. Para obtener detalles acerca de las entradas de nombres alternativos del sujeto necesarias para los servidores proxy inversos, directores y front-end, consulte <a href="lync-server-2013-certificate-summary-autodiscover.md">Resumen del certificado: detección automática</a>.



## En esta sección

  - [Resumen del certificado: detección automática](lync-server-2013-certificate-summary-autodiscover.md)

  - [Resumen del puerto: detección automática en Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Resumen de DNS: detección automática en Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Implementación híbrida y dominio dividido: detección automática](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

