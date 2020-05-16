---
title: Consentimiento específico de recursos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga más información sobre la configuración que necesita configurar para controlar si los propietarios de los equipos de su organización pueden dar su consentimiento a las aplicaciones.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256598"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimiento específico de recursos en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El consentimiento específico de recursos de Microsoft Teams permite que los propietarios del equipo otorguen consentimiento a las aplicaciones para acceder a los datos del equipo. Algunos ejemplos de este tipo de acceso son la capacidad de leer mensajes de canal, crear y eliminar canales, y crear y quitar pestañas de canal.

Como administrador, puede controlar si los propietarios del equipo de su organización pueden dar su consentimiento mediante la configuración que configure mediante el módulo de PowerShell Azure Active Directory (Azure AD) o el portal de Azure y el centro de administración de Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Establecer si los propietarios del equipo pueden dar su consentimiento a las aplicaciones

A continuación se muestran las opciones de configuración que debe establecer para que los propietarios del equipo puedan dar su consentimiento a las aplicaciones. Asegúrese de revisar todas las opciones siguientes.

### <a name="settings-in-azure-ad"></a>Configuración en Azure AD

Las dos opciones siguientes determinan si los propietarios del equipo pueden dar su consentimiento a las aplicaciones.

> [!IMPORTANT]
> Cambiar cualquiera de estos valores de configuración no afecta al acceso a los datos de las aplicaciones a las que ya se ha otorgado consentimiento. Por ejemplo, si configura estas opciones para evitar que los propietarios del equipo den su consentimiento, estos cambios no quitarán el acceso a datos que ya se haya otorgado.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Configuración de la opción "los usuarios pueden conceder acceso a los datos de la compañía en su nombre"

Esta configuración controla si los usuarios de su organización pueden dar consentimiento a las aplicaciones en su nombre. Para permitir a los propietarios del equipo dar su consentimiento, esta configuración debe estar establecida en **sí**. Para administrar esta configuración, haga lo siguiente:

1. En el portal de Azure, vaya a configuración de usuario de **aplicaciones empresariales**  >  **User settings**.
2. En **aplicaciones empresariales**, establezca **los usuarios pueden aceptar las aplicaciones que tienen acceso a los datos de la empresa en su nombre** a **no** o **sí**.

También puede administrar esta configuración con PowerShell. Para obtener más información, vea [configurar el contenido de usuario para aplicaciones](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>La opción "EnableGroupSpecificConsent"

Esta configuración controla si los usuarios de su organización pueden autorizar a las aplicaciones que acceden a los datos de la compañía para los grupos de su propiedad. Esta configuración debe estar habilitada para que los propietarios del equipo otorguen el consentimiento. Para conocer los pasos sobre cómo administrar esta configuración con PowerShell, consulte [configurar el consentimiento del propietario del grupo para las aplicaciones que acceden](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)a los datos del grupo.

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configuración en el centro de administración de Microsoft Teams

Además de la configuración en Azure AD, la configuración de la [aplicación de toda la organización](manage-apps.md#manage-org-wide-app-settings) en la página [Administrar aplicaciones](manage-apps.md) , independientemente de si una aplicación está bloqueada o permitida en la página de [Administración de aplicaciones](manage-apps.md#allow-and-block-apps) , y la Directiva de permisos de la [aplicación](teams-app-permission-policies.md) asignada al propietario del equipo determinar si el propietario del equipo puede dar su consentimiento.

> [!IMPORTANT]
> Cambiar cualquiera de estos valores de configuración no afecta al acceso a los datos de las aplicaciones a las que ya se ha otorgado consentimiento. Por ejemplo, si deshabilita aplicaciones de terceros para toda la organización o bloquea determinadas aplicaciones para evitar que los propietarios del equipo den su consentimiento, estos cambios no quitan el acceso a datos que ya se ha otorgado.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Configuración "permitir aplicaciones de terceros" en la configuración de la aplicación de toda la organización

Esta configuración de aplicación de toda la organización controla si los usuarios de su organización pueden usar aplicaciones de terceros. Esta configuración debe estar activada para permitir a los propietarios del equipo dar su consentimiento. Para administrar esta configuración, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**y, a continuación, haga clic en **configuración de aplicaciones en toda la organización**.
2. En **aplicaciones de terceros**, desactive o desactive **permitir aplicaciones de terceros**.

    ![Captura de pantalla de la opción "permitir aplicaciones de terceros en Teams"](media/resource-specific-consent-org-wide-setting.png)

Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir o bloquear la aplicación en el nivel de la organización

Cuando bloquea o permite una aplicación en la página [Administrar aplicaciones](manage-apps.md#allow-and-block-apps) , la aplicación está bloqueada o está permitida para todos los usuarios de su organización. Los propietarios del equipo solo pueden dar su consentimiento a una aplicación si la aplicación está permitida. Para permitir o bloquear una aplicación en el nivel de la organización, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.
2. En la página Administrar aplicaciones, seleccione la aplicación y, a continuación, haga clic en **bloquear** para bloquearlo o haga clic en **permitir** para permitirlo.

    ![Captura de pantalla de las aplicaciones bloqueadas en la configuración de toda la organización](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Directiva de permisos de aplicación asignada al propietario del equipo

Los propietarios de equipo solo pueden dar consentimiento a las aplicaciones que la Directiva de permisos de la aplicación permita que se ejecuten. Para ver y administrar la Directiva de permisos de la aplicación que está asignada a un propietario del equipo, haga lo siguiente:

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **usuarios**.
2. Haga doble clic en el nombre para mostrar del propietario del equipo y, a continuación, haga clic en **directivas**.
3. La directiva asignada al propietario del equipo se muestra en **Directiva de permisos de aplicaciones**.
    - Para asignar una directiva diferente, haga clic en **Editar**y, a continuación, seleccione la Directiva que desea asignar.
    - Para editar la configuración de la Directiva que está asignada al propietario del equipo, haga clic en el nombre de la Directiva y, a continuación, realice los cambios que desee.  

## <a name="uploading-custom-apps"></a>Cargando aplicaciones personalizadas

Al cargar una aplicación personalizada (también conocida como instalación de prueba) que usa el consentimiento específico de recursos, la aplicación debe proceder del inquilino en el que se está instalando. En otras palabras, el registro de la aplicación Azure AD debe ser de este inquilino. Los administradores globales están exentos de esta restricción y pueden cargar aplicaciones personalizadas desde cualquier inquilino, ya sea directamente a un equipo (de descarga de prueba) o al catálogo de aplicaciones de inquilino.

## <a name="related-topics"></a>Temas relacionados

- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
