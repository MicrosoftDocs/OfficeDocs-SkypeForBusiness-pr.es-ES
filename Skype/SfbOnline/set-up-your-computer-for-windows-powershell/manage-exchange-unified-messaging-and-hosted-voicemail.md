---
title: Administrar la mensajería unificada de Exchange y el correo de voz hospedado
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell para administrar las capacidades de mensajería unificada de Exchange, como el acceso de operador automático y el buzón de voz hospedado en Skype empresarial online.
ms.openlocfilehash: 4bc953307059a1679ad435b3674befe824e34056
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284704"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Puede administrar la mensajería unificada de Exchange y el buzón de voz hospedado en Skype empresarial online mediante un conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Los siguientes cmdlets se pueden usar para administrar la mensajería unificada de Exchange y las directivas de buzón de voz hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Crea y administra objetos de contacto que se usan para los servicios de acceso automático de operadores y suscriptores cuando la mensajería unificada de Exchange es un servicio hospedado.  <br/><br/> Skype empresarial online funciona con la mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluido el acceso de operador automático y de suscriptor. El operador automático permite que las llamadas se respondan automáticamente y se enruten a la persona correcta. El acceso de suscriptor permite a los usuarios conectarse a la mensajería unificada de Exchange y recuperar el correo electrónico, los mensajes de voz, los contactos y la información del calendario.  <br/><br/> Cuando se proporciona una mensajería unificada de Exchange como servicio hospedado, los objetos de contacto usados para el operador automático y los servicios de acceso al suscriptor deben crearse con Microsoft PowerShell. Estos objetos se crean y administran mediante los cmdlets de **CsExUmContact** . <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Administra las directivas de buzón de voz hospedadas que se usan en la organización. Las directivas de buzón de voz hospedadas especifican cómo se enrutan las llamadas no contestadas al servicio MU de Exchange. Estas directivas solo afectan a los usuarios que se han habilitado para el buzón de voz hospedado de mensajería unificada de Exchange.  <br/><br/> Para comprobar si un usuario está habilitado para el buzón de voz hospedado, ejecute un comando similar al siguiente en el símbolo del sistema de PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
