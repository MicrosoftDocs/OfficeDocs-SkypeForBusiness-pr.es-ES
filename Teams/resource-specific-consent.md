---
title: Consentimiento específico de recursos en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la configuración que necesita configurar para controlar si los propietarios de equipos de su organización pueden dar su consentimiento a las aplicaciones.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7b9379db7760fa8ef03440c24b93cb0223b4bee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117628"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimiento específico de recursos en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El consentimiento específico de los recursos en Microsoft Teams permite a los propietarios del equipo dar su consentimiento a las aplicaciones para obtener acceso a los datos del equipo. Algunos ejemplos de este acceso son la capacidad de leer mensajes de canal, crear y eliminar canales, así como crear y quitar pestañas de canal.

Como administrador, puede controlar si los propietarios de equipos de su organización pueden dar su consentimiento a través de la configuración que configure mediante el módulo de PowerShell de Azure Active Directory (Azure AD) o azure portal y el centro de administración de Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Establecer si los propietarios de equipos pueden dar consentimiento a las aplicaciones

Estas son las opciones de configuración que debe establecer para controlar si los propietarios de equipos pueden dar su consentimiento a las aplicaciones. Asegúrese de revisar todas las opciones de configuración siguientes.

### <a name="settings-in-azure-ad"></a>Configuración en Azure AD

Las dos opciones siguientes determinan si los propietarios de equipos pueden dar consentimiento a las aplicaciones.

> [!IMPORTANT]
> Cambiar cualquiera de estas opciones de configuración no afecta al acceso a los datos de las aplicaciones a las que ya se les ha concedido el consentimiento. Por ejemplo, si configura esta configuración para impedir que los propietarios de equipos den su consentimiento, estos cambios no quitan el acceso a datos que ya se ha concedido.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>La configuración "Los usuarios pueden consentir que las aplicaciones accedan a los datos de la empresa en su nombre".

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento a las aplicaciones en su nombre. Para permitir que los propietarios de equipos den su consentimiento, esta configuración debe establecerse en **Sí.** Para administrar esta configuración, haga lo siguiente:

1. En Azure Portal, vaya a Enterprise **configuración de** usuario de  >  **las aplicaciones.**
2. En **Enterprise ,** establezca Que los usuarios **puedan** dar su consentimiento para que las aplicaciones accedan a los datos de la compañía en su nombre **en No** o **Sí.**

También puede administrar esta configuración con PowerShell. Para obtener más información, vea [Configurar contenido de usuario en aplicaciones.](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>La configuración "EnableGroupSpecificConsent"

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa para los grupos que poseen. Esta configuración debe estar habilitada para que los propietarios del equipo den su consentimiento. Para obtener pasos sobre cómo administrar esta configuración mediante PowerShell, vea Configurar el consentimiento del propietario del grupo para que [las aplicaciones accedan a datos de grupo.](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configuración en el centro Microsoft Teams administración

Además de la configuración de Azure [AD,](manage-apps.md#manage-org-wide-app-settings) la configuración de la aplicación para toda [](manage-apps.md#allow-and-block-apps) la organización en [](teams-app-permission-policies.md) la página Administrar aplicaciones, si una aplicación está bloqueada o está permitida en la página Administrar aplicaciones, y la directiva de permisos de aplicación asignada al propietario del equipo determina si el propietario del equipo puede dar su consentimiento. [](manage-apps.md)

> [!IMPORTANT]
> Cambiar cualquiera de estas opciones de configuración no afecta al acceso a los datos de las aplicaciones a las que ya se les ha concedido el consentimiento. Por ejemplo, si deshabilita aplicaciones de terceros en toda la organización o si bloquea aplicaciones específicas para impedir que los propietarios del equipo concedan su consentimiento, estos cambios no quitan el acceso a datos que ya se ha concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>La configuración "Permitir aplicaciones de terceros" en la configuración de la aplicación para toda la organización

Esta configuración de aplicación para toda la organización controla si los usuarios de su organización pueden usar aplicaciones de terceros. Esta configuración debe estar activa para permitir que los propietarios de equipos den su consentimiento. Para administrar esta configuración, haga lo siguiente:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a Teams aplicaciones Administrar aplicaciones y, **a** continuación, haga clic en Configuración de aplicaciones para toda la  >   **organización.**
2. En **Aplicaciones de terceros,** desactiva o activa Permitir **aplicaciones de terceros.**

    ![Captura de pantalla de la configuración "Permitir aplicaciones de terceros Teams"](media/resource-specific-consent-org-wide-setting.png)

Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir o bloquear la aplicación en el nivel de organización

Al bloquear o permitir una [](manage-apps.md#allow-and-block-apps) aplicación en la página Administrar aplicaciones, esa aplicación está bloqueada o permitida para todos los usuarios de su organización. Los propietarios de equipos solo pueden dar su consentimiento a una aplicación si la aplicación está permitida. Para permitir o bloquear una aplicación en el nivel de organización, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la página Administrar aplicaciones, seleccione  la aplicación y, a continuación, haga clic en Bloquear para bloquearla o haga clic **en** Permitir para permitirla.

    ![Captura de pantalla de las aplicaciones bloqueadas en la configuración de toda la organización](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Directiva de permisos de aplicación asignada al propietario del equipo

Los propietarios de equipos solo pueden dar consentimiento a las aplicaciones que su directiva de permisos de aplicación les permite ejecutar. Para ver y administrar la directiva de permisos de aplicación asignada a un propietario del equipo, haga lo siguiente:

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Usuarios.**
2. Haga doble clic en el nombre para mostrar del propietario del equipo y, a continuación, haga clic en **Directivas.**
3. La directiva asignada al propietario del equipo se muestra en **Directiva de permisos de aplicación.**
    - Para asignar una directiva diferente, haga clic **en Editar** y, a continuación, seleccione la directiva que desea asignar.
    - Para editar la configuración de la directiva asignada al propietario del equipo, haga clic en el nombre de la directiva y, después, realice los cambios que desee.  

## <a name="uploading-custom-apps"></a>Cargar aplicaciones personalizadas

Al cargar una aplicación personalizada (también conocida como sideloading) que usa el consentimiento específico de los recursos, la aplicación debe venir del inquilino en el que se está instalando. En otras palabras, el registro de la aplicación de Azure AD debe ser de este inquilino. Los administradores globales están exentos de esta restricción y pueden cargar aplicaciones personalizadas desde cualquier espacio empresarial, ya sea directamente a un equipo (carga lateral) o al catálogo de aplicaciones de inquilino.

## <a name="related-topics"></a>Temas relacionados

- [Permisos de RSC disponibles](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Administrar las aplicaciones en el centro Microsoft Teams administración](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)