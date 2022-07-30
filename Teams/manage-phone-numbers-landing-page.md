---
title: Administrar los números de teléfono para su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Obtenga información sobre cómo obtener y administrar números de teléfono de usuarios (suscriptores) y de servicio (de pago y gratuitos) para Microsoft Teams para su organización.
ms.openlocfilehash: 15caaa7b5d21ae86d0b0079aeb743690294fd85b
ms.sourcegitcommit: 3f6ae7946b64e857f6358019be2f0fdf19a207ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2022
ms.locfileid: "67074678"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Administrar los números de teléfono de su organización

Actualmente, Microsoft admite dos tipos de números de teléfono: 

- [**Números de usuario**](#user-telephone-numbers), también denominados números de suscriptor, que se pueden asignar a los usuarios de su organización.

- [**Números de servicio**](#service-telephone-numbers) asignados a servicios, como [Audioconferencia](deploy-audio-conferencing-teams-landing-page.md), [Operadores automáticos](plan-auto-attendant-call-queue.md) o Colas de [llamadas](plan-auto-attendant-call-queue.md).

Microsoft está trabajando para simplificar los tipos de números, pero por ahora tendrá que decidir:

- ¿Qué ubicaciones de usuario necesitan nuevos números de teléfono de Microsoft?
- ¿Qué tipo de número de teléfono (suscriptor o servicio) necesito?
- Cómo transferir los números de teléfono existentes a Teams?

La forma de adquirir y administrar los números de teléfono varía según la opción de conectividad de la red telefónica conmutada (RTC).

- Para obtener información sobre la administración de números de teléfono para Microsoft Calling Plan, consulte [Administrar números de teléfono para planes de llamadas](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obtener información sobre la administración de números de teléfono para Operador De conexión, vea [Configurar números de teléfono con Operador de conexión](operator-connect-configure.md#set-up-phone-numbers).

- Para obtener información sobre la administración de números de teléfono para enrutamiento directo, vea [Configurar el número de teléfono y habilitar la voz empresarial](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).


> [!NOTE]
> Si necesita tipos de números adicionales u otros que no sean los que se ven en el Centro de administración de Microsoft Teams, puede enviar una solicitud de número de teléfono al [Centro de servicio de números](https://pstnsd.powerappsportals.com/) de teléfono.

## <a name="user-telephone-numbers"></a>Números de teléfono de usuario

Hay dos tipos de números de teléfono de usuario, que se pueden asignar a los usuarios de su organización:  
    
- **Los números geográficos** tienen una relación con un área geográfica y son los más comunes. Por ejemplo, los números de teléfono geográficos en la mayoría de los casos solo se pueden usar dentro de una determinada dirección, ciudad, estado o región del país.
    
- **Los números no geográficos** se conocen como números nacionales o, a veces, números VoIP. Estos números no tienen una relación con un área geográfica dentro de un país o región. Por ejemplo, los números no geográficos suelen tener el mismo coste al llamar al número desde cualquier lugar dentro del país o la región. Además, algunos países, como Dinamarca, solo tienen números no geográficos disponibles.


## <a name="service-telephone-numbers"></a>Números de teléfono de servicio  

En esta sección se describen los números de servicio disponibles de Microsoft que se incluyen en la licencia. Para obtener información sobre los números de servicio proporcionados por el operador Conectar o enrutamiento directo, póngase en contacto con su proveedor. 

Hay dos tipos de números de teléfono de servicio proporcionados por Microsoft (de pago y gratuitos) que se pueden asignar a servicios como Audioconferencia, Operadores automáticos o Colas de llamadas. Los números de servicio tienen una mayor capacidad de llamadas simultáneas que los números de usuario. La disponibilidad del número de servicio varía según el país o la región y el tipo de número (ya sea un número de pago o gratuito). Las licencias de telefonía de Microsoft en cada país o región determinan para qué se puede usar el número.
    
 - **Números de servicio** de pago: existen dos tipos de números de servicio de pago, que pueden conllevar un coste de pago para el autor de la llamada:
    
   - **Números geográficos** Los números geográficos tienen una relación con un área geográfica. Por ejemplo, los números de teléfono geográficos en la mayoría de los casos solo se pueden usar dentro de una determinada dirección, ciudad, estado o región del país.
        
   - **Números no geográficos** Los números no geográficos son números nacionales que no tienen una relación con un área geográfica dentro de un país o región. Por ejemplo, los números no geográficos suelen tener el mismo coste al llamar al número desde cualquier lugar dentro del país o la región.
   
- **Números de servicio gratuitos** : estos números de servicio no suelen conllevar un coste de pago para el autor de la llamada. Teams proporciona números gratuitos nacionales en más de 60 países o regiones.
    
    > [!CAUTION]
    > Algunos países o regiones y tipos de números originales, como las llamadas que provienen de teléfonos móviles, pueden en algunos casos conllevar un coste de pago para el autor de la llamada. 

## <a name="where-phone-numbers-are-managed"></a>Dónde se administran los números de teléfono

La ubicación y cómo se administran los números dependen de la opción de conectividad con RTC:

- Los números de teléfono Microsoft Calling Plan y Operator Connect solo se pueden administrar en Microsoft 365.

- Los números de teléfono de enrutamiento directo se pueden administrar en la Active Directory local o en Microsoft 365, como se describe en las secciones siguientes.

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>Números de enrutamiento directo administrados en un Active Directory local

Si tiene o ha tenido una implementación híbrida Skype Empresarial Server, lo más probable es que el Active Directory local se sincronice con Microsoft 365. Esto significa que los atributos del directorio en las cuentas de usuarios y recursos se administran en el Active Directory local y se sincronizan en Microsoft 365.

Si el número de teléfono de enrutamiento directo se administra en la cuenta de usuario o recurso de la Active Directory local, el parámetro msRTCSIP-Line de la cuenta contiene un valor. Puede usar una herramienta como Edición ADSI para ver el parámetro msRTCSIP-Line de una cuenta de usuario o recurso que tiene un número de teléfono de enrutamiento directo asignado en Active Directory local.   

Después de que este parámetro se sincronice automáticamente con la cuenta de usuario o recurso de Microsoft 365 a través del proceso de sincronización de directorios (Azure AD Connect), puede ver el número de teléfono consultando el parámetro OnPremLineURi en el resultado del cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) .

| Dónde | Parámetro | Valor |
| :------------| :-------| :---------|
| AD local | msRTCSIP-Line | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>Números de enrutamiento directo administrados en Microsoft 365

Si no administra los números de teléfono de Enrutamiento directo en la Active Directory local, estos se administran en Microsoft 365. Como los números de teléfono no se sincronizan con Microsoft 365, no están visibles en el parámetro OnPremLineUri en el resultado de la ejecución del cmdlet Get-CsOnlineUser para la cuenta de usuario o recurso.

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>Números de enrutamiento directo administrados tanto en un Active Directory local como en Microsoft 365

Es posible administrar los números de teléfono de enrutamiento directo de algunas cuentas de usuario y recursos en una Active Directory local y números de teléfono de enrutamiento directo de otras cuentas en Microsoft 365. Esta capacidad depende de si el atributo msRTCSIP-Line se establece en la cuenta de usuario o recurso de la Active Directory local.    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>Cambiar dónde se administran los números de teléfono de enrutamiento directo

Para cambiar la ubicación en la que se administra un número de teléfono de enrutamiento directo, debe quitar el número de teléfono del atributo msRTCSIP-Line del usuario o de la cuenta resouce de la Active Directory local.   

Para obtener más información, vea [Borrar atributos de Skype Empresarial para todos los usuarios locales en Active Directory](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md). Tenga en cuenta que el número de teléfono debe reasignarse a la cuenta de usuario o recurso en Microsoft 365.

Después de sincronizar la eliminación con Microsoft 365, el atributo OnPremLineUri del resultado de Get-CsOnlineUser en la cuenta de usuario o recurso estará vacío. 

