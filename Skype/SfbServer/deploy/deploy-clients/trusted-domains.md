---
title: Dominios de confianza del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834120"
---
# <a name="skype-room-system-trusted-domains"></a>Dominios de confianza del Sistema de sala de Skype
 
Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.
  
## <a name="trusted-domains"></a>Dominios de confianza

El cliente de Skype Empresarial muestra un cuadro de diálogo que permite a los usuarios aceptar el certificado de Skype Empresarial Server si el dominio SIP de la cuenta de usuario que inicia sesión es diferente del nombre que aparece en el asunto o el nombre alternativo del sujeto en el certificado. Si el certificado configurado para Skype Empresarial Server en su organización no tiene el nombre de dominio SIP de la cuenta del Sistema de sala de Skype en el asunto o el nombre alternativo del sujeto, debe configurar los dominios presentados en el certificado en la clave del Registro de dominios de confianza en el equipo de consola del Sistema de sala de Skype. La Guía del administrador del sistema de sala de Skype proporcionada por el fabricante del Sistema de sala de Skype explica cómo y dónde agregar dominios de confianza en el cliente de Skype Empresarial. 
  
Por ejemplo, supongamos que los certificados configurados en Skype Empresarial Server tienen el nombre alternativo asunto/asunto "CONTOSO. LOCAL" y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión del Sistema de sala de Skype es "confrm1@contoso.net". Como contoso.net no está en el certificado, en el equipo del Sistema de sala de Skype, tendrá que configurar "contoso.local" como un dominio de confianza en el Registro, como se explica en la Guía del administrador del sistema de sala de Skype proporcionada por el fabricante del Sistema de sala de Skype. 
  

