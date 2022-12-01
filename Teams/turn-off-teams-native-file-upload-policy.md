---
title: Desactivar la directiva de carga de archivos nativos de Teams
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Obtenga información sobre cómo crear, establecer, asignar y ajustar la directiva de archivos de Teams con PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198532"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desactivar la directiva de carga de archivos nativos de Teams

Microsoft Teams usa OneDrive y SharePoint para almacenar y compartir contenido, pero es posible que algunas organizaciones y usuarios prefieran usar proveedores de almacenamiento de terceros.  

Si su organización elige un tercero para el almacenamiento de contenido, debe desactivar el `NativeFileEntryPoints` parámetro en la directiva Archivos de Teams. Este parámetro está habilitado de forma predeterminada, lo que muestra la opción de cargar contenido de OneDrive o SharePoint en chats o canales de Teams.

Este artículo le ayudará a crear, establecer, asignar y quitar el `NativeFileEntryPoints` parámetro con PowerShell.

>[!NOTE]
>Cuando la directiva Archivos de Teams está desactivada, los usuarios no verán puntos de acceso para OneDrive y SharePoint en Teams, pero la creación de nuevos equipos y canales seguirá desencadenando la generación de bibliotecas de SharePoint coincidentes.

## <a name="prepare-to-update-the-teams-files-policy"></a>Prepararse para actualizar la directiva de archivos de Teams

### <a name="set-up-microsoft-powershell"></a>Configurar Microsoft PowerShell

Actualmente, esta directiva no se puede cambiar en el Centro de administración de Teams. El administrador de inquilinos de Microsoft 365 de su organización tendrá que realizar los cambios con los cmdlets de PowerShell que se detallan más adelante en este artículo.

Obtenga información sobre cómo instalar el módulo de PowerShell Teams con Galería de PowerShell leyendo [Instalar Microsoft módulo de PowerShell de Teams](teams-powershell-install.md).

Para instalar o descargar el módulo de PowerShell de Teams, consulte [Galería de PowerShell para Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obtener más información sobre cómo configurar PowerShell para la administración de Teams, consulte [Administrar Teams con Microsoft PowerShell de Teams](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicaciones de terceros en el Centro de Administración de Teams

Este paso no es necesario para cambiar la directiva archivos de Teams, pero es necesario cuando esté listo para integrar su proveedor de almacenamiento de terceros en la experiencia de los usuarios de Teams.

El administrador de inquilinos de Microsoft 365 deberá habilitar la directiva "Permitir aplicaciones de terceros" en el Centro de administración de Teams.

Para obtener información sobre cómo permitir aplicaciones personalizadas o de terceros, consulte Administrar la configuración de aplicaciones para toda la organización en [Administrar las aplicaciones en el centro de administración de Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desactivar NativeFileEntryPoints para todo el espacio empresarial

Si establece el `-Identity` parámetro en `Global` , se aplicará la configuración de directiva a todos los usuarios de la organización.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Ejemplo de cmdlet de directiva de PowerShell para todo el espacio empresarial

Este comando de Ejemplo de PowerShell establecerá el`NativeFileEntryPoints` parámetro para `Disabled` todo el espacio empresarial.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Comprobar el estado de su inquilino  

Para ver el estado actual de la directiva de archivos de Teams de su inquilino, use el `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Activar o desactivar el punto de carga de archivos nativos

Para activar o desactivar el punto de carga de archivos nativos para todo el espacio empresarial, establezca el `NativeFileEntryPoints` parámetro en uno `Enabled` o `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Quitar la directiva de los usuarios

Para quitar la directiva Archivos de Teams para sus usuarios, use el `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desactivar NativeFileEntryPoints para usuarios específicos

También puede actualizar la directiva Archivos de Teams para usuarios específicos creando una nueva cadena de directiva `-Identity` Archivos de Teams y asignando la directiva recién creada a los usuarios.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Ejemplo de cmdlet de directiva de PowerShell para usuarios específicos

Este comando de PowerShell de ejemplo creará un nuevo `CsTeamsFilesPolicy` con el `-Identity` nombre como `UserPolicy` y el `NativeFileEntryPoints` parámetro establecido `Disabled`en .

Cuando se asigna a un usuario el `CsTeamsFilesPolicy` con `-Identity UserPolicy`, sus puntos de entrada de archivos nativos se desactivarán.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Asignar una directiva a un usuario

Una vez que haya creado la nueva directiva, puede asignarla a los usuarios mediante el `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Actualizar la directiva

Si necesita cambiar la configuración de la nueva directiva `UserPolicy`de archivos de Teams, use el `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Quitar la directiva de la lista completa de usuarios

Para quitar la directiva de todos los usuarios asignados a la directiva `UserPolicy`Archivos de Teams, use el `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Una vez que haya realizado cambios en la directiva, deje que los cambios se muestren en los clientes de Teams de los usuarios hasta 12 horas.
