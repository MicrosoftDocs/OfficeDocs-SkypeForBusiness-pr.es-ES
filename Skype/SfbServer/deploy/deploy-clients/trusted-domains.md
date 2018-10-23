---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: bc025849f56a7257ac3684b9783e551959bd0228
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699689"
---
# <a name="skype-room-system-trusted-domains"></a>Dominios de confianza del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
  
## <a name="trusted-domains"></a>Dominios de confianza

El Skype para cliente empresarial muestra un cuadro de diálogo que permite a los usuarios que acepte el certificado desde el Skype para Business Server si el dominio SIP de la cuenta de usuario de inicio de sesión es diferente del nombre que se presentan en el asunto o el nombre alternativo de sujeto en el certificado. Si el certificado configurado para Skype para Business Server en la organización no tiene el nombre de dominio SIP de la cuenta del sistema de salas de Skype en el asunto o el nombre alternativo de sujeto, debe configurar los dominios que aparecen en el certificado en los dominios de confianza clave del registro en el equipo de la consola del sistema de salas de Skype. Sistema de sala de Skype suministrados por el fabricante Skype salón del administrador del sistema esta guía se explica cómo y dónde para agregar dominios de confianza en el Skype para clientes empresariales. 
  
Por ejemplo, supongamos que los certificados configurados en Skype para Business Server tienen un nombre de sujeto o sujeto alternativo de "CONTOSO. "LOCAL" y uno de los dominios SIP que se asigna a un usuario de la dirección de inicio de sesión del sistema de salas de Skype es "confrm1@contoso.net". Debido a que contoso.net es no en el certificado, en el equipo del sistema de salas de Skype, debe configurar "contoso.local" como un dominio de confianza en el registro, como se explica en la Guía de Skype salón suministrados por el fabricante Skype salón del sistema del administrador del sistema. 
  

