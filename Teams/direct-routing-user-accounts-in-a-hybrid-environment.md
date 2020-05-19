---
title: Cuentas de usuario en entornos híbridos con RTC
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga más información sobre las diferentes combinaciones de creación de usuarios y qué combinaciones son compatibles o no.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 635ab29498ee01c976b33dc62a193bb723ba190e
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280259"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Cuentas de usuario en un entorno híbrido con conectividad RTC

## <a name="about-the-environment"></a>Acerca del entorno

Este artículo se aplica a entornos en los que tiene todas las opciones siguientes: 
 
- Skype empresarial Server o Lync Server 2013 
- Una organización de Office 365 
- Conectividad híbrida configurada entre Skype empresarial Server y Skype empresarial online o el inquilino de Microsoft Teams 
- Usuarios que tienen habilitada la opción de realizar y recibir llamadas de red telefónica conmutada (RTC) a y desde el cliente

 
Si tiene un entorno diferente (como Skype empresarial Cloud Connector Edition), no está configurado para entornos híbridos o los usuarios no tienen habilitada la opción de llamadas RTC, la matriz de compatibilidad será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Acerca de las combinaciones y la declaración de compatibilidad  

Un entorno híbrido de Skype empresarial con conectividad RTC proporciona flexibilidad en cuanto a la ubicación de los servicios de usuario y el aprovisionamiento y la administración de las cuentas de usuario. Pero la abundancia de opciones puede crear algunas combinaciones no admitidas. En esta sección se explican las distintas combinaciones de creación de usuarios, seguida de una declaración de compatibilidad.


**Las**   
- **Telefonía IP empresarial:** Opción para proporcionar acceso a RTC para usuarios con una cuenta de usuario local de Skype empresarial. El servidor de mediación de Skype para empresas local permite la interconectividad con RTC.  
- **Conectividad de voz híbrida:** Opción para proporcionar acceso a RTC para usuarios con cuenta de Skype empresarial online. El servidor de mediación de Skype para empresas local permite la interconectividad con RTC. 
- **Enrutamiento directo:** Opción para proporcionar acceso a RTC para los usuarios con una cuenta de Skype empresarial en línea, licencia de Microsoft Teams, con el cliente de Microsoft Teams. La SBC está conectada al proxy SIP en Office 365 sin necesidad de ningún software local de Microsoft.

  
**El entorno admite las siguientes combinaciones:**
- **Escenario 1:** Cuenta de usuario en Skype empresarial local y usará el cliente de Skype empresarial con telefonía IP empresarial
- **Escenario 2:** Cuenta de usuario en Skype empresarial online y usará el cliente de Skype empresarial con conectividad de voz híbrida
- **Escenario 3:** Cuenta de usuario en Skype empresarial online con la licencia de Microsoft Teams y usará el cliente de Teams
 
### <a name="supportability-matrix"></a>Matriz de capacidad de soporte


|**Objeto de usuario creado en**  |**Proveedor de servicios de Skype empresarial del usuario**|**Cliente del usuario**|**Opción de voz**|**Compatible**|
| ------------ | --------- | --------- | --------- | -------- |
|ANUNCIO local| Implementación local |Skype Empresarial   | Telefonía IP empresarial   |Sí|
|ANUNCIO local|Online| Skype Empresarial  | Conectividad de voz híbrida   |Sí |
|ANUNCIO local|Online |Microsoft Teams |Enrutamiento directo  |Sí |
|**Combinaciones no admitidas**    | |         |         |      |
|Azure AD| Local o en línea | Skype empresarial/Microsoft Teams|Voz empresarial/conectividad híbrida de voz/enrutamiento directo  |No, el objeto de usuario debe crearse primero en un anuncio local |
|ANUNCIO local  |Implementación local| Microsoft Teams| Voz empresarial/conectividad híbrida de voz/enrutamiento directo   |No, el cliente de Microsoft Teams no es compatible con Skype empresarial local |     
|ANUNCIO local  |Online |Skype Empresarial  | Enrutamiento directo  |No, el enrutamiento directo no es compatible con el cliente de Skype empresarial  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Declaración de compatibilidad para el entorno híbrido con RTC

Para todos los usuarios, el objeto de usuario **debe** crearse en el anuncio local y sincronizarse con Azure ad con la herramienta Azure ad Connect. **No se admite** la habilitación de usuarios para equipos o Skype empresarial si el objeto de usuario se crea directamente en Azure ad en una configuración híbrida. Para los nuevos usuarios, como un nuevo empleado, que se habilitará directamente para los equipos, el usuario debe estar habilitado para Skype empresarial mediante las herramientas de administración locales de Skype empresarial. **No es posible**crear usuarios en línea en Skype empresarial o Teams sin necesidad de habilitarlos en un grupo local con la telefonía IP empresarial. Para obtener más información, consulte [plan Phone System en Office 365 con conectividad RTC local en Skype empresarial Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
