---
title: Consentimiento específico de recursos en Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre la configuración que necesita configurar para controlar si los propietarios de equipos de su organización pueden dar su consentimiento a las aplicaciones.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190501"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentimiento específico de recursos en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

El consentimiento específico de recursos en Microsoft Teams permite a los propietarios del equipo dar su consentimiento a las aplicaciones para acceder a los datos del equipo. Algunos ejemplos de este tipo de acceso son la capacidad de leer mensajes de canal, crear y eliminar canales, así como de crear y quitar pestañas de canales.

Como administrador, puede controlar si los propietarios de equipos de su organización pueden dar su consentimiento mediante la configuración que configure mediante el módulo de PowerShell de Azure Active Directory (Azure AD) o el Azure Portal y el centro de administración de Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Establecer si los propietarios de equipos pueden dar consentimiento a las aplicaciones

Estas son las opciones de configuración que debe establecer para controlar si los propietarios del equipo pueden dar su consentimiento a las aplicaciones. Asegúrate de revisar todas las opciones de configuración siguientes.

### <a name="settings-in-azure-ad"></a>Configuración en Azure AD

Las dos opciones siguientes determinan si los propietarios del equipo pueden dar su consentimiento a las aplicaciones.

> [!IMPORTANT]
> El cambio de cualquiera de estas opciones de configuración no afecta al acceso a los datos de las aplicaciones que ya tenían el consentimiento concedido. Por ejemplo, si configura estas opciones para evitar que los propietarios del equipo den su consentimiento, estos cambios no quitarán el acceso a los datos que ya se han concedido.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>La opción "Los usuarios pueden dar su consentimiento para que las aplicaciones accedan a los datos de la empresa en su nombre"

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento a las aplicaciones en su nombre. Para permitir que los propietarios del equipo den su consentimiento, esta configuración debe establecerse en **Sí**. Para administrar esta configuración, haga lo siguiente:

1. En la Azure Portal, vaya a **Enterprise aplicaciones** > **Configuración de usuario**.
2. En **Enterprise aplicaciones**, establezca **Los Usuarios pueden dar su consentimiento a las aplicaciones que tengan acceso a los datos de la compañía en su nombre** en **No** o **Sí**.

También puede administrar esta configuración con PowerShell. Para obtener más información, consulte [Configurar contenido de usuario en aplicaciones](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>La configuración de "EnableGroupSpecificConsent"

Esta configuración controla si los usuarios de su organización pueden dar su consentimiento a las aplicaciones que tengan acceso a los datos de la compañía para los grupos de los que son propietarios. Esta configuración debe estar habilitada para que los propietarios del equipo den su consentimiento. Para conocer los pasos para administrar esta configuración con PowerShell, consulte [Configurar el consentimiento del propietario del grupo para que las aplicaciones accedan a los datos del grupo](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Configuración en el centro de administración de Microsoft Teams

Además de la configuración de Azure AD, la [configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings) en la página [Administrar aplicaciones](manage-apps.md) , si una aplicación está bloqueada o permitida en la página [Administrar aplicaciones](manage-apps.md#allow-and-block-apps) , y la [directiva de permisos de la aplicación](teams-app-permission-policies.md) asignada al propietario del equipo determina si el propietario del equipo puede dar su consentimiento.

> [!IMPORTANT]
> El cambio de cualquiera de estas opciones de configuración no afecta al acceso a los datos de las aplicaciones que ya tenían el consentimiento concedido. Por ejemplo, si deshabilita aplicaciones de terceros en toda la organización o bloquea aplicaciones específicas para evitar que los propietarios del equipo den su consentimiento, estos cambios no quitarán el acceso a datos que ya se ha concedido.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>La configuración "Permitir aplicaciones de terceros" en la configuración de aplicaciones de toda la organización

Esta configuración de aplicaciones para toda la organización controla si los usuarios de su organización pueden usar aplicaciones de terceros. Esta configuración debe estar activada para permitir que los propietarios del equipo den su consentimiento. Para administrar esta configuración, haga lo siguiente:

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **Teams aplicaciones****Administrar aplicaciones** >  y, a continuación, haga clic en **Configuración de aplicaciones para toda la organización**.
2. En **Aplicaciones de terceros**, desactiva o activa **Permitir aplicaciones de terceros**.

    ![Captura de pantalla de la configuración "Permitir aplicaciones de terceros en Teams"](media/resource-specific-consent-org-wide-setting.png)

Es posible que tenga que esperar hasta 24 horas para que sus cambios surtan efecto.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Permitir o bloquear la aplicación en el nivel de organización

Al bloquear o permitir una aplicación en la página [Administrar aplicaciones](manage-apps.md#allow-and-block-apps) , esa aplicación se bloquea o se permite para todos los usuarios de la organización. Los propietarios de equipos solo pueden dar su consentimiento a una aplicación si se permite la aplicación. Para permitir o bloquear una aplicación en el nivel de organización, haga lo siguiente:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la página Administrar aplicaciones, selecciona la aplicación y, a continuación, haz clic en **Bloquear** para bloquearla o haz clic en **Permitir** para permitirla.

    ![Captura de pantalla de las aplicaciones bloqueadas en la configuración de toda la organización.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Directiva de permisos de aplicación asignada al propietario del equipo

Los propietarios de equipos solo pueden dar su consentimiento a las aplicaciones para que su directiva de permisos de aplicación les permita ejecutarse. Para ver y administrar la directiva de permisos de la aplicación asignada a un propietario de equipo, haga lo siguiente:

1. En el panel de navegación izquierdo del Microsoft Teams centro de administración, vaya a **Usuarios**.
2. Haga doble clic en el nombre para mostrar del propietario del equipo y, a continuación, haga clic en **Directivas**.
3. La directiva asignada al propietario del equipo se muestra en **Directiva de permisos de aplicación**.
    - Para asignar una directiva diferente, haga clic en **Editar** y, a continuación, seleccione la directiva que desea asignar.
    - Para editar la configuración de la directiva asignada al propietario del equipo, haga clic en el nombre de la directiva y luego realice los cambios que desee.  

## <a name="uploading-custom-apps"></a>Cargar aplicaciones personalizadas

Al cargar una aplicación personalizada (también conocida como instalación de prueba) que use consentimiento específico de recursos, la aplicación debe proceder del espacio empresarial en el que se está instalando. En otras palabras, el registro de la aplicación de Azure AD debe ser de este inquilino. Los administradores globales están exentos de esta restricción y pueden cargar aplicaciones personalizadas desde cualquier espacio empresarial, directamente en un equipo (instalación de prueba) o en el catálogo de aplicaciones del inquilino.

## <a name="related-topics"></a>Temas relacionados

- [Permisos de RSC disponibles](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Administrar las aplicaciones en el centro de administración de Microsoft Teams](manage-apps.md)
- [Administrar directivas de permisos de aplicación en Teams](teams-app-permission-policies.md)
