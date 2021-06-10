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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo configurar la autenticación moderna para Salas de Microsoft Teams
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117488"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticación en Salas de Microsoft Teams

La administración de cuentas Salas de Microsoft Teams dispositivos se administra en el nivel de aplicación. La aplicación se conecta a Microsoft Teams, Skype Empresarial y Exchange para obtener recursos para la cuenta de sala para habilitar las llamadas y las experiencias de reunión. El dispositivo se mantiene independiente de la cuenta para permitir capacidades siempre disponibles, escenarios de llamadas (para dispositivos configurados con un plan de llamadas) y mecanismos de bloqueo personalizados implementados en estos dispositivos. Esto significa que la autenticación para estos dispositivos se hace de una manera diferente a la de los dispositivos de usuario final.  

Se recomienda la autenticación moderna para todos los clientes que usan Salas de Microsoft Teams dispositivos con Microsoft 365 o Office 365. Si tiene una implementación local de un servidor Exchange o un [](/office365/enterprise/hybrid-modern-auth-overview) servidor Skype Empresarial, configure la autenticación moderna híbrida con Azure Active Directory (Azure AD) para habilitar el uso de la autenticación moderna.

La autenticación moderna es compatible Salas de Microsoft Teams versión 4.4.25.0 y posteriores.

## <a name="modern-authentication"></a>Autenticación moderna

Al usar la autenticación moderna con la aplicación Salas de Microsoft Teams, la biblioteca de autenticación de Active Directory (ADAL) se usa para conectarse Microsoft Teams, Exchange y Skype Empresarial. Un Salas de Microsoft Teams es un dispositivo compartido y realiza un reinicio nocturno para garantizar un buen funcionamiento y obtener actualizaciones críticas del sistema operativo, el controlador, el firmware o la aplicación. El mecanismo de [](/azure/active-directory/develop/v2-oauth-ropc) autenticación moderno usa el tipo de concesión de autorización de credenciales de contraseña del propietario del recurso en OAuth 2.0, que no requiere ninguna intervención del usuario. Esta es una de las diferencias clave entre el funcionamiento de la autenticación moderna para las cuentas de usuario y las cuentas de recursos que usa la aplicación Salas de Microsoft Teams usuario. Debido a esto, Salas de Microsoft Teams cuentas de recursos no deben configurarse para usar la autenticación multifactor (MFA), la autenticación de tarjeta inteligente o la autenticación basada en certificados de cliente (que están disponibles para los usuarios finales).

