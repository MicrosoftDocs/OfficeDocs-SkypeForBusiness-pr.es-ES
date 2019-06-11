---
title: 'Lync Server 2013: infraestructura de clave pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infraestructura de clave pública para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-13_

Microsoft Lync Server 2013 se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003 infraestructura de clave pública (PKI) proporciona la infraestructura para establecer y validar esta cadena de confianza.

Los certificados son identificadores digitales. Identifican un servidor por nombre y especifican sus propiedades. Para garantizar la validez de la información incluida en un certificado, este debe proceder de una entidad de certificación (CA) que sea de confianza para los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta únicamente a otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades ubicadas fuera de la red privada, es posible que se requiera una CA pública.

Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.

Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.

<div>


> [!NOTE]  
> No todas las entidades emisoras públicas cumplen con los requisitos de los certificados de 2013 de Lync Server. Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas. Para obtener más información, vea socios de certificados <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>de comunicaciones unificadas en.



</div>

<div>

## <a name="crl-distribution-points"></a>Puntos de distribución CRL

Lync Server 2013 requiere que todos los certificados de servidor contengan uno o varios puntos de distribución de la lista de revocación de certificados (CRL). Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.

</div>

<div>

## <a name="enhanced-key-usage"></a>Uso mejorado de clave

Lync Server 2013 requiere que todos los certificados de servidor admitan el uso mejorado de claves (EKU) para la autenticación del servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.

<div>


> [!NOTE]  
> El EKU de autenticación de cliente es necesario para las conexiones MTLS de salida de Live Communications Server 2003 y Live Communications Server 2005, pero ya no es necesario. Sin embargo, este EKU debe estar presente en los servidores perimetrales que se conectan a AOL por medio de la conectividad de mensajería instantánea pública.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

