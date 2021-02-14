---
title: Cuentas de usuario en entorno híbrido con RTC
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
description: Obtenga información sobre las distintas combinaciones de creación de usuarios y qué combinaciones son compatibles o incompatibles.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7b41eb474d7574aa23b5fa195219794ed715424
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690876"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Cuentas de usuario en un entorno híbrido con conectividad RTC

## <a name="about-the-environment"></a>Acerca del entorno

Este artículo se aplica a los entornos en los que tiene todo lo siguiente: 
 
- Skype Empresarial Server o Lync Server 2013 
- Una organización de Microsoft 365 u Office 365 
- Conectividad híbrida configurada entre Skype Empresarial Server y Skype Empresarial Online o el espacio empresarial de Microsoft Teams 
- Usuarios habilitados para realizar y recibir llamadas de red telefónica conmutada (RTC) hacia y desde el cliente

 
Si tiene un entorno diferente (por ejemplo, Skype Empresarial Cloud Connector Edition), la implementación híbrida no está configurada o los usuarios no están habilitados para las llamadas RTC, la matriz de compatibilidad será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Acerca de las combinaciones y la declaración de compatibilidad  

Un entorno híbrido de Skype Empresarial con conectividad RTC proporciona flexibilidad respecto a dónde se proporcionan los servicios de usuario y cómo se aprovisionan y administran las cuentas de usuario. Sin embargo, la variedad de opciones podría crear algunas combinaciones no admitidas. En esta sección se explican las distintas combinaciones de creación de usuarios, seguidas de una instrucción de compatibilidad.


**Definiciones:**   
- **Telefonía IP empresarial:** Opción para proporcionar acceso a RTC para los usuarios con una cuenta de usuario de Skype Empresarial local. El servidor de mediación local de Skype Empresarial proporciona interconexión a RTC.  
- **Conectividad de voz híbrida:** Opción para proporcionar acceso a RTC para los usuarios con una cuenta de Skype Empresarial Online. El servidor de mediación local de Skype Empresarial proporciona interconexión a RTC. 
- **Enrutamiento directo:** Opción para proporcionar acceso a RTC para los usuarios con una cuenta de Skype Empresarial en línea o una licencia de Microsoft Teams, con el cliente de Microsoft Teams. La SBC se conecta al proxy SIP en Microsoft 365 u Office 365 sin necesidad de ningún software local de Microsoft.

  
**El entorno admite las siguientes combinaciones:**
- **Escenario 1:** Cuenta de usuario en Skype Empresarial local y usará el cliente de Skype Empresarial con Telefonía IP empresarial
- **Escenario 2:** Cuenta de usuario en Skype Empresarial Online y usará el cliente de Skype Empresarial con conectividad de voz híbrida
- **Escenario 3:** Cuenta de usuario en Skype Empresarial Online con licencia de Microsoft Teams y usará el cliente de Teams
 
### <a name="supportability-matrix"></a>Matriz de compatibilidad


|**Objeto de usuario creado en**  |**Proveedor de servicios de Skype Empresarial del usuario**|**Cliente del usuario**|**Opción de voz**|**Compatible**|
| ------------ | --------- | --------- | --------- | -------- |
|AD local| Implementación local |Skype Empresarial   | Telefonía IP empresarial   |Sí|
|AD local|Online| Skype Empresarial  | Conectividad de voz híbrida   |Sí |
|AD local|Online |Microsoft Teams |Enrutamiento directo  |Sí |
|**Combinaciones no admitidas**    | |         |         |      |
|Azure AD| Local/en línea | Skype Empresarial/Microsoft Teams|Telefonía IP empresarial/conectividad de voz híbrida/enrutamiento directo  |No, el objeto de usuario DEBE crearse primero en ad local |
|AD local  |Implementación local| Microsoft Teams| Telefonía IP empresarial/conectividad de voz híbrida/enrutamiento directo   |No, el cliente de Microsoft Teams no es compatible con Skype Empresarial local |     
|AD local  |Online |Skype Empresarial  | Enrutamiento directo  |No, el enrutamiento directo no se admite con el cliente de Skype Empresarial  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Declaración de compatibilidad para el entorno híbrido con RTC

Para todos los usuarios, el objeto de usuario debe crearse en el AD local y sincronizarse con Azure AD con la herramienta Azure AD Connect.  No se admite la  habilitación de usuarios para Teams/Skype Empresarial si el objeto de usuario se crea directamente en Azure AD en una configuración híbrida. Para los nuevos usuarios, como los nuevos empleados, que se habilitarán directamente para Teams, el usuario debe estar habilitado para Skype Empresarial con las herramientas de administración locales de Skype Empresarial. No se admite la creación de usuarios en Skype Empresarial o Teams en línea sin habilitarlos primero en un grupo local Telefonía IP empresarial **usuarios.** Para obtener más información sobre esto, consulte Plan Phone System con conectividad RTC local [en Skype Empresarial Server.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