La otra diferencia clave entre cómo funciona la autenticación moderna en dispositivos de Salas de Microsoft Teams y dispositivos de usuario final es que no puede usar una cuenta de recursos para aplicar directivas de acceso condicional a nivel de dispositivo en Azure Active Directory y Endpoint Manager ya que la información del dispositivo no se pasa al usar este tipo de concesión. En su lugar, puede inscribir un dispositivo en Microsoft Endpoint Manager y aplicar directivas de cumplimiento mediante las instrucciones que se proporcionan en Administrar Teams salas de reuniones [con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar la autenticación moderna en un Salas de Microsoft Teams móvil

Para Salas de Microsoft Teams la autenticación moderna con Skype Empresarial y Exchange, habilite la configuración del cliente para la autenticación moderna en el Salas de Microsoft Teams dispositivo. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

> [!NOTE]
> Antes de habilitar la configuración del cliente para la autenticación moderna, asegúrese de que su entorno está configurado correctamente para usar la autenticación moderna.

### <a name="using-device-settings"></a>Usar la configuración del dispositivo

1. En el dispositivo Microsoft Team Rooms, vaya a **Más** (**...**).
    
2. Seleccione **Configuración** y, a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la **pestaña Cuenta,** active **Autenticación moderna** y, a continuación, **seleccione Guardar y salir.**

### <a name="using-the-xml-config-file"></a>Usar el archivo de configuración XML

En el SkypeSettings.xml, establezca el elemento XML de autenticación moderna en **Verdadero,** como se muestra a continuación.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar la configuración, vea Administrar una configuración Salas de Microsoft Teams consola de forma [remota con un archivo de configuración XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar el entorno para la autenticación moderna

Antes de empezar, asegúrese de comprender los modelos de identidad que debe usar con Office 365 y Azure AD. Puede encontrar más información en Office 365 y en [Azure Active Directory](/Office365/Enterprise/about-office-365-identity) identidad híbrida y sincronización de directorios para Microsoft 365 o [Office 365](/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar la autenticación moderna en Microsoft 365 o Office 365

Para activar la autenticación moderna para Exchange Online, vea [Habilitar la autenticación moderna en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Si usa Skype Empresarial Online, también debe asegurarse de que la autenticación moderna está activada para Skype Empresarial Online. Para obtener más información, [vea Skype Empresarial Online: Habilitar el espacio empresarial para la autenticación moderna.](https://aka.ms/SkypeModernAuth)

Le recomendamos que no quite las directivas de autenticación básicas para Exchange Online ni deshabilite la autenticación básica para el inquilino hasta que haya validado que los dispositivos Salas de Microsoft Teams pueden iniciar sesión correctamente con Exchange Online, Teams y Skype Empresarial Online.

Para obtener más información sobre cómo deshabilitar la autenticación básica en Exchange Online, vea [Deshabilitar la autenticación básica en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticación moderna híbrida

Para garantizar una autenticación correcta en su servidor de Exchange local o en un servidor Skype Empresarial, debe asegurarse de que la cuenta de recursos que se usa con Salas de Microsoft Teams está configurada para obtener autorización de Azure AD. 

Salas de Teams flujos de autenticación varían según la configuración de autenticación. Para los clientes que usan un dominio administrado, Salas de Teams credenciales de contraseña del propietario de recursos de [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) con Azure Active Directory. Sin embargo, para los clientes que usan un dominio federado, se usa la aserción del Flow SAML de [OAuth 2.0.](/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Es posible que su proveedor de identidades necesite configuraciones o configuraciones específicas para la integración con Azure Active Directory o Office 365. Póngase en contacto con su proveedor de identidades si necesita ayuda para configurar la autenticación con Salas de Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Requisitos previos específicos de Salas de Microsoft Teams

Los requisitos previos para habilitar la autenticación moderna en la topología híbrida se tratan en Información general sobre autenticación moderna híbrida y requisitos previos para usarlo con servidores locales Skype Empresarial y [Exchange híbridos.](/office365/enterprise/hybrid-modern-auth-overview) Se aplican todos los requisitos previos que se deba en el artículo.

Sin embargo, como Salas de Microsoft Teams [](https://tools.ietf.org/html/rfc6749#section-1.3.3) usa la autorización de credenciales de contraseña del propietario del recurso y las API de REST subyacentes para la autenticación moderna, las siguientes son diferencias importantes para tener en cuenta que son específicas de Salas de Microsoft Teams.

- Debe tener Exchange Server CU8 de 2016 o posterior, o Exchange Server 2019 CU1 o posterior.
- Debe tener Skype Empresarial Server 2015 CU5 o posterior, o Skype Empresarial Server 2019 o posterior.
- MFA no es compatible independientemente de la topología que tenga.
- Salas de Microsoft Teams no admite la falta de coincidencia de SIP y UPN. Debe crear una cuenta Salas de Microsoft Teams con el mismo UPN y SIP para que funcione.
- Si usa un proveedor de autenticación de terceros compatible con Azure AD, debe admitir un flujo de autenticación activo a través de WS-Trust.
- No use directivas de acceso condicional a nivel de dispositivo para una cuenta de recursos configurada con la aplicación. Al hacerlo, se producirán errores de inicio de sesión. En su lugar, inscriba un dispositivo en Microsoft Intune y aplique directivas de cumplimiento mediante las instrucciones publicadas en Administrar Teams salas de reuniones [con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar la autenticación moderna híbrida en Exchange Server, vea Cómo configurar Exchange Server local para [usar la autenticación moderna híbrida.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Configurar Skype Empresarial Server

Para habilitar la autenticación moderna híbrida con Skype Empresarial Server, vea Cómo configurar Skype Empresarial local para [usar la autenticación moderna híbrida.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Quitar o deshabilitar Skype Empresarial y Exchange

Si su configuración no permite la autenticación moderna híbrida o necesita quitar o deshabilitar la autenticación moderna híbrida para Exchange o Skype Empresarial, vea Quitar o deshabilitar la autenticación moderna híbrida de Skype Empresarial y [Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD

Puede configurar una cuenta de recursos que se usa Salas de Microsoft Teams para el acceso basado en ip/ubicación. Para obtener más información, vea [Acceso condicional: Bloquear el acceso por ubicación.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

No se admiten otras directivas de acceso condicional. Para obtener más información sobre el cumplimiento del dispositivo, [vea Administrar Teams salas de reuniones con Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)