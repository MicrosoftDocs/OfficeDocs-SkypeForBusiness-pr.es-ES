---
title: 'Lync Server 2013: Compatibilidad con protocolo IP y de red'
TOCTitle: Compatibilidad con protocolo IP y de red
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48276379
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con protocolo IP y de red en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 admite los protocolos IP y de red siguientes:

  - **Protocolos IP.**    Lync Server 2013 admite la versión 4 IP (IPv4) o la versión IP 6 (IPv6) para la red del servidor.
    

    > [!NOTE]
    > Lync Server 2013 puede funcionar en una red con una pila de IP dual habilitada.



  - **Protocolos de transporte SIP.**   Por lo general, SIP puede usar al menos tres tipos de transporte: Protocolo de datagramas de usuario (UDP), Protocolo de control de transmisión (TCP) y Protocolo de seguridad de la capa de transporte (TLS). En la configuración predeterminada de transporte SIP, TLS se ejecuta a través de TCP y se utiliza en la red de Lync Server 2013. En la zona perimetral de la red, Lync Server 2013 puede interoperar a través de TCP. Lync Server 2013 no admite UPD para el transporte SIP porque no satisface la normativa mínima para la seguridad, fiabilidad y escalabilidad de las comunicaciones empresariales. Para más información, consulte el artículo en inglés del blog de NextHop "Actualizar o no actualizar, esa es la cuestión" en [http://go.microsoft.com/fwlink/?linkid=185369\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=185369%26clcid=0xc0a).
    

    > [!NOTE]
    > El contenido de los blogs y sus URL están sujetos a cambios sin previo aviso.


