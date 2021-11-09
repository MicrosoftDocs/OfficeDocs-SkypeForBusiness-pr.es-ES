---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La página Nombre y seguridad Configuración proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud de bits del par de claves públicas y privadas y una casilla que permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: da3125456a97408dd9f3e694a16238d5657fc1d6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861757"
---
# <a name="certificate-request-basic"></a>Solicitud de certificado (básica)
 
La página Nombre y seguridad **Configuración** proporciona un cuadro de texto para definir  un nombre **descriptivo,** una lista desplegable para la longitud de bits del par de claves privadas y públicas y una casilla que permite marcar la clave privada del certificado como **exportable**.
  
El nombre descriptivo o simple de un certificado es un nombre fácilmente reconocible que facilita la identificación de la persona que ve el certificado.
  
La longitud de bits del par de claves pública y privada se puede seleccionar como 1024, 2048 o 4096.
  
Si se selecciona la casilla marcar la clave privada del certificado como **exportable,** el certificado y la clave privada se exportan y se mueven a otro equipo o servidor. La única vez que esto es necesario es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación de retransmisión multimedia (MRAS).
  
> [!CAUTION]
> Para ayudar a mantener la seguridad del certificado y del par de claves, debe seleccionar la opción Marcar la clave privada del certificado como exportable solo si es absolutamente necesario. 
  

