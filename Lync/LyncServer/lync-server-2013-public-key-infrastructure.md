---
title: 'Lync Server 2013: infraestructura de clave pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec711ad773aeb1b3b426e929b2d87d033f8d8004
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infraestructura de clave pública para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-13_

Microsoft Lync Server 2013 se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y la infraestructura de clave pública (PKI) de Windows Server 2003 proporcionan la infraestructura para establecer y validar esta cadena de confianza.

Los certificados son identificadores digitales. Identifican un servidor por su nombre y especifican sus propiedades. Para asegurarse de que la información de un certificado es válida, el certificado debe ser emitido por una entidad de certificación en la que confían los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta sólo con otros clientes y servidores de una red privada, la entidad de certificación puede ser una entidad de certificación empresarial. Si el servidor interactúa con entidades fuera de la red privada, es posible que se requiera una entidad de certificación pública.

Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.

Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.

<div>


> [!NOTE]  
> No todas las entidades de certificación públicas cumplen con los requisitos de los certificados 2013 de Lync Server. Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas. Para obtener más información, vea asociados de certificados <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>de comunicaciones unificadas en.



</div>

<div>

## <a name="crl-distribution-points"></a>Puntos de distribución CRL

Lync Server 2013 requiere que todos los certificados de servidor contengan uno o más puntos de distribución de listas de revocación de certificados (CRL). Los puntos de distribución CRL son ubicaciones desde las que se pueden descargar listas de revocación de certificados para comprobar si un certificado no ha sido revocado después de su emisión. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.

</div>

<div>

## <a name="enhanced-key-usage"></a>Uso mejorado de clave

Lync Server 2013 requiere que todos los certificados de servidor sean compatibles con el uso mejorado de clave (EKU) para fines de autenticación de servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.

<div>


> [!NOTE]  
> El EKU para la autenticación de clientes se requería para las conexiones MTLS salientes de Live Communications Server 2003 y Live Communications Server 2005, pero ya no se requiere. Sin embargo, este EKU debe estar presente en los servidores perimetrales que se conectan a AOL a través de la conectividad de mensajería instantánea pública.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

