---
title: Cuentas de usuario en un entorno híbrido con RTC
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre las distintas combinaciones de creación de usuarios y qué combinaciones son compatibles o no compatibles.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676422"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Cuentas de usuario en un entorno híbrido con conectividad RTC

## <a name="about-the-environment"></a>Acerca del entorno

Este artículo se aplica a entornos en los que tiene todos los siguientes elementos:

- Skype Empresarial Server o Lync Server 2013
- Una organización Microsoft 365 o Office 365
- Conectividad híbrida configurada entre el Skype Empresarial Server y Skype Empresarial Online o Microsoft Teams espacio empresarial
- Usuarios habilitados para realizar y recibir llamadas de red telefónica conmutada (RTC) al cliente y desde este


Si tiene un entorno diferente (por ejemplo, Skype for Business Edición de conector de nube), la implementación híbrida no está configurada o los usuarios no están habilitados para llamadas RTC, la matriz de compatibilidad será diferente.

## <a name="about-the-combinations-and-the-supportability-statement"></a>Acerca de las combinaciones y la declaración de compatibilidad

Un entorno Skype Empresarial híbrido con conectividad CON RTC proporciona flexibilidad sobre dónde se proporcionan los servicios de usuario y cómo se aprovisionan y administran las cuentas de usuario. Sin embargo, la abundancia de opciones podría crear algunas combinaciones no compatibles. En esta sección se explican las distintas combinaciones de creación de usuarios, seguidas de una instrucción de compatibilidad.

**Definiciones:**

- **Telefonía IP empresarial:** opción para proporcionar acceso a RTC a los usuarios con una cuenta de usuario Skype Empresarial local. El servidor de mediación Skype Empresarial local proporciona interconexión a RTC.
- **Conectividad de voz híbrida:** Opción para proporcionar acceso a RTC para los usuarios con Skype Empresarial cuenta en línea. El servidor de mediación Skype Empresarial local proporciona interconexión a RTC.
- **Enrutamiento directo:** Opción para proporcionar acceso a RTC a los usuarios con una cuenta de Skype Empresarial en línea, Microsoft Teams licencia con Microsoft Teams cliente. El SBC se conecta al proxy SIP en Microsoft 365 o Office 365 sin necesidad de ningún software local de Microsoft.

**El entorno admite las combinaciones siguientes:**

- **Escenario 1:** Cuenta de usuario en Skype Empresarial local y usará el cliente de Skype Empresarial con Telefonía IP empresarial
- **Escenario 2:** Cuenta de usuario en Skype para empresas en línea y usará el cliente de Skype Empresarial con conectividad de voz híbrida
- **Escenario 3:** Cuenta de usuario en Skype Empresarial en línea con licencia de Microsoft Teams y usará Teams cliente

### <a name="supportability-matrix"></a>Matriz de compatibilidad

|Objeto de usuario creado en|Proveedor de servicios Skype Empresarial del usuario|Cliente del usuario|Opción de voz|Compatible|
|---|---|---|---|---|
|AD local|Implementación local|Skype Empresarial|Telefonía IP empresarial|Sí|
|AD local|Online|Skype Empresarial|Conectividad de voz híbrida|Sí|
|AD local|Online|Microsoft Teams|Enrutamiento directo|Sí|
|**Combinaciones no admitidas**|||||
|Azure AD|Local/en línea|Skype Empresarial/Microsoft Teams|Telefonía IP empresarial/conectividad de voz híbrida/enrutamiento directo|No, el objeto de usuario DEBE crearse primero en AD local|
|AD local|Implementación local|Microsoft Teams|Telefonía IP empresarial/conectividad de voz híbrida/enrutamiento directo|No, Microsoft Teams cliente no es compatible con los Skype Empresarial locales|
|AD local|Online|Skype Empresarial|Enrutamiento directo|No, enrutamiento directo no es compatible con Skype Empresarial cliente|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Declaración de compatibilidad para el entorno híbrido con RTC

Para todos los usuarios, el objeto de usuario **debe** crearse en el AD local y sincronizarse con Azure AD con la herramienta de Conectar de Azure AD. **No se admite** la habilitación de usuarios para Teams/Skype Empresarial si el objeto de usuario se crea directamente en Azure AD en una configuración híbrida. Para los usuarios nuevos, como los nuevos empleados, que se habilitarán directamente para Teams, el usuario debe estar habilitado para Skype Empresarial mediante herramientas de administración locales Skype Empresarial. No **se admite** la creación de usuarios en Skype Empresarial en línea o Teams sin habilitarlos antes en un grupo local con Telefonía IP empresarial. Para obtener más información al respecto, consulte [Planear Sistema telefónico con conectividad CON RTC local en Skype Empresarial Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
