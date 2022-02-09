---
title: Skype de confianza del sistema de sala
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.
ms.openlocfilehash: f3ea0557c22214addd0f7cc4d935af919a131ae1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399934"
---
# <a name="skype-room-system-trusted-domains"></a>Skype de confianza del sistema de sala
 
Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.
  
## <a name="trusted-domains"></a>Dominios de confianza

El cliente de Skype Empresarial muestra un cuadro de diálogo que permite a los usuarios aceptar el certificado del Skype Empresarial Server si el dominio SIP de la cuenta de usuario que inicia sesión es diferente del nombre que se muestra en el asunto o el nombre alternativo del sujeto en el certificado. Si el certificado configurado para Skype Empresarial Server en su organización no tiene el nombre de dominio SIP de una cuenta del sistema de sala de Skype en Subject o Subject Alt Name, debe configurar los dominios presentados en el certificado bajo la clave del Registro dominios de confianza en el equipo de consola del sistema de sala de Skype. La Skype de administradores del sistema de sala Skype de sala proporcionada por el fabricante explica cómo y dónde agregar dominios de confianza en el Skype Empresarial cliente. 
  
Por ejemplo, supongamos que los certificados configurados en Skype Empresarial Server tienen un nombre alt subject/subject de "CONTOSO. LOCAL" y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión Skype room system es "confrm1@contoso.net". Dado que contoso.net no está en el certificado, en el equipo del sistema de sala de Skype, deberá configurar "contoso.local" como dominio de confianza en el Registro, como se explica en la Guía del administrador del sistema de sala Skype proporcionada por el fabricante del sistema de sala de Skype. 
  

