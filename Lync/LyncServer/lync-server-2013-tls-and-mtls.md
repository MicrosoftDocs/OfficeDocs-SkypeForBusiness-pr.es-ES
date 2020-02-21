---
title: 'Lync Server 2013: TLS y MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c3d9dbaeb4c630445b832ab8f220c209461837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS y MTLS para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-07_

Los protocolos de seguridad de la capa de transporte (TLS) y seguridad de la capa de transporte mutua (MTLS) proporcionan comunicaciones cifradas y autenticación de extremo en Internet. Microsoft Lync Server 2013 usa estos dos protocolos para crear la red de servidores de confianza y garantizar que todas las comunicaciones a través de esa red están cifradas. Todas las comunicaciones SIP entre servidores se producen a través de MTLS. Las comunicaciones SIP del cliente al servidor se producen a través de TLS.

TLS permite a los usuarios, mediante su software cliente, autenticar los servidores de Lync Server 2013 a los que se conectan. En una conexión TLS, el cliente solicita un certificado válido del servidor. Para que sea válido, el certificado debe haber sido emitido por una entidad de certificación que también sea de confianza para el cliente y el nombre DNS del servidor debe coincidir con el nombre DNS del certificado. Si el certificado es válido, el cliente usa la clave pública del certificado para cifrar las claves de cifrado simétricas que se van a usar para la comunicación, por lo que solo el propietario original del certificado puede usar su clave privada para descifrar el contenido de la comunicación. La conexión resultante es de confianza y desde ese punto no es cuestionada por otros servidores o clientes de confianza. Dentro de este contexto, la capa de sockets seguros (SSL), tal como se usa con los servicios Web, se puede asociar como basada en TLS.

Las conexiones de servidor a servidor se basan en MTLS para la autenticación mutua. En una conexión MTLS, el servidor que originó un mensaje y el servidor que los recibe intercambian certificados de una entidad de certificación de confianza mutua. Los certificados demuestran la identidad de cada servidor en el otro. En las implementaciones de Lync Server 2013, los certificados emitidos por la CA de empresa que están durante el período de validez y no revocados por la CA emisora se consideran automáticamente válidos para todos los clientes y servidores internos, ya que todos los miembros de un dominio de Active Directory Confíe en la entidad de certificación empresarial de ese dominio. En los escenarios federados, los dos socios federados deben confiar en la entidad emisora de certificados. Cada socio puede usar una entidad de certificación diferente, si lo desea, siempre que el otro asociado también confíe en esa CA. Esta confianza es más sencilla para los servidores perimetrales que tienen el certificado de CA raíz del asociado en sus entidades de certificación raíz de confianza o mediante el uso de una entidad de certificación de terceros en la que confían ambas partes.

TLS y MTLS ayudan a evitar el espionaje y los ataques de intermediario. En un ataque de tipo "Man in the Middle", el atacante redirige las comunicaciones entre dos entidades de red a través del equipo del atacante sin el conocimiento de ninguna de las partes. TLS y Lync Server 2013 especificación de servidores de confianza (sólo los especificados en el generador de topologías) mitiga el riesgo de un ataque de intermediario parcialmente en el nivel de aplicación mediante el cifrado de un extremo a otro coordinado mediante la criptografía de clave pública entre los dos puntos de conexión, y un atacante tendría que tener un certificado válido y de confianza con la clave privada correspondiente y que se haya emitido para el nombre del servicio al que el cliente se comunica para descifrar la comunicación. Sin embargo, en última instancia, debe seguir los procedimientos de seguridad de la infraestructura de red (en este caso, el DNS corporativo). Lync Server 2013 presupone que el servidor DNS es de confianza de la misma manera que los controladores de dominio y los catálogos globales son de confianza, pero DNS proporciona un nivel de protección contra ataques de secuestro de DNS al impedir que el servidor del atacante responda correctamente a un solicitud al nombre falso.

En la figura siguiente se muestra a alto nivel cómo Lync Server 2013 usa MTLS para crear una red de servidores de confianza.

**Conexiones de confianza en una red de Lync Server**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

