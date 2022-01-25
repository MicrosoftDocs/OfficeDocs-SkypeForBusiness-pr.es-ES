---
title: Desactivar la Teams de archivos Upload nativos
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Obtenga información sobre cómo crear, establecer, asignar y ajustar la directiva Teams archivos con PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192507"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Desactivar la Teams de archivos Upload nativos

Microsoft Teams usa OneDrive y SharePoint (ODSP) para almacenar y compartir contenido, pero algunas organizaciones y usuarios pueden preferir usar proveedores de almacenamiento de terceros.  

Si su organización elige un tercero para el almacenamiento de contenido, debe desactivar el parámetro en la directiva ``NativeFileEntryPoints`` Teams archivos. Este parámetro está habilitado de forma predeterminada, que muestra la opción de cargar contenido desde ODSP a Teams chats o canales.

Este artículo le ayudará a crear, establecer, asignar y quitar el ``NativeFileEntryPoints`` parámetro con PowerShell.

>[!NOTE]
>Cuando la directiva archivos de Teams está desactivada, los usuarios no verán los puntos de acceso de OneDrive y SharePoint (ODSP) en Teams, pero la creación de nuevos equipos y canales seguirá desencadenando la generación de bibliotecas de SharePoint que coincidan.

## <a name="prepare-to-update-the-teams-files-policy"></a>Prepararse para actualizar la directiva Teams archivos

### <a name="set-up-microsoft-powershell"></a>Configurar Microsoft PowerShell

Actualmente, esta directiva no se puede cambiar en el centro Teams administración. El administrador de Microsoft 365 inquilino de su organización tendrá que realizar los cambios con los cmdlets de PowerShell detallados más adelante en este artículo.

Obtenga información sobre cómo instalar el módulo de Teams PowerShell con la Galería de PowerShell leyendo [Instalar Microsoft Teams módulo de PowerShell](teams-powershell-install.md).

Para instalar o descargar el módulo Teams PowerShell, vea [Galería de PowerShell para Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Para obtener más información sobre cómo configurar PowerShell para Teams administración, vea Administrar Teams con [Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Permitir aplicaciones de terceros en el Centro Teams administración

Este paso no es necesario para cambiar la directiva de archivos de Teams, pero es necesario cuando esté listo para integrar su proveedor de almacenamiento de terceros en la experiencia de Teams usuarios.

El Microsoft 365 inquilino deberá habilitar la directiva "Permitir aplicaciones de terceros" en el Teams de administración.

Para obtener información sobre cómo permitir aplicaciones personalizadas o de terceros, vea Administrar la configuración de aplicaciones de toda la organización en Administrar las aplicaciones en el centro de administración [de Microsoft Teams de administración.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Desactivar NativeFileEntryPoints para todo el espacio empresarial

Si establece ``-Identity`` el parámetro ``Global`` en, se aplicará la configuración de directiva a todos los usuarios de su organización.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Cmdlet de directiva de PowerShell de ejemplo para todo el espacio empresarial

Este comando de PowerShell de ejemplo establecerá ``NativeFileEntryPoints`` el parámetro en para todo el espacio ``Disabled`` empresarial.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Comprobar el estado del inquilino  

Para ver el estado actual de la directiva de archivos Teams inquilino, use el ``Get-CsTeamsFilesPolicy`` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Activar o desactivar el punto de carga de archivos nativos

Para activar o desactivar el punto de carga de archivos nativos para todo el espacio empresarial, establezca el ``NativeFileEntryPoints`` parámetro en ``Enabled`` o ``Disabled`` .

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Quitar la directiva para los usuarios

Para quitar la directiva Teams archivos para los usuarios, use el ``Remove-CsTeamsFilesPolicy`` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Desactivar NativeFileEntryPoints para usuarios específicos

También puede actualizar la directiva Teams archivos para usuarios específicos creando una nueva cadena de directiva archivos de Teams y asignando la directiva recién creada a ``-Identity`` los usuarios.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Cmdlet de directiva de PowerShell de ejemplo para usuarios específicos

Este comando de PowerShell de ejemplo creará una nueva con ``CsTeamsFilesPolicy`` el nombre como y el parámetro establecido en ``-Identity`` ``UserPolicy`` ``NativeFileEntryPoints`` ``Disabled`` .

Cuando se asigne a un usuario los puntos de entrada con , se desactivarán sus puntos de entrada de archivo ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` nativos.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Asignar una directiva al usuario

Una vez que haya creado la nueva directiva, puede asignarla a los usuarios con el ``Grant-CsTeamsFilesPolicy`` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Actualizar la directiva

Si necesita cambiar la configuración de la nueva directiva Teams ``UserPolicy`` archivos, use el ``Set-CsTeamsFilePolicy`` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Quitar la directiva de la lista completa de usuarios

Para quitar la directiva de todos los usuarios asignados a la directiva Teams archivos ``UserPolicy`` , use el ``Remove-CsTeamsFilesPolicy`` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Una vez que haya realizado cambios en la directiva, permita hasta 12 horas para que los cambios se muestren en los clientes Teams usuarios.
