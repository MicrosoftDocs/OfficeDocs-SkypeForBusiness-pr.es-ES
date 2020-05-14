---
title: Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server
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
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221100"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server
 
En este tema se describe cómo habilitar a los usuarios para el sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
  
- Para obtener información sobre cómo configurar la conectividad híbrida, vea [plan Hybrid Connectivity between Skype for Business Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implemente la conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener información sobre cómo planear la implementación, consulte [plan Phone System with on-local RTC Connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información acerca del sistema telefónico, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuarios al sistema telefónico con conectividad con RTC local

Antes de mover los usuarios a Skype empresarial online, se recomienda que habilite a los usuarios de forma local en Skype empresarial Server o Lync Server 2013 y, a continuación, los mueva en línea. Para obtener más información, vea [plan Hybrid Connectivity between Skype for Business Server y Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y la sección de consideraciones especiales de [habilitar los usuarios para la telefonía IP empresarial](enable-the-users-for-enterprise-voice-on-premises.md) local (se realiza mientras los usuarios están hospedados de forma local). 
  
Todos los usuarios deben crearse en Active Directory local y sincronizarse con Microsoft 365 u Office 365 mediante la versión compatible del conector de Azure AD. No puede habilitar a los usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar el sistema telefónico con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta conector de Azure AD. 
  
Para habilitar a un usuario para el sistema telefónico con conectividad RTC local y, a continuación, para moverlo a Skype empresarial online, es necesario seguir estos pasos:
  
- [Habilite a los usuarios para la telefonía IP empresarial](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios están hospedados de forma local).
    
- [Asignar una directiva de enrutamiento de voz](assign-a-voice-routing-policy.md) (se realiza mientras los usuarios están hospedados de forma local).
    
- [Sincronizar los usuarios con la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realizadas con Office 365).
    
- [Mueva a los usuarios locales a Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (se realiza mediante Windows PowerShell local, pero usando sus credenciales de administrador de Office 365).
    
- [Habilite a los usuarios para Enterprise Voice online y el correo de voz de sistema telefónico](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (se realiza con PowerShell remoto).
    

