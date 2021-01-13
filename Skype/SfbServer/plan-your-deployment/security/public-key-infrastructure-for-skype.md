---
title: Infraestructura de clave pública para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype Empresarial Server se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores y entre los distintos roles de servidor. La infraestructura de clave pública (PKI) de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 y Windows Server 2008 proporciona la infraestructura para establecer y validar esta cadena de confianza.
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832150"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infraestructura de clave pública para Skype Empresarial Server
 
Skype Empresarial Server se basa en certificados para la autenticación de servidores y para establecer una cadena de confianza entre clientes y servidores y entre los distintos roles de servidor. La infraestructura de clave pública (PKI) de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 y Windows Server 2008 proporciona la infraestructura para establecer y validar esta cadena de confianza.
  
Los certificados son los ID digitales. Identifican un servidor por nombre y especifican sus propiedades. Para asegurarse de que la información de un certificado es válida, el certificado debe ser emitido por una CA de confianza para los clientes u otros servidores que se conectan al servidor. Si el servidor se conecta solo con otros clientes y servidores de una red privada, la CA puede ser una CA de empresa. Si el servidor interactúa con entidades fuera de la red privada, es posible que se necesite una CA pública.
  
Incluso si la información incluida en el certificado es válida, es preciso comprobar de alguna manera que el servidor que presenta el certificado es realmente el servidor representado por el certificado. Ahí es donde entra en juego la PKI de Windows.
  
Cada certificado está asociado a una clave pública. El servidor indicado en el certificado tiene una clave privada correspondiente que solo él conoce. El cliente o servidor que se conecta usa la clave pública para cifrar un fragmento de información aleatorio y enviarlo al servidor. Si el servidor descifra la información y la devuelve como texto sin formato, la entidad que se conecta puede estar segura de que el servidor tiene la clave privada asociada al certificado y, por consiguiente, es el servidor indicado en el certificado.
  
> [!NOTE]
> No todas las CA públicas cumplen con los requisitos de los certificados de Skype Empresarial Server. Para los certificados públicos, se recomienda consultar la lista de proveedores autorizados de CA públicas. Para obtener más información, consulte [Asociados de certificados de comunicaciones unificadas.](https://go.microsoft.com/fwlink/p/?LinkId=140898) 
  
## <a name="crl-distribution-points"></a>Puntos de distribución CRL

Skype Empresarial Server requiere que todos los certificados de servidor contengan uno o más puntos de distribución de lista de revocación de certificados (CRL). Los puntos de distribución CRL son ubicaciones desde las que se pueden descargar listas de revocación de certificados para comprobar si un certificado no ha sido revocado después de su emisión. Un punto de distribución CRL se anota en las propiedades del certificado como una dirección URL y suele ser HTTPS.
  
## <a name="enhanced-key-usage"></a>Uso mejorado de clave

Skype Empresarial Server requiere que todos los certificados de servidor admitan el uso mejorado de claves (EKU) para la autenticación del servidor. La configuración del campo EKU para la autenticación de los servidores significa que el certificado es válido para la autenticación de los servidores. Este EKU es esencial para MTLS. Puede haber varias entradas en el EKU; de este modo, se habilita el certificado para varios propósitos.
  

