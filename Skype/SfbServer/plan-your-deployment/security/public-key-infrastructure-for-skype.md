---
title: Infraestructura de clave pública para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype empresarial Server se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 y la infraestructura de clave pública (PKI) de Windows Server 2008 proporcionan la infraestructura para establecer y validar esta cadena de confianza.
ms.openlocfilehash: ec2ae6e94d9cf00a6193c45d6cefd7db6d5a5b62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815638"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infraestructura de clave pública para Skype empresarial Server
 
Skype empresarial Server se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores, así como entre los diferentes roles de servidor. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 y la infraestructura de clave pública (PKI) de Windows Server 2008 proporcionan la infraestructura para establecer y validar esta cadena de confianza.
  
Los certificados son identificadores digitales. Identifican un servidor por nombre y especifican sus propiedades. Para garantizar la validez de la información incluida en un certificado, este debe proceder de una entidad de certificación (CA) que sea de confianza para los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta únicamente a otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades ubicadas fuera de la red privada, es posible que se requiera una CA pública.
  
Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.
  
Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.
  
> [!NOTE]
> No todas las entidades emisoras públicas cumplen con los requisitos de los certificados de Skype empresarial Server. Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas. Para obtener más información, consulte [socios de certificados de comunicaciones unificadas](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Puntos de distribución CRL

Skype empresarial Server requiere que todos los certificados de servidor contengan uno o varios puntos de distribución de la lista de revocación de certificados (CRL). Los puntos de distribución CRL (CDP) son ubicaciones desde las que se pueden descargar CRL para comprobar si un certificado no ha sido revocado después de su emisión y todavía se encuentra dentro del período de validez. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.
  
## <a name="enhanced-key-usage"></a>Uso mejorado de clave

Skype empresarial Server requiere que todos los certificados de servidor admitan el uso mejorado de claves (EKU) para fines de autenticación de servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.
  

