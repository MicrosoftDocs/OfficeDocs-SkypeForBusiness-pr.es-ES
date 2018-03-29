---
title: Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Este tema describe cómo habilitar a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local. Antes de seguir los pasos de este tema, lea lo siguiente:.
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server
 
Este tema describe cómo habilitar a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local. Antes de seguir los pasos de este tema, lea lo siguiente:.
  
- Para aprender a configurar la conectividad híbrida, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y [conectividad de implementación híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener información acerca de cómo planear la implementación, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información sobre el sistema de teléfono en Office 365, incluyendo licencias y planes, consulte [PSTN llamando a planes de Skype para el negocio](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover los usuarios al sistema de teléfono en Office 365 con conectividad de RTC local

Antes de mover los usuarios a Skype para los negocios en línea, se recomienda permitir a los usuarios en las instalaciones de Skype para Business Server o Lync Server 2013 y moverlos en línea. Para obtener más información, consulte la sección Consideraciones especiales de [Permitir que los usuarios de Telefonía IP empresarial en instalaciones](enable-the-users-for-enterprise-voice-on-premises.md)y [Plan de conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) . 
  
Todos los usuarios deben ser creados en Active Directory en locales y sincronizados a Office 365 con la versión compatible de conector de AD de Azure. No puede habilitar a los usuarios para el sistema de teléfono en Office 365 creados directamente en Azure AD. Si desea habilitar el sistema de teléfono en Office 365 con conectividad de RTC local para un usuario que se creó en Azure AD, necesitará crear una nueva cuenta para ese usuario en sus instalaciones AD, configurar la cuenta local y, a continuación, sincronizar la cuenta mediante una versión compatible de la herramienta Conector de AD de Azure. 
  
Habilitar a un usuario para el sistema telefónico en Office 365 con conectividad de RTC local y, a continuación, moverlos a Skype para los negocios en línea requieren los pasos siguientes:
  
- [Permitir que los usuarios de Telefonía IP empresarial en instalaciones](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza cuando los usuarios están alojados en locales).
    
- [Asignar una directiva de enrutamiento de voz](assign-a-voice-routing-policy.md) (se realiza cuando los usuarios están alojados en locales).
    
- [Sincronizar usuarios a la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realiza mediante Office 365).
    
- [Mover usuarios locales a Skype para los negocios en línea](move-on-premises-users-to-skype-for-business-online.md) (se realiza mediante Windows PowerShell local, sino mediante sus credenciales de administrador de Office 365).
    
- [Permitir que los usuarios de Telefonía IP empresarial en línea y sistema de teléfono en el correo de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (lo realiza el uso de PowerShell remoto).
    

