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
description: 'En este tema se describe cómo habilitar a los usuarios del sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120872"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

En este tema se describe cómo habilitar a los usuarios del sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .
  
- Para obtener información sobre cómo configurar la conectividad híbrida, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Para obtener información sobre cómo planear la implementación, vea [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información acerca del sistema telefónico, incluidas las licencias y los planes, vea Planes de llamadas [RTC para Skype Empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, la conectividad RTC entre el entorno local ya no se admite a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuarios al sistema telefónico con conectividad RTC local

Antes de mover los usuarios a Skype Empresarial Online, se recomienda habilitar los usuarios locales en Skype Empresarial Server o Lync Server 2013 y, a continuación, moverlos en línea. Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) y la sección de consideraciones especiales de Enable the users for Telefonía IP empresarial on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (realizado mientras los usuarios se encuentran en el entorno local). 
  
Todos los usuarios deben crearse en Active Directory localmente y sincronizarse con Microsoft 365 u Office 365 mediante la versión compatible de Azure AD Connector. No puede habilitar usuarios de Sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar el sistema telefónico con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta Azure AD Connector. 
  
Habilitar un usuario para sistema telefónico con conectividad RTC local y, a continuación, moverlos a Skype Empresarial Online requiere los siguientes pasos:
  
- [Habilite los usuarios para Telefonía IP empresarial local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios se encuentran en el entorno local).
    
- [Asignar una directiva de enrutamiento de](assign-a-voice-routing-policy.md) voz (realizada mientras los usuarios se encuentran en el entorno local).
    
- [Sincronizar usuarios con la nube y asignar licencias (realizadas](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) con Office 365).
    
- [Mover usuarios locales a Skype Empresarial Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (realizado con Windows PowerShell local, pero con sus credenciales de administrador de Office 365).
    
- [Habilite a los usuarios para Telefonía IP empresarial en](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) línea y el correo de voz del sistema telefónico (realizado con PowerShell remoto).
