---
title: Consentimiento específico del recurso en Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre los ajustes que necesita configurar para controlar si los propietarios de equipos de su organización pueden dar su consentimiento a las aplicaciones.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b506352052924b8394cbdfc712ce96750b96523
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67298899"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimiento específico del recurso en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El consentimiento específico del recurso en Microsoft Teams permite a los propietarios del equipo dar su consentimiento a las aplicaciones para que accedan a los datos del equipo. Entre los ejemplos de acceso se incluye la capacidad de leer los mensajes del canal, crear y eliminar canales, y crear y quitar pestañas del canal.

Como administrador, puede controlar si los propietarios del equipo de la organización pueden dar su consentimiento a través de los ajustes que configure mediante el módulo de PowerShell de Azure Active Directory (Azure AD) o el Azure Portal y el Centro de administración de Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Establecer si los propietarios del equipo pueden dar su consentimiento a las aplicaciones

Esta es la configuración que debe establecer para controlar si los propietarios del equipo pueden dar su consentimiento a las aplicaciones. Asegúrese de revisar todas las opciones de configuración siguientes.

### <a name="settings-in-azure-ad"></a>Configuración en Azure AD

Las dos opciones siguientes determinan si los propietarios del equipo pueden dar su consentimiento a las aplicaciones.

> [!IMPORTANT]
> Los cambios en cualquiera de estas opciones de configuración no afectarán el acceso a los datos de las aplicaciones a las que ya se haya concedido consentimiento. Por ejemplo, si configura estas opciones para evitar que los propietarios del equipo den su consentimiento, estos cambios no quitarán el acceso a datos que ya se haya concedido.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Configuración de “Los usuarios pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa en su nombre”

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento a las aplicaciones en su nombre. Para permitir que los propietarios del equipo den su consentimiento, esta configuración debe establecerse en **Sí**. Para administrar esta configuración, haga lo siguiente:

1. En el Azure Portal, vaya a **Aplicaciones empresariales** > **Configuración del usuario**.
2. En **Aplicaciones empresariales**, establezca **Los usuarios pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa en su nombre** en **No** o **Sí**.

También puede administrar esta configuración mediante PowerShell. Para obtener más información, consulte [Configurar consentimiento del usuario para las aplicaciones](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Configuración de “EnableGroupSpecificConsent”

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa de los grupos que poseen. Esta configuración debe estar habilitada para que los propietarios del equipo puedan dar su consentimiento. Para conocer los pasos para administrar esta configuración mediante PowerShell, consulte [Configurar el consentimiento del propietario del grupo para que las aplicaciones accedan a los datos del grupo](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Otras opciones de configuración en el Centro de administración de Microsoft Teams

Además de la configuración de Azure AD, las opciones [Configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings) en la página [Administrar aplicaciones](manage-apps.md), si una aplicación está bloqueada o permitida en la página [Administrar aplicaciones](manage-apps.md#allow-and-block-apps) y la [Directiva de permisos de aplicación](teams-app-permission-policies.md) asignada al propietario del equipo son las que determinan si un propietario del equipo puede dar su consentimiento.

> [!IMPORTANT]
> Los cambios en cualquiera de estas opciones de configuración no afectarán el acceso a los datos de las aplicaciones a las que ya se haya concedido consentimiento. Por ejemplo, si deshabilita aplicaciones de terceros en toda la organización o si bloquea aplicaciones específicas para impedir que los propietarios del equipo den su consentimiento, estos cambios no quitarán el acceso a los datos que ya se haya concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Ajuste “Permitir aplicaciones de terceros” en la configuración de aplicaciones para toda la organización

Esta configuración controla si los usuarios de la organización pueden usar aplicaciones de terceros. Esta configuración debe estar activada para permitir que los propietarios del equipo den su consentimiento. Para administrar esta configuración, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones** y, luego, haga clic en **Configuración de aplicaciones para toda la organización**.
2. En **Aplicaciones de terceros**, desactive o active **Permitir aplicaciones de terceros**.

    ![Recorte de pantalla del ajuste “Permitir aplicaciones de terceros en Teams”](media/resource-specific-consent-org-wide-setting.png)

Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir o bloquear la aplicación en el nivel de organización

Cuando se bloquea o permite una aplicación en la página [Administrar aplicaciones](manage-apps.md#allow-and-block-apps), la aplicación se bloquea o se permite para todos los usuarios de la organización. Los propietarios del equipo solo pueden dar su consentimiento a una aplicación si dicha aplicación está permitida. Para permitir o bloquear una aplicación en el nivel de organización, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la página Administrar aplicaciones, seleccione la aplicación y, a continuación, haga clic en **Bloquear** para bloquearla o haga clic en **Permitir** para permitirla.

    ![Recorte de pantalla de las aplicaciones bloqueadas en la configuración de toda la organización.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Directiva de permisos de aplicación asignada al propietario del equipo

Los propietarios del equipo solo pueden dar su consentimiento a las aplicaciones que su directiva de permisos de aplicación les permita ejecutar. Para ver y administrar la directiva de permisos de aplicación asignada a un propietario de equipo, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios**.
2. Haga doble clic en el nombre para mostrar del propietario del equipo y, a continuación, haga clic en **Directivas**.
3. La directiva asignada al propietario del equipo aparece en **Directiva de permisos de aplicación**.
    - Para asignar una directiva diferente, haga clic en **Editar** y, a continuación, seleccione la directiva que desea asignar.
    - Para editar la configuración de la directiva asignada al propietario del equipo, haga clic en el nombre de la directiva y, a continuación, realice los cambios que desee.  

## <a name="uploading-custom-apps"></a>Cargar aplicaciones personalizadas

Al cargar una aplicación personalizada (también conocida como instalación de prueba) que usa el consentimiento específico del recurso, la aplicación debe proceder del inquilino en el que se está instalando. En otras palabras, el registro de la aplicación Azure AD debe ser de este inquilino. Los administradores globales están exentos de esta restricción y pueden cargar aplicaciones personalizadas desde cualquier inquilino, ya sea directamente en un equipo (instalación de prueba) o en el catálogo de aplicaciones del inquilino.

## <a name="related-topics"></a>Temas relacionados

- [Permisos RSC disponibles](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Administrar aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
