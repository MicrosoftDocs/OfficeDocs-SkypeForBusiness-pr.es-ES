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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use PowerShell para administrar capacidades de mensajería unificada de Exchange, como el Operador automático de suscriptores y el correo de voz hospedado en Skype Empresarial Online.
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692685"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Puede administrar la mensajería unificada de Exchange y el correo de voz hospedado en Skype Empresarial Online mediante un conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Los siguientes cmdlets se pueden usar para administrar la mensajería unificada de Exchange (UM) y las directivas de correo de voz hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Crea y administra los objetos de contacto que se usan para los Operador automático de acceso de suscriptor y de mensajería unificada de Exchange, cuando este se encuentra en un servicio hospedado.  <br/><br/> Skype Empresarial Online funciona con la mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluidos el Operador automático y el acceso de suscriptores. Operador automático proporciona una manera de que las llamadas se conteste automáticamente y se enrute a la persona correcta. El acceso de suscriptor permite a los usuarios conectarse a la mensajería unificada de Exchange y recuperar correo electrónico, mensajes de voz, contactos e información del calendario.  <br/><br/> Cuando la mensajería unificada de Exchange se proporciona como servicio hospedado, los objetos de contacto usados para los servicios de Operador automático y De Acceso de suscriptor deben crearse con Microsoft PowerShell. Estos objetos se crean y administran mediante los **cmdlets CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Administra las directivas de correo de voz hospedadas que se usan en la organización. Las directivas de correo de voz hospedado especifican cómo se enrutar las llamadas no a respuestas al servicio de MU de Exchange. Estas directivas afectan solo a los usuarios habilitados para el correo de voz hospedado de MU de Exchange.  <br/><br/> Para comprobar si un usuario está habilitado para el correo de voz hospedado, ejecute un comando similar al siguiente desde el símbolo del sistema de PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
