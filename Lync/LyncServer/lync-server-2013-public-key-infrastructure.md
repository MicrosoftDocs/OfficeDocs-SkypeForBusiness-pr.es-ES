---
title: Infraestructura de clave pública de Lync Server 2013
TOCTitle: Infraestructura de clave pública de Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59679370
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Infraestructura de clave pública de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 usa certificados para autenticar los servidores y establecer una cadena de confianza entre clientes y servidores y entre los diversos roles de servidor. La infraestructura de clave pública (PKI) de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003 proporciona la infraestructura para establecer y validar esta cadena de confianza.

Los certificados son identificadores digitales. Identifican un servidor por nombre y especifican sus propiedades. Para garantizar la validez de la información incluida en un certificado, este debe proceder de una entidad de certificación (CA) que sea de confianza para los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta únicamente a otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades ubicadas fuera de la red privada, es posible que se requiera una CA pública.

Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.

Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.


> [!NOTE]
> No todas las CA públicas cumplen con los requisitos de certificados de Lync Server 2013. Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas. Para obtener información detallada, vea Entidades de certificación de comunicaciones unificadas en <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.



## Puntos de distribución CRL

Lync Server 2013 requiere que todos los certificados de servidor cuenten con uno o más puntos de distribución de listas de revocación de certificados (CRL). Los puntos de distribución CRL son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.

## Uso mejorado de clave

Lync Server 2013 requiere que todos los certificados de servidor admitan el uso mejorado de clave (EKU) para la autenticación de los servidores. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.


> [!NOTE]
> El EKU para la autenticación de clientes se requería para las conexiones MTLS salientes de Live Communications Server 2003 y Live Communications Server 2005, pero ya no se requiere. Sin embargo, este EKU debe estar presente en los servidores perimetrales que se conectan a AOL a través de la conectividad de mensajería instantánea pública.


