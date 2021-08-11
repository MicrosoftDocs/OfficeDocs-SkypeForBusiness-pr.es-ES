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
description: 'En este tema se describe cómo habilitar a los usuarios Sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .'
ms.openlocfilehash: 1706c91bc9e277da75253ab2f8675d6dc9c4c06c6057668f69cfd7da058691e3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288878"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

En este tema se describe cómo habilitar a los usuarios Sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .
  
- Para obtener información sobre cómo configurar la conectividad híbrida, vea [Plan hybrid connectivity between Skype Empresarial Server and Skype Empresarial Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype Empresarial Server and Skype Empresarial [Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Para obtener información sobre la planeación de la implementación, [vea Plan Sistema telefónico with on-premises PSTN connectivity in Skype Empresarial Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para obtener más información Sistema telefónico, incluidas las licencias y los planes, vea Planes de llamadas [RTC para Skype Empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad RTC entre el entorno local mediante Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuarios a Sistema telefónico con conectividad RTC local

Antes de mover los usuarios a Skype Empresarial Online, se recomienda habilitar los usuarios locales en Skype Empresarial Server o Lync Server 2013 y, a continuación, moverlos en línea. Para obtener más información, vea [Plan hybrid connectivity between Skype Empresarial Server and Skype Empresarial Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) y la sección de consideraciones especiales de Enable the users for Telefonía IP empresarial on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises). 
  
Todos los usuarios deben crearse en Active Directory localmente y sincronizarse Microsoft 365 o Office 365 con la versión compatible de Azure AD Connector. No puede habilitar usuarios para Sistema telefónico en Office 365 que se crearon directamente en Azure AD. Si desea habilitar Sistema telefónico con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta Azure AD Connector. 
  
Habilitar un usuario para Sistema telefónico con conectividad RTC local y, a continuación, moverlos a Skype Empresarial Online requiere los siguientes pasos:
  
- [Habilite los usuarios para Telefonía IP empresarial local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios se encuentran en el entorno local).
    
- [Asignar una directiva de enrutamiento de](assign-a-voice-routing-policy.md) voz (realizada mientras los usuarios se encuentran en el entorno local).
    
- [Sincronizar usuarios con la nube y asignar licencias (realizadas](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) mediante Office 365).
    
- [Mover usuarios locales a Skype Empresarial Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (realizado con Windows PowerShell local, pero con las credenciales Office 365 administrador).
    
- [Habilite a los usuarios Telefonía IP empresarial en](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) línea y Sistema telefónico correo de voz (realizado con PowerShell remoto).
