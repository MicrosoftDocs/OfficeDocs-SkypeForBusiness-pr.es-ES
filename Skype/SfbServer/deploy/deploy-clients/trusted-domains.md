---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: eacc468508ba9107534ce4ac729edf0d0d6c895d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287873"
---
# <a name="skype-room-system-trusted-domains"></a>Dominios de confianza del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
  
## <a name="trusted-domains"></a>Dominios de confianza

El cliente de Skype empresarial muestra un cuadro de diálogo que permite a los usuarios aceptar el certificado de Skype empresarial Server si el dominio SIP de la cuenta de usuario que inicia sesión es diferente del nombre presentado en el asunto o nombre alternativo del asunto en el certificado. Si el certificado configurado para Skype empresarial Server en su organización no tiene el nombre de dominio SIP de la cuenta del sistema de salas de Skype en el nombre alternativo asunto o asunto, debe configurar los dominios presentados en el certificado en los dominios de confianza. clave del registro en la máquina de consola del sistema de salas de Skype. La guía del administrador de sistemas de salas de Skype proporcionada por el fabricante de su sistema de salas de Skype explica cómo y dónde agregar dominios de confianza en el cliente de Skype empresarial. 
  
Por ejemplo, supongamos que los certificados configurados en Skype empresarial Server tienen un nombre alternativo de asunto y asunto de "CONTOSO. LOCAL "y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión del sistema de salas de Skype es" confrm1@contoso.net ". Debido a que contoso.net no está en el certificado, en el equipo del sistema de la sala de Skype, necesitará configurar "contoso. local" como dominio de confianza en el registro, como se explica en la guía del administrador de sistemas de Skype Room. 
  

