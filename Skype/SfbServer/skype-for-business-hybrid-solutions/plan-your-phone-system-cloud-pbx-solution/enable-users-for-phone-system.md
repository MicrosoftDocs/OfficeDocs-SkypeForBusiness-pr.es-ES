---
title: Habilitar usuarios para el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
ms.openlocfilehash: c0c9f840c15e40aa3a78b69a5cbbf2f721251bbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802190"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuarios para el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
 
En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
  
- Para obtener información sobre cómo configurar la conectividad híbrida, consulte planear la conectividad [híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener más información sobre cómo planear la implementación, consulte [planear el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información sobre el sistema telefónico en Office 365, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover usuarios a un sistema telefónico en Office 365 con conectividad RTC local

Antes de mover los usuarios a Skype empresarial online, se recomienda habilitar a los usuarios locales en Skype empresarial Server o Lync Server 2013 y, a continuación, moverlos a través de Internet. Para obtener más información, consulte [planear la conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , y la sección de consideraciones especiales de [habilitar los usuarios de Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realizan mientras los usuarios están alojados de forma local). 
  
Todos los usuarios deben crearse en Active Directory local y sincronizarse con Office 365 con la versión compatible del conector de Azure AD. No puede habilitar usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si quiere habilitar el sistema telefónico en Office 365 con conectividad RTC local para un usuario que se creó en Azure AD, tendrá que crear una cuenta nueva para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta conector de Azure AD. 
  
Habilitar un usuario para el sistema telefónico en Office 365 con conectividad RTC local y, a continuación, moverlos a Skype empresarial online requiere los pasos siguientes:
  
- [Habilitar a los usuarios para Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realizan mientras los usuarios están alojados de forma local).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (realizado mientras los usuarios están hospedados de forma local).
    
- [Sincronizar los usuarios con la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realizadas con Office 365).
    
- [Mover usuarios locales a Skype empresarial online (se](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) realiza con Windows PowerShell local, pero usando las credenciales de administrador de Office 365).
    
- [Habilite los usuarios de Enterprise Voice online y el sistema telefónico en el buzón de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (se realiza con PowerShell remoto).
    

