---
title: 'Lync Server 2013: TLS y MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS y MTLS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los protocolos de Seguridad de la capa de transporte (TLS) y Seguridad de la capa de transporte mutua (MTLS) ofrecen comunicaciones cifradas y autenticación de extremos en Internet. Microsoft Lync Server 2013 usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red están cifradas. Todas las comunicaciones SIP entre los servidores se llevan a cabo a través de MTLS. Las comunicaciones SIP entre el cliente y el servidor se realizan a través de TLS.

TLS permite a los usuarios, mediante el software cliente, autenticar los servidores de Lync Server 2013 a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe haber sido emitido por una CA que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se utilizarán para la comunicación, de modo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es fiable y desde ese punto no es desafiada por otros servidores o clientes fiables. En este contexto, SSL, tal como se usa con los servicios web, se puede asociar como basada en TLS.

Las conexiones entre servidores dependen de MTLS para la autenticación mutua. En una conexión MTLS, el servidor de origen de un mensaje y el que lo recibe intercambian certificados procedentes de una CA de confianza para ambos. Los certificados permiten a los servidores demostrarse mutuamente sus identidades. En implementaciones de Lync Server 2013, los certificados emitidos por la CA de empresa que se encuentren durante el período de validez y que no hayan sido revocados por la entidad emisora de certificados son considerados automáticamente por todos los clientes y servidores internos, ya que todos los miembros de un dominio de Active Directory confiar en la entidad emisora de certificados de empresa en ese dominio. En los escenarios de federación, ambos socios federados deben confiar en la CA que emite los certificados. Si así lo desea, cada socio puede utilizar una CA diferente, siempre y cuando el otro socio también confíe en esa CA. La manera más fácil de lograr esa confianza es configurar los servidores perimetrales para que el certificado de la CA raíz del socio figure entre sus CA raíz de confianza, o bien usar una CA de otro fabricante en la que confíen ambas partes.

TLS y MTLS ayudan a evitar los ataques de interceptación y de tipo "Man in the middle". En los ataques de tipo "Man in the middle", el atacante enruta las comunicaciones entre dos entidades de red a través del equipo del atacante sin que lo sepa ninguna de esas entidades. TLS y la especificación 2013 de Lync Server de servidores de confianza (solo las especificadas en el generador de topologías) reducen el riesgo de un ataque de intermediario parcialmente en el nivel de aplicación mediante el cifrado de extremo a extremo coordinado con el cifrado de clave pública entre los dos puntos de conexión, un atacante tendría que tener un certificado válido y confiable con la clave privada correspondiente y se emitió para el nombre del servicio al que se comunica el cliente para descifrar la comunicación. En todo caso, usted deberá seguir buenas prácticas de seguridad en su infraestructura de red (en este caso, DNS empresarial). Lync Server 2013 supone que el servidor DNS es de confianza de la misma forma en que se confía en los controladores de dominio y los catálogos globales, pero DNS ofrece un nivel de protección contra ataques de usurpación de DNS evitando que el servidor de un atacante responda correctamente a un solicitud para el nombre falso.

En la siguiente ilustración se muestra en un nivel superior cómo Lync Server 2013 usa MTLS para crear una red de servidores de confianza.

**Conexiones de confianza en una red de Lync Server**

![437749da-c372-4f0d-AC72-ccfd5191696b] (images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-AC72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

