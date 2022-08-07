---
title: Autenticación en Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Obtenga información sobre cómo configurar la autenticación moderna para Salas de Microsoft Teams
ms.openlocfilehash: ef576c2d785f3e3fb16afd42e6136b607711c28b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268245"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticación en Salas de Microsoft Teams

La administración de cuentas para Salas de Microsoft Teams se controla en el nivel de aplicación. La aplicación se conecta a Microsoft Teams, Skype for Business y Exchange para obtener recursos para la cuenta de recursos con el fin de habilitar las experiencias de llamada y reunión. Salas de Teams usa una cuenta de recursos dedicada para permitir funcionalidades siempre activadas, escenarios de llamadas (para dispositivos configurados con un plan de llamadas) y mecanismos de bloqueo personalizados. Esto significa que la autenticación para Salas de Teams se realiza de una manera diferente a la de los dispositivos del usuario final.  

Se recomienda la autenticación moderna para todos los clientes que usen Salas de Microsoft Teams con Microsoft 365 o Office 365. Si tiene una implementación local de Exchange Server o Skype for Business servidor, configure la [autenticación moderna híbrida](/office365/enterprise/hybrid-modern-auth-overview) con Azure Active Directory (Azure AD) para habilitar el uso de la autenticación moderna.

La autenticación moderna se admite en Salas de Microsoft Teams versión 4.4.25.0 y posteriores.

## <a name="modern-authentication"></a>Autenticación moderna

Al usar la autenticación moderna con la aplicación de Salas de Microsoft Teams, se usa la Biblioteca de autenticación de Active Directory (ADAL) para conectarse a Microsoft Teams, Exchange y Skype for Business. El mecanismo de autenticación moderno usa el tipo de autorización de autorización de [las credenciales del propietario del recurso](/azure/active-directory/develop/v2-oauth-ropc) en OAuth 2.0, que no requiere la intervención del usuario. Esta es una de las diferencias clave entre el funcionamiento de la autenticación moderna para las cuentas de usuario y las cuentas de recursos usadas por Salas de Microsoft Teams. Por este motivo, Salas de Microsoft Teams cuentas de recursos no deben configurarse para usar la autenticación multifactor (MFA), la autenticación de tarjetas inteligentes o la autenticación basada en certificados de cliente (que están disponibles para los usuarios finales).

