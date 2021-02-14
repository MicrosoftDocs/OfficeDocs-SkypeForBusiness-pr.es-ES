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
description: 'En este tema se describe cómo habilitar a los usuarios para el Sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .'
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359146"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

En este tema se describe cómo habilitar a los usuarios para el Sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .
  
- To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para obtener información sobre cómo planear la implementación, consulte [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información sobre el Sistema telefónico, incluidas las licencias y los planes, consulte Planes de llamadas [RTC para Skype Empresarial.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)
    
> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuarios al sistema telefónico con conectividad RTC local

Antes de mover los usuarios a Skype Empresarial Online, se recomienda habilitar los usuarios locales en Skype Empresarial Server o Lync Server 2013 y, a continuación, moverlos en línea. Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y la sección de consideraciones especiales de Habilitar a los usuarios para [Telefonía IP empresarial](enable-the-users-for-enterprise-voice-on-premises.md) local (realizada mientras los usuarios se encuentran en el entorno local). 
  
Todos los usuarios deben crearse en Active Directory local y sincronizarse con Microsoft 365 u Office 365 con la versión compatible de Azure AD Connector. No puede habilitar usuarios para sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar sistema telefónico con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta Conector de Azure AD. 
  
Para habilitar un usuario para sistema telefónico con conectividad RTC local y, a continuación, moverlo a Skype Empresarial Online, es necesario seguir estos pasos:
  
- [Habilite los usuarios para Telefonía IP empresarial local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios se encuentran en el entorno local).
    
- [Asignar una directiva de enrutamiento de](assign-a-voice-routing-policy.md) voz (realizada mientras los usuarios están en el entorno local).
    
- [Sincronice los usuarios con la nube y asigne licencias (realizadas](synchronize-users-to-the-cloud-and-assign-licenses.md) con Office 365).
    
- [Mover usuarios locales](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) a Skype Empresarial Online (realizado con Windows PowerShell local, pero con sus credenciales de administrador de Office 365).
    
- [Habilite a los usuarios Telefonía IP empresarial correo](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) de voz del sistema telefónico y en línea (realizado con PowerShell remoto).
    

