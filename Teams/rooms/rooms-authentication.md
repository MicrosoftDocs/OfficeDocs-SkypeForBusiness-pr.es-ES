---
title: Autenticación en salas de Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: Obtenga información sobre cómo configurar la autenticación moderna para salas de Microsoft Teams
ms.openlocfilehash: f44fe0e66e5dd219606b2ceaa3860e01164ccfa4
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666262"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Autenticación en salas de Microsoft Teams

Administración de cuentas para los dispositivos de salas de Microsoft Teams se maneja en el nivel de aplicación. La aplicación se conecta a Microsoft Teams, Skype empresarial y Exchange para obtener los recursos de la cuenta de la sala para habilitar las experiencias de llamada y de reunión. El dispositivo se mantiene como independiente de la cuenta para permitir capacidades siempre activadas, escenarios de llamadas (para dispositivos configurados con un plan de llamadas) y mecanismos de bloqueo personalizados implementados en estos dispositivos. Esto significa que la autenticación para estos dispositivos se produce de forma diferente a la de los dispositivos de usuario final.  

Se recomienda la autenticación moderna para todos los clientes que usen dispositivos de salas de Microsoft Teams con Microsoft 365 u Office 365. Si dispone de una implementación local de Exchange Server o de Skype empresarial Server, configure la [autenticación moderna híbrida](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) con Azure Active Directory (Azure ad) para habilitar el uso de la autenticación moderna.

La autenticación moderna es compatible con las salas de Microsoft Teams versión 4.4.25.0 y posteriores.

## <a name="modern-authentication"></a>Autenticación moderna

