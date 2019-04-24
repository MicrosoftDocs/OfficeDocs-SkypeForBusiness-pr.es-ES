---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La página nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud en bits del par de claves público y privado y una casilla de verificación que le permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: abc022cd9126b90fb83244657dfb32ac214a62c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216399"
---
# <a name="certificate-request-basic"></a>Solicitud de certificado (básica)
 
La página **nombre y configuración de seguridad** proporciona un cuadro de texto para definir un **Nombre descriptivo**, una lista desplegable para la **longitud en bits** del par de claves público y privado y una casilla de verificación que permite a la clave privada **marca el certificado como exportable**.
  
El nombre descriptivo, o sencillo, de un certificado es un nombre fácilmente reconocible que permite que la persona que lo ve lo identifique más fácilmente.
  
La longitud de bits del par de claves pública y privada se puede seleccionar entre 1024, 2048 o 4096.
  
Seleccionar la casilla de verificación para **marcar la clave privada del certificado como exportable** permite que el certificado y la clave privada se exportan y se muevan a otro servidor o equipo. La única vez que se necesita activar es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación relé multimedia (MRAS).
  
> [!CAUTION]
> Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la marca de la clave privada del certificado como exportable opción sólo si es absolutamente necesario. 
  

