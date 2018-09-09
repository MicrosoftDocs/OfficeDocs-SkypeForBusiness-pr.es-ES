---
title: Habilitar a usuarios para el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad de RTC local. Antes de seguir los pasos descritos en este tema, debe leer los siguientes:.
ms.openlocfilehash: 7427bf33c275d55b99c240aaf192d180c2d63945
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887405"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar a usuarios para el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server
 
En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad de RTC local. Antes de seguir los pasos descritos en este tema, debe leer los siguientes:.
  
- Para obtener información sobre cómo configurar la conectividad híbrida, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y la [conectividad de híbrido de implementar entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener información acerca de cómo planear la implementación, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información acerca del sistema de teléfono en Office 365, incluida la concesión de licencias y planes, consulte [planes de RTC de llamada de Skype para la empresa](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover a los usuarios al sistema de teléfono en Office 365 con conectividad de RTC local

Antes de mover los usuarios a Skype para profesionales en línea, se recomienda que permiten a los usuarios en local en Skype para Business Server o Lync Server 2013 y, a continuación, muévalos en línea. Para obtener más información, vea la sección Consideraciones especiales de [Habilitar a los usuarios para Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md)y [planeación de la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) . 
  
Todos los usuarios deben crearse en Active Directory local y sincronizan en Office 365 con la versión admitida del conector de AD de Azure. No se puede habilitar a los usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar el sistema telefónico en Office 365 con conectividad de RTC local para un usuario que se creó en Azure AD, que necesitará para crear una nueva cuenta para ese usuario en sus instalaciones AD, configuración de la cuenta local y, a continuación, sincronizar el uso de la cuenta una versión compatible de la herramienta de conector de AD de Azure. 
  
Habilitar a un usuario para el sistema telefónico en Office 365 con conectividad de RTC local y, a continuación, moverlos a Skype para profesionales Online requieren los siguientes pasos:
  
- [Habilitar a los usuarios para Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza cuando los usuarios están hospedados en implementaciones locales).
    
- [Asignar una directiva de enrutamiento de voz](assign-a-voice-routing-policy.md) (se realiza cuando los usuarios están hospedados en implementaciones locales).
    
- [Sincronizar a los usuarios a la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realiza mediante Office 365).
    
- [Mover a los usuarios de local Skype para profesionales en línea](move-on-premises-users-to-skype-for-business-online.md) (lo realiza el uso de Windows PowerShell local, pero con sus credenciales de administrador de Office 365).
    
- [Habilitar a los usuarios para Enterprise Voice en línea y el sistema de teléfono en el correo de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realizado mediante PowerShell remoto).
    

