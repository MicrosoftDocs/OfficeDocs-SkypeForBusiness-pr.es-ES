---
title: Habilitar a los usuarios para sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
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
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad con RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050192"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar a los usuarios para sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
 
En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad con RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
  
- Para obtener información sobre cómo configurar la conectividad híbrida, vea [plan Hybrid Connectivity between Skype for Business Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implemente la conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener información sobre cómo planear la implementación, consulte [plan Phone System in Office 365 with on-premises RTC Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información acerca del sistema telefónico en Office 365, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover usuarios al sistema telefónico en Office 365 con conectividad con RTC local

Antes de mover los usuarios a Skype empresarial online, se recomienda que habilite a los usuarios de forma local en Skype empresarial Server o Lync Server 2013 y, a continuación, los mueva en línea. Para obtener más información, vea [plan Hybrid Connectivity between Skype for Business Server y Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y la sección de consideraciones especiales de [habilitar los usuarios para la telefonía IP empresarial](enable-the-users-for-enterprise-voice-on-premises.md) local (se realiza mientras los usuarios están hospedados de forma local). 
  
Todos los usuarios se deben crear en Active Directory local y sincronizarse con Office 365 con la versión compatible del conector de Azure AD. No puede habilitar a los usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar el sistema telefónico en Office 365 con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta conector de Azure AD. 
  
La habilitación de un usuario para sistema telefónico en Office 365 con conectividad con RTC local y su traslado a Skype empresarial online requiere los pasos siguientes:
  
- [Habilite a los usuarios para la telefonía IP empresarial](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios están hospedados de forma local).
    
- [Asignar una directiva de enrutamiento de voz](assign-a-voice-routing-policy.md) (se realiza mientras los usuarios están hospedados de forma local).
    
- [Sincronizar los usuarios con la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realizadas con Office 365).
    
- [Mueva a los usuarios locales a Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (se realiza mediante Windows PowerShell local, pero usando sus credenciales de administrador de Office 365).
    
- [Habilite a los usuarios para telefonía IP empresarial en línea y sistema telefónico en el correo de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realizado con PowerShell remoto).
    

