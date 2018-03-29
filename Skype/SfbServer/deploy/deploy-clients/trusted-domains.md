---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a>Dominios de confianza del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
  
## <a name="trusted-domains"></a>Dominios de confianza

El Skype para empresa cliente muestra un cuadro de diálogo que permite a los usuarios que acepte el certificado desde el Skype para Business Server si el dominio SIP de iniciar sesión en la cuenta de usuario es diferente del nombre que se presenta en el asunto o el nombre de Alt de asunto en el certificado. Si el certificado configurado para Skype para Business Server de su organización no tiene nombre de dominio SIP de la cuenta de sistema del sitio de Skype en el asunto o el nombre de asunto Alt, debe configurar esos dominios presentados en el certificado en los dominios de confianza clave del registro en el equipo de la consola de sistema de sala de Skype. Guía de sistema de sala de Skype suministrados por el fabricante Skype sala del administrador del sistema se explica dónde y cómo agregar dominios de confianza en el Skype para cliente de empresa. 
  
Por ejemplo, supongamos que los certificados configurados en Skype para Business Server tienen un nombre de sujeto o Alt de "CONTOSO. "LOCAL" y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión de sistema de sala de Skype es "confrm1@contoso.net". Porque contoso.net no aparece en el certificado en el equipo de sistema del sitio de Skype, debe configurar "contoso.local" como un dominio de confianza en el registro, como se explica en la Guía de sistema de sala de Skype suministrados por el fabricante Skype sala del administrador del sistema. 
  

