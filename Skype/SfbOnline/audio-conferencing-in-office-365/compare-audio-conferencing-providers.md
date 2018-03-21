---
title: "Comparar proveedores de conferencias de acceso telefónico local"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b0d2b50e-def3-4bd8-82d4-a27f4b6f205c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Cuando se configuran conferencias de acceso telefónico local o RTC para Skype Empresarial, es necesario elegir un proveedor de conferencias de acceso telefónico local. Puede elegir Microsoft como su proveedor de conferencias de acceso telefónico local o un tercero."
ms.openlocfilehash: e2b08b9d5db41cd9f6a0bff6d000c65ecbe6dfba
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="compare-audio-conferencing-providers"></a>Comparar proveedores de conferencias de acceso telefónico local

[] Cuando se configuran conferencias de acceso telefónico local o RTC para Skype Empresarial, es necesario elegir un proveedor de conferencias de acceso telefónico local. Puede elegir Microsoft como su proveedor de conferencias de acceso telefónico local o un tercero. 
  
> [!IMPORTANT]
> Tanto si es Microsoft como un tercero, el proveedor de conferencias de acceso telefónico local hará lo siguiente: 
  
Audio conferencing providers do the following: 
  
- Proporcionan un *puente de conferencia de audio*. El puente de conferencia establecerá la conferencia identificadores para las reuniones, pines y números de teléfono de acceso telefónico.
    
- Definirá el idioma que los usuarios escucharán al llamar a una reunión.
    
- Creará los id. de conferencia que se utilizan cuando los usuarios se unen a una reunión.
    
- Proporcionará los PIN de organizador para iniciar las reuniones por teléfono.
    
- Utilice la siguiente tabla para comparar lo que obtiene si elige como proveedor de conferencias de acceso telefónico local a Microsoft o a un tercero.
    
Use the following table to compare what you get if you choose Microsoft or a third-party audio conferencing provider.
  
||||
|:-----|:-----|:-----|
|**Microsoft (Office 365)** <br/> |**Un tercero** <br/> |Configuración del proveedor <br/> |
|Fácil de configurar. La mayor parte de la configuración es automática.  <br/> |Difícil de configurar. Requiere pasos manuales.  <br/> |Licencias  <br/> |
|Licensing  <br/> |Se requiere una licencia de **Conferencia de Audio** . See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> |Administración  <br/> |
|Integrada en el centro de administración de Office 365.  <br/> |Administración manual con el tercero  <br/> |Configuración de usuarios  <br/> |
|Fácil  <br/> |Difícil  <br/> |Facturación  <br/> |
|A través de Office 365  <br/> |Adicional a través del ACP de terceros.  <br/> | Asignación de puente de conferencias de acceso telefónico local <br/> |
|Automática  <br/> |Requiere una entrada manual del puente de conferencia para cada usuario.  <br/> |Administración de id. de conferencia  <br/> |
|Automática  <br/> |Manual  <br/> |Restablecer id. de conferencia de reunión  <br/> |
|Reset meeting conference ID  <br/> |Sí, pero tendrá que introducirlo manualmente.<br/> |Números de teléfono gratuitos  <br/> |
|Sí  <br/> |Sí  <br/> |Números de teléfono nacionales de pago  <br/> |
|Sí  <br/> |Sí  <br/> |Números de teléfono internacionales de pago  <br/> |
|Sí  <br/> |Sí  <br/> |Transferir números de teléfono existentes  <br/> |
|Sí  <br/> |No  <br/> |Acceso telefónico/Llamarme: nacional  <br/> |
|Sí  <br/> |Sí  <br/> |Acceso telefónico/Llamarme: internacional  <br/> |
|Dial-out / Call-me - International  <br/> |Sí, pero solo está disponible en algunos países o regiones. Ver [disponibilidad de país y región para conferencias de Audio y llamar a planes](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) para obtener una lista de países y regiones compatibles. <br/> |El organizador de la reunión puede autenticar a través de un PIN.  <br/> |
|Sí  <br/> |No  <br/> |Cualquier usuario de la organización puede autenticar mediante un PIN  <br/> |
|No  <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |
|Sí  <br/> |Sí  <br/> |Página de acceso telefónico adicional con una lista completa de los números de teléfono de acceso telefónico admitidos  <br/> |
|Sí  <br/> |Sí  <br/> |Opción para iniciar una reunión de terceros sin un PIN  <br/> |
|Sí  <br/> |No  <br/> |Compatibilidad con varios idiomas  <br/> |
|Multiple language support  <br/> |Sí. Ver [idiomas admitidos de conferencia de Audio](audio-conferencing-supported-languages.md).  <br/> |Administración de idiomas para el operador automático de la reunión.  <br/> |
|Sí  <br/> |Sí  <br/> |Compatibilidad en varios países o regiones  <br/> |
|Multiple country/region support  <br/> |Sí. Ver [disponibilidad de país y región para conferencias de Audio y llamar a los planes](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).  <br/> |Los usuarios escuchan música en espera si la reunión no se ha iniciado o si la reunión se ha bloqueado.  <br/> |
|Sí  <br/> |No  <br/> |Configuración de un número de acceso telefónico internacional como número de acceso telefónico predeterminado (que se muestra en la invitación a la reunión) para un usuario  <br/> |
|Sí  <br/> |No  <br/> |Experiencia integrada para el usuario de Skype Empresarial Online para restablecer el Id. de conferencia de reunión y el PIN  <br/> |
|Disponible en una versión futura  <br/> |No  <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |
|Disponible en una versión futura  <br/> |No  <br/> |No  <br/> |
   
See also
  
## <a name="related-topics"></a>See also

[Conferencias de acceso telefónico en Office 365](set-up-audio-conferencing.md)
