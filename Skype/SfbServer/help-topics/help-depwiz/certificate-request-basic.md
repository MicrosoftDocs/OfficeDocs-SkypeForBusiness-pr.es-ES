---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La página nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud en bits del par de claves privada y pública, y una casilla que le permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: 66b9506086207fc8803bae9b77d39ee9f12ac43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302944"
---
# <a name="certificate-request-basic"></a>Solicitud de certificado (básica)
 
La página **nombre y configuración de seguridad** proporciona un cuadro de texto para definir un **nombre descriptivo**, una lista desplegable para la **longitud en bits** del par de clave privada y pública, y una casilla que le permite **marcar la clave privada del certificado como **exportable.
  
El nombre descriptivo, o sencillo, de un certificado es un nombre fácilmente reconocible que permite que la persona que lo ve lo identifique más fácilmente.
  
La longitud de bits del par de claves pública y privada se puede seleccionar entre 1024, 2048 o 4096.
  
Activar la casilla para **marcar la clave privada del certificado como** exportable permite que el certificado y la clave privada se exporten y muevan a otro equipo o servidor. La única vez que se necesita activar es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación relé multimedia (MRAS).
  
> [!CAUTION]
> Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la opción marcar la clave privada del certificado como exportable solo si es absolutamente necesario. 
  

