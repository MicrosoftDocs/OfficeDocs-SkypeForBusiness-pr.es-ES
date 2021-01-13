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
description: Obtenga información sobre las opciones que necesita configurar para controlar si los propietarios de equipos de su organización pueden dar su consentimiento para las aplicaciones.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815680"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimiento específico de recursos en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El consentimiento específico de los recursos en Microsoft Teams permite que los propietarios de equipos den su consentimiento a las aplicaciones para acceder a los datos del equipo. Algunos ejemplos de este tipo de acceso son la posibilidad de leer mensajes del canal, crear y eliminar canales, así como de crear y quitar fichas de canal.

Como administrador, puede controlar si los propietarios de los equipos de su organización pueden dar su consentimiento mediante las opciones de configuración que configure mediante el módulo PowerShell de Azure Active Directory (Azure AD) o el Portal de Azure y el Centro de administración de Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Establecer si los propietarios de equipos pueden dar su consentimiento a las aplicaciones

Estas son las opciones de configuración que debe establecer para controlar si los propietarios de equipos pueden dar su consentimiento a las aplicaciones. Asegúrese de revisar todos los ajustes siguientes.

### <a name="settings-in-azure-ad"></a>Configuración de Azure AD

Las dos opciones siguientes determinan si los propietarios del equipo pueden dar consentimiento a las aplicaciones.

> [!IMPORTANT]
> El cambio de cualquiera de estas opciones de configuración no afecta al acceso a datos para aplicaciones que ya tienen el consentimiento concedido. Por ejemplo, si configura estas opciones para evitar que los propietarios del equipo concedan su consentimiento, estos cambios no quitan el acceso a los datos ya concedidos.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>La configuración "Los usuarios pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa en su nombre".

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento para las aplicaciones en su nombre. Para permitir que los propietarios del equipo puedan dar su consentimiento, esta configuración debe establecerse en **Sí.** Para administrar esta configuración, haga lo siguiente:

1. En el Portal de Azure, vaya a **Configuración de usuario de aplicaciones**  >  **empresariales.**
2. En **Aplicaciones empresariales,** establezca **que los usuarios puedan dar** su consentimiento para que las aplicaciones accedan a los datos de la empresa en su nombre en **No** o **Sí.**

También puede administrar esta configuración con PowerShell. Para obtener más información, vea [Configurar contenido de usuario en aplicaciones.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>La configuración "EnableGroupSpecificConsent"

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento para que las aplicaciones accedan a los datos de la compañía de los grupos de los que son propietarios. Esta configuración debe estar habilitada para que los propietarios del equipo puedan dar su consentimiento. Para ver los pasos sobre cómo administrar esta configuración con PowerShell, vea El consentimiento del propietario del grupo para que las aplicaciones accedan a los [datos del grupo.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configuración en el Centro de administración de Microsoft Teams

Además de la configuración de Azure [AD,](manage-apps.md#manage-org-wide-app-settings) la configuración de aplicaciones para toda la [](manage-apps.md#allow-and-block-apps) organización en la [](teams-app-permission-policies.md) página Administrar aplicaciones determina si una aplicación está bloqueada o está permitida en la página Administrar aplicaciones, y la directiva de permisos de aplicación asignada al propietario del equipo determina si el propietario del equipo puede dar su consentimiento. [](manage-apps.md)

> [!IMPORTANT]
> El cambio de cualquiera de estas opciones de configuración no afecta al acceso a datos para aplicaciones que ya tienen el consentimiento concedido. Por ejemplo, si deshabilita aplicaciones de terceros en toda la organización o bloquea aplicaciones específicas para impedir que los propietarios del equipo concedan su consentimiento, estos cambios no quitan el acceso a los datos ya concedidos.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>La configuración "Permitir aplicaciones de terceros" en la configuración de aplicaciones para toda la organización

Esta configuración de aplicaciones para toda la organización controla si los usuarios de su organización pueden usar aplicaciones de terceros. Esta configuración debe estar activa para permitir que los propietarios de equipos puedan dar su consentimiento. Para administrar esta configuración, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Administrar aplicaciones de **Teams** y, a continuación, haga clic en Configuración  >  de aplicaciones para toda **la organización.**
2. En **Aplicaciones de terceros,** desactiva o activa Permitir **aplicaciones de terceros.**

    ![Captura de pantalla de la configuración "Permitir aplicaciones de terceros en Teams"](media/resource-specific-consent-org-wide-setting.png)

Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir o bloquear la aplicación en el nivel de organización

Al bloquear o permitir una [](manage-apps.md#allow-and-block-apps) aplicación en la página Administrar aplicaciones, esa aplicación se bloquea o se permite para todos los usuarios de la organización. Los propietarios de equipos solo pueden dar su consentimiento a una aplicación si se permite. Para permitir o bloquear una aplicación en el nivel de la organización, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones de Teams.**  >  
2. En la página Administrar aplicaciones, seleccione  la aplicación y, a continuación, haga clic en Bloquear para bloquearla o haga clic en Permitir **para** permitirla.

    ![Captura de pantalla de las aplicaciones bloqueadas en la configuración de toda la organización](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Directiva de permisos de aplicación asignada al propietario del equipo

Los propietarios del equipo solo pueden dar su consentimiento a las aplicaciones que la directiva de permisos de aplicación les permita ejecutar. Para ver y administrar la directiva de permisos de aplicación que se asigna a un propietario del equipo, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios.**
2. Haga doble clic en el nombre para mostrar del propietario del equipo y, a continuación, haga clic en **Directivas.**
3. La directiva asignada al propietario del equipo se enumera en la directiva **de permisos de aplicación.**
    - Para asignar una directiva diferente, haga **clic en Editar** y, a continuación, seleccione la directiva que desea asignar.
    - Para editar la configuración de la directiva asignada al propietario del equipo, haga clic en el nombre de la directiva y luego realice los cambios que desee.  

## <a name="uploading-custom-apps"></a>Cargar aplicaciones personalizadas

Al cargar una aplicación personalizada (también conocida como instalación de equipo) que usa el consentimiento específico de los recursos, la aplicación debe proceder del inquilino en el que se está instalando. Es decir, el registro de aplicaciones de Azure AD debe ser de este inquilino. Los administradores globales están exentos de esta restricción y pueden cargar aplicaciones personalizadas desde cualquier espacio empresarial, ya sea directamente a un equipo (instalación de equipo) o al catálogo de aplicaciones de espacio empresarial.

## <a name="related-topics"></a>Temas relacionados

- [Permisos de RSC disponibles](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Administrar las aplicaciones en el Centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
