---
title: "Administrar la mensajería unificada de Exchange y aloja el correo de voz"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "Usar PowerShell para administrar las capacidades de mensajería unificada de Exchange como Operador automático y acceso de suscriptor y correo de voz hospedado en Skype para los negocios en línea."
ms.openlocfilehash: a5f358d06ed7c7e805aeffbce6a6898cc2a86b73
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Administrar la mensajería unificada de Exchange y aloja el correo de voz

Puede administrar la mensajería unificada de Exchange y alojado el correo de voz de Skype para los negocios en línea mediante un conjunto de cmdlets.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Administrar la mensajería unificada de Exchange y aloja el correo de voz

Los cmdlets siguientes puede utilizarse para administrar Exchange Unified Messaging (UM) y alojada en las directivas de buzón de voz:
  
|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [Nueva CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Quitar CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Conjunto de CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crea y administra objetos de contacto utilizados para los servicios de Operador automático y acceso de suscriptor, cuando la mensajería unificada de Exchange es un servicio hospedado.  <br/><br/> Skype para los negocios en línea funciona con mensajería unificada de Exchange para proporcionar varias capacidades relacionadas con la voz, incluyendo acceso de suscriptor y Operador automático. Operador automático proporciona una forma de llamadas a automáticamente se responden y se enruta a la persona correcta. Acceso de suscriptores permite a los usuarios conectarse a mensajería unificada de Exchange y recuperar la información de calendario, contactos, mensajes de voz y correo electrónico.  <br/><br/> Cuando la mensajería unificada de Exchange se proporciona como un servicio hospedado, objetos de contacto utilizados para los servicios de Operador automático y acceso de suscriptor deben crearse utilizando Microsoft PowerShell. Estos objetos se crean y se administran mediante los cmdlets de **CsExUmContact** . <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Concesión CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Administra las políticas de correo de voz hospedado utilizadas en la organización. Las políticas de correo de voz hospedado especifican cómo sin contestar las llamadas se enrutan al servicio de mensajería unificada de Exchange. Estas directivas afectan a sólo los usuarios que han sido habilitados para mensajería unificada de Exchange alojado en el correo de voz.  <br/><br/> Para comprobar si un usuario está habilitado para correo de voz hospedado, ejecute un comando similar al siguiente en el símbolo del sistema de PowerShell.  <br/> ' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail'|
   

## <a name="related-topics"></a>Temas relacionados
[Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell](set-up-your-computer-for-windows-powershell.md)