Al usar la autenticación moderna con la aplicación Microsoft Teams Rooms, la biblioteca de autenticación de Active Directory (ADAL) se usa para conectarse a Microsoft Teams, Exchange y Skype empresarial. Un dispositivo de salas de Microsoft Teams es un dispositivo compartido y realiza un reinicio nocturno para garantizar un funcionamiento sin problemas y para obtener actualizaciones críticas del sistema operativo, el controlador, el firmware o la aplicación. El mecanismo de autenticación moderna usa el tipo de concesión de autorización [credenciales](https://tools.ietf.org/html/rfc6749#section-1.3.3) de la contraseña del propietario del recurso en OAuth 2,0, que no requiere ninguna intervención por parte del usuario. Esta es una de las diferencias clave entre el funcionamiento de la autenticación moderna para las cuentas de usuario y las cuentas de recursos que se usan en la aplicación salas de Microsoft Teams. Por eso, las salas de las salas de Microsoft Teams no se deben configurar para usar la autenticación multifactor (MFA), la autenticación de tarjetas inteligentes o la autenticación basada en certificados de cliente (que están disponibles para los usuarios finales).

La otra diferencia clave entre el funcionamiento de la autenticación moderna en los dispositivos de las salas de Microsoft Teams y los dispositivos de usuario final es que no se puede usar una cuenta de recursos para aplicar directivas de acceso condicional en el nivel de dispositivo, como "requerir que el dispositivo se marque como conforme" o "requerir un dispositivo Unido de Azure AD", etc. Esto se debe a que los conceptos de nivel de dispositivo no se aplican a la autenticación moderna cuando se usan en el nivel de aplicación. En su lugar, puede inscribir un dispositivo en Microsoft Intune y aplicar directivas de cumplimiento con las instrucciones proporcionadas en [administrar salas de reuniones de Teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Habilitar la autenticación moderna en un dispositivo de salas de Microsoft Teams

Para que las salas de Microsoft Teams usen la autenticación moderna con Skype empresarial y Exchange, habilite la configuración del cliente para la autenticación moderna en el dispositivo de salas de Microsoft Teams. Puede hacerlo en la configuración del dispositivo o en el archivo de configuración XML.

> [!NOTE]
> Antes de habilitar la configuración del cliente para la autenticación moderna, asegúrese de que su entorno está configurado correctamente para usar la autenticación moderna.

### <a name="using-device-settings"></a>Usar la configuración de dispositivos

1. En el dispositivo de Microsoft Team Rooms, vaya a **más** (**...**).
    
2. Seleccione **configuración**y, a continuación, escriba el nombre de usuario y la contraseña del administrador del dispositivo.
3. Vaya a la pestaña **cuenta** , Active **autenticación moderna**y, a continuación, seleccione **Guardar y salir**.

### <a name="using-the-xml-config-file"></a>Usar el archivo de configuración XML

En el archivo SkypeSettings. XML, establezca el elemento XML de autenticación moderna en **true**, como se indica a continuación.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Para aplicar la configuración, consulte [administrar de forma remota la configuración de una consola de salas de Microsoft Teams con un archivo de configuración XML](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Preparar el entorno para la autenticación moderna

Antes de empezar, asegúrese de que comprende los modelos de identidad que se deben usar con Office 365 y Azure AD. Puede encontrar más información en los [modelos de identidad de Office 365 y Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) , y en la [identidad híbrida y en la sincronización de directorios para Microsoft 365 u Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Habilitar la autenticación moderna en Microsoft 365 u Office 365

Para activar la autenticación moderna para Exchange Online, consulte [Habilitar la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Si usa Skype empresarial online, también debe asegurarse de que la autenticación moderna está activada en Skype empresarial online. Para obtener más información, consulte [Skype empresarial online: habilitar su espacio empresarial para la autenticación moderna](https://aka.ms/SkypeModernAuth).

Le recomendamos que no quite las directivas básicas de autenticación para Exchange online o que deshabilite la autenticación básica de su espacio empresarial antes de que haya validado que los dispositivos de salas de Microsoft Teams pueden iniciar sesión en Exchange Online y Teams o Skype empresarial online correctamente cuando la configuración de autenticación moderna está activada y que no hay ningún dispositivo que aún esté configurado para usar la autenticación básica.

Para obtener más información sobre cómo deshabilitar la autenticación básica en Exchange Online, vea [deshabilitar la autenticación básica en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Autenticación moderna híbrida

Para garantizar una autenticación correcta en su servidor de Exchange local o en Skype empresarial Server, debe asegurarse de que la cuenta de recursos que se usa con las salas de Microsoft Teams está configurada para obtener autorización de Azure AD. Para obtener más información sobre las identidades híbridas y los métodos que funcionan con su organización, lea los siguientes temas: 

- [¿Qué es la sincronización de hash de contraseña?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [¿Qué es la autenticación por paso?](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [¿Qué es la Federación?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Requisitos previos específicos de las salas de Microsoft Teams

Los requisitos previos para habilitar la autenticación moderna en su topología híbrida se tratan en la [información general de la autenticación moderna híbrida y los requisitos previos para usarlo con Skype empresarial y los servidores de Exchange locales](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Se aplican todos los requisitos previos descritos en el artículo.

Sin embargo, debido a que las salas de Microsoft Teams usan la autorización de [credenciales de contraseña de propietario de recursos](https://tools.ietf.org/html/rfc6749#section-1.3.3) y las API de REST subyacentes para la autenticación moderna, las siguientes son importantes diferencias que debe tener en cuenta que son específicas de las salas de Microsoft Teams.

- Debe tener Exchange Server 2016 CU8 o posterior, o Exchange Server 2019 CU1 o posterior.
- Debe tener Skype empresarial Server 2015 CU5 o posterior, o Skype empresarial Server 2019 o posterior.
- MFA no es compatible con independencia de la topología que tenga.
- Si usa un proveedor de autenticación de terceros admitido por Azure AD, debe admitir OAuth y usar la autorización de credenciales de la contraseña del propietario del recurso.
- No use directivas de acceso condicional a nivel de dispositivo para una cuenta de recursos configurada con la aplicación. Si lo hace, se producirán errores de inicio de sesión. En su lugar, inscriba un dispositivo en Microsoft Intune y aplique directivas de cumplimiento mediante las instrucciones publicadas en [administrar salas de reuniones de Teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

### <a name="configure-exchange-server"></a>Configurar Exchange Server

Para habilitar la autenticación moderna híbrida en Exchange Server, consulte [Cómo configurar Exchange Server local para usar la autenticación moderna híbrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Configurar Skype empresarial Server

Para habilitar la autenticación moderna híbrida con Skype empresarial Server, consulte [Cómo configurar Skype empresarial local para usar la autenticación moderna híbrida](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Quitar o deshabilitar Skype empresarial y Exchange

Si su configuración no permite la autenticación moderna híbrida o si necesita quitar o deshabilitar la autenticación moderna híbrida para Exchange o Skype empresarial, vea [quitar o deshabilitar la autenticación moderna híbrida de Skype empresarial y Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Acceso condicional de Azure AD

Puede configurar una cuenta de recursos que se use con salas de Microsoft Teams para el acceso basado en IP/ubicación. Para obtener más información, consulte [acceso condicional: bloquear el acceso por ubicación](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

No se admiten otras directivas de acceso condicional. Para obtener más información sobre el cumplimiento de dispositivos, consulte [administrar salas de reuniones de Teams con Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).  
