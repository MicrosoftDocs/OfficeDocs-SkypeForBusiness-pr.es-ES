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
description: Use PowerShell para administrar las capacidades de mensajería unificada de Exchange, como el acceso Operador automático suscriptores y el correo de voz hospedado en Skype Empresarial Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113206"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Puede administrar la mensajería unificada de Exchange y el correo de voz hospedado en Skype Empresarial Online mediante un conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Administrar la mensajería unificada de Exchange y el correo de voz hospedado

Los cmdlets siguientes se pueden usar para administrar la mensajería unificada (MU) de Exchange y las directivas de correo de voz hospedadas:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Crea y administra objetos de contacto usados para Operador automático y servicios de acceso de suscriptores, cuando Exchange UM es un servicio hospedado.  <br/><br/> Skype Empresarial Online funciona con Mensajería unificada de Exchange para proporcionar varias funcionalidades relacionadas con la voz, incluidos Operador automático y acceso de suscriptores. Operador automático proporciona una forma de que las llamadas se conteste automáticamente y se enrute a la persona correcta. Acceso para suscriptores permite a los usuarios conectarse a mensajería unificada de Exchange y recuperar correo electrónico, mensajes de voz, contactos e información del calendario.  <br/><br/> Cuando la mensajería unificada de Exchange se proporciona como un servicio hospedado, los objetos de contacto que se usan para los servicios Operador automático y acceso de suscriptores deben crearse con Microsoft PowerShell. Estos objetos se crean y administran con los **cmdlets CsExUmContact.** <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Administra las directivas de correo de voz hospedadas que se usan en la organización. Las directivas de correo de voz hospedadas especifican cómo se enrutar las llamadas sin responder al servicio de mensajería unificada de Exchange. Estas directivas afectan solo a los usuarios que se han habilitado para el correo de voz hospedado en MU de Exchange.  <br/><br/> Para comprobar si un usuario está habilitado para el correo de voz hospedado, ejecute un comando similar al siguiente desde el símbolo del sistema de PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
