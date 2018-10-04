---
title: Administrar la mensajería unificada de Exchange y el correo de voz hospedado
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Uso de PowerShell para administrar las funciones de mensajería unificada de Exchange, como operador automático y acceso de suscriptor y correo de voz hospedado en Skype para profesionales en línea.
ms.openlocfilehash: d00328ad50bdcfeea326255d1dcd6d22daa9a3a4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372858"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Puede administrar la mensajería unificada de Exchange y hospedada de correo de voz de Skype para profesionales en línea mediante el uso de un conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Administrar la mensajería unificada de Exchange y hospedado de correo de voz

Los cmdlets siguientes pueden usarse para administrar la mensajería unificada de Exchange (MU) y las directivas de correo de voz hospedado:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Crea y administra objetos de contacto que usa para los servicios de operador automático y acceso de suscriptor, cuando la mensajería unificada de Exchange es un servicio hospedado.  <br/><br/> Skype para profesionales Online funciona con mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluido el acceso de suscriptor y operador automático. Operador automático proporciona una manera para llamadas a automáticamente se ha atendido y redirige a la persona correcta. Acceso de suscriptor permite a los usuarios para conectarse a la mensajería unificada de Exchange y recuperar información de calendario, contactos, los mensajes de voz y correo electrónico.  <br/><br/> Cuando la mensajería unificada de Exchange se proporciona como un servicio hospedado, usados para los servicios de acceso de suscriptor y operador automático de los objetos de contacto deben crearse mediante el uso de Microsoft PowerShell. Estos objetos se crean y administran mediante los cmdlets de **CsExUmContact** . <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[GRANT-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Administra las directivas de correo de voz hospedado utilizadas en la organización. Las directivas de correo de voz hospedado especifican las llamadas no respondidas cómo se enrutan al servicio de mensajería unificada de Exchange. Estas directivas afectan a sólo los usuarios que han sido habilitados para mensajería unificada de Exchange hospedado en el correo de voz.  <br/><br/> Para comprobar si un usuario está habilitado para correo de voz hospedado, ejecute un comando similar al siguiente desde el símbolo del sistema de PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 