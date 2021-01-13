---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La página Nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud de bits del par de claves pública y privada, y una casilla que permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830420"
---
# <a name="certificate-request-basic"></a>Solicitud de certificado (básica)
 
La  página Nombre y configuración de seguridad proporciona un cuadro de texto  para definir un nombre **descriptivo,** una lista desplegable para la longitud de bits del par de claves pública y privada, y una casilla que permite marcar la clave privada del certificado como **exportable.**
  
El nombre descriptivo o simple de un certificado es un nombre fácilmente reconocible que facilita a la persona que ve el certificado identificarlo.
  
La longitud de bits del par de claves pública y privada se puede seleccionar como 1024, 2048 o 4096.
  
Si se selecciona la casilla para marcar la clave privada del certificado como **exportable,** el certificado y la clave privada se pueden exportar y mover a otro equipo o servidor. La única vez que esto es necesario es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación de retransmisión multimedia (MRAS).
  
> [!CAUTION]
> Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la opción Marcar la clave privada del certificado como exportable solo si es absolutamente necesario. 
  