La otra diferencia clave entre cómo funciona la autenticación moderna en Salas de Microsoft Teams y dispositivos de usuario final es que no puede usar una cuenta de recursos para aplicar directivas de acceso condicional a nivel de dispositivo en Azure Active Directory y Endpoint Manager como no se pasa la información del dispositivo al usar este tipo de concesión. En su lugar, puede inscribir un dispositivo en Microsoft Endpoint Manager y aplicar directivas de cumplimiento. Vea [Acceso condicional y cumplimiento de Intune para obtener Salas de Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obtener más información.

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Habilitar la autenticación moderna en Salas de Microsoft Teams

Para Salas de Microsoft Teams usar la autenticación moderna con Skype for Business y Exchange, habilite la configuración del lado cliente para la autenticación moderna en Salas de Microsoft Teams. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

> [!NOTE]
> Antes de habilitar la configuración del lado cliente para la autenticación moderna, asegúrese de que su entorno está configurado correctamente para usar la autenticación moderna.

### <a name="using-device-settings"></a>Uso de la configuración del dispositivo

1. En Salas de Microsoft Teams, vaya a **Más** (**...**).
    
2. Selecciona **Configuración** y, a continuación, escribe el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la pestaña **Cuenta** , active autenticación **moderna** y, a continuación, seleccione **Guardar y salir**.

### <a name="using-the-xml-config-file"></a>Usar el archivo de configuración XML

En el archivo de SkypeSettings.xml, establezca el elemento XML de autenticación moderna en **True**, como se indica a continuación.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar la configuración, consulte [Administrar una configuración de la consola de Salas de Microsoft Teams de forma remota con un archivo de configuración XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar el entorno para la autenticación moderna

Antes de empezar, asegúrese de comprender los modelos de identidad que se usan con Office 365 y Azure AD. Puede encontrar más información en [Office 365 modelos de identidad y Azure Active Directory](/Office365/Enterprise/about-office-365-identity) y en [Identidad híbrida y sincronización de directorios para Microsoft 365 o Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar la autenticación moderna en Microsoft 365 o Office 365

Para activar la autenticación moderna para Exchange Online, vea [Habilitar la autenticación moderna en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

Le recomendamos que no quite directivas de autenticación básicas para Exchange Online ni deshabilite la autenticación básica para su inquilino hasta que haya validado que Salas de Microsoft Teams dispositivos pueden iniciar sesión correctamente con Exchange Online y Teams.

Para obtener más información sobre cómo deshabilitar la autenticación básica en Exchange Online, vea [Deshabilitar la autenticación básica en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticación moderna híbrida

Para garantizar una autenticación correcta en su servidor local de Exchange y/o Skype for Business servidor, debe asegurarse de que la cuenta de recursos que se usa con Salas de Microsoft Teams está configurada para obtener autorización de Azure AD.

Salas de Teams los flujos de autenticación varían según la configuración de autenticación. Para los clientes que usan un dominio administrado, Salas de Teams usa [credenciales de contraseña de propietario de recursos de OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Sin embargo, para los clientes que usan un dominio federado, se usa [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) .

> [!NOTE]
> Es posible que su proveedor de identidades necesite configuraciones o configuraciones específicas para la integración con Azure Active Directory o Office 365. Póngase en contacto con su proveedor de identidades si necesita ayuda para configurar la autenticación con Salas de Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Requisitos previos específicos de Salas de Microsoft Teams

Los requisitos previos para habilitar la autenticación moderna en la topología híbrida se tratan en [Información general sobre la autenticación moderna híbrida y requisitos previos para usarlo con Skype for Business locales y servidores de Exchange](/office365/enterprise/hybrid-modern-auth-overview). Se aplican todos los requisitos previos descritos en el artículo.

Sin embargo, como Salas de Microsoft Teams usa la autorización de [credenciales de contraseña del propietario del recurso](https://tools.ietf.org/html/rfc6749#section-1.3.3) y las API rest subyacentes para la autenticación moderna, a continuación se muestran diferencias importantes que debe tener en cuenta para Salas de Microsoft Teams.

- Usted debe tener Exchange Server 2016 CU8 o posterior, o Exchange Server 2019 CU1 o posterior.
- Usted debe tener Skype Empresarial Server 2015 CU5 o posterior, o Skype Empresarial Server 2019 o posterior.
- La MFA no es compatible independientemente de la topología que tenga.
- Salas de Microsoft Teams no admite la falta de coincidencia entre SIP y UPN. Debe crear una cuenta de Salas de Microsoft Teams con el mismo UPN y SIP para que funcione.
- Si usa un proveedor de autenticación de terceros que sea compatible con Azure AD, este debe admitir un flujo de autenticación activo a través de WS-Trust.
- No use directivas de acceso condicional a nivel de dispositivo para una cuenta de recursos configurada con la aplicación. Si lo hace, se producirán errores de inicio de sesión. En su lugar, inscriba un dispositivo en Microsoft Intune y aplique directivas de cumplimiento. Vea [Acceso condicional y cumplimiento de Intune para obtener Salas de Microsoft Teams](conditional-access-and-compliance-for-devices.md) para obtener más información.

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar la autenticación moderna híbrida en Exchange Server, consulte [Cómo configurar Exchange Server local para usar la autenticación moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar Skype Empresarial Server

Para habilitar la autenticación moderna híbrida con Skype Empresarial Server, consulte [Cómo configurar Skype for Business local para usar la autenticación moderna híbrida](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Quitar o deshabilitar Skype for Business y Exchange

Si su configuración no permite la autenticación moderna híbrida o necesita quitar o deshabilitar la autenticación moderna híbrida para Exchange o Skype for Business, consulte [Quitar o deshabilitar la autenticación moderna híbrida de Skype for Business y Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD

Puede configurar una cuenta de recursos que se usa con Salas de Microsoft Teams para el acceso basado en IP/ubicación. Para obtener más información, vea [Acceso condicional: Bloquear el acceso por ubicación](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Para obtener más información sobre el cumplimiento de dispositivos, vea [Acceso condicional admitido y directivas de cumplimiento de Intune para Salas de Microsoft Teams](supported-ca-and-compliance-policies.md).
