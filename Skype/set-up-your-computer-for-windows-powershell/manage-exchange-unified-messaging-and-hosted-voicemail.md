---
title: "Administrar la mensajería unificada de Exchange y alojado correo de voz de Skype empresarial Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Administrar la mensajería unificada de Exchange y alojado correo de voz de Skype empresarial Online

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Puede administrar Exchange mensajería unificada y correo de voz hospedado en Skype Empresarial Online mediante un conjunto de cmdlets.
  
## Administrar la mensajería unificada de Exchange y alojado correo de voz

Los siguientes cmdlets puede usarse para administrar Exchange directivas de hospedado de correo de voz y mensajería unificada:
  
|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [Nueva CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Quitar CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Establecer CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crea y administra objetos de contacto que utiliza para los servicios de operador automático y acceso de suscriptor, cuando Exchange MU es un servicio hospedado.  <br/> Skype Empresarial Online funciona con Exchange MU para proporcionar varias funciones relacionadas con la voz, incluidos operador automático y acceso de suscriptor. Operador automático proporciona una manera para las llamadas automáticamente se responde y se dirige a la persona correcta. Acceso de suscriptores permite a los usuarios conectarse a Exchange mensajería unificada y recuperar correo electrónico, mensajes de voz, contactos y la información de calendario.  <br/> Cuando Exchange MU se proporciona como un servicio hospedado, objetos de contacto que utiliza para los servicios de operador automático y el acceso de suscriptor deben crearse mediante Microsoft PowerShell. Estos objetos se crean y se administra mediante los cmdlets **CsExUmContact**. <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Conceder CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Administra las directivas de correo de voz hospedado utilizadas en la organización. Directivas de correo de voz hospedado especifican las llamadas no respondidas cómo se enrutan al servicio de mensajería unificada Exchange. Estas directivas afecta solo los usuarios que se han habilitado para Exchange MU habían hospedado correo de voz.  <br/> Para comprobar si un usuario está habilitado para hospeda el correo de voz, ejecutar un comando similar al siguiente en el símbolo del sistema de PowerShell.  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

