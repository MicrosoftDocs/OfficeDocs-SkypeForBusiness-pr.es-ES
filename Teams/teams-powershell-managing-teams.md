---
title: Administrar Teams con Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a administrar Microsoft Teams con PowerShell de Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396531"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Administrar Teams con Microsoft Teams PowerShell

En este artículo se muestra cómo usar Microsoft Teams PowerShell para administrar Teams y Skype Empresarial.

Use esta guía junto con la [referencia de cmdlets de Microsoft Teams](/powershell/teams/?view=teams-ps) y [la referencia de cmdlet de Skype Empresarial](/powershell/skype/intro?view=skype-ps).

Para administrar Teams en el Centro de administración de Teams, consulte [Administrar Teams con Azure Cloud Shell](#manage-teams-with-azure-cloud-shell).

## <a name="create-and-manage-teams-using-powershell"></a>Crear y administrar equipos con PowerShell

Los cmdlets para crear y administrar equipos se encuentran en el [módulo de Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Teams cuenta con el respaldo de Office 365 Grupos, por lo que al crear un equipo, se crea un grupo. Se proporciona un conjunto de cmdlets para operar en el equipo principal y su configuración (, , ), la administración de usuarios del equipo (``add-teamuser``, ``remove-teamuser``), así como cmdlets para administrar los canales del equipo (``new-teamchannel``, ``remove-teamchannel``). ``set-team````get-team````new-team`` Todos estos cmdlets se pueden ejecutar como usuarios finales, pero solo funcionarán en los equipos de su propiedad o de los que sea miembro. Si es un Administración global o administrador de Teams, podrá actuar en todos los equipos de su organización.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> El **GroupId** usado en los cmdlets del módulo PowerShell de Microsoft Teams es el mismo que la propiedad **Identity** devuelta por ``Get-UnifiedGroup`` en el módulo de Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Administrar Teams con Azure Cloud Shell

Cloud Shell es un shell interactivo, autenticado y accesible para el explorador que le permite administrar los recursos. Para obtener más información sobre Cloud Shell, vea [Azure Cloud Shell](/azure/cloud-shell/overview).

Para obtener acceso a Azure Cloud Shell y usar PowerShell para administrar Teams, inicie sesión en el Centro de administración de Teams.

1. Seleccione el icono de Cloud Shell en la esquina superior derecha.

    ![Captura de pantalla del encabezado del Centro de administración de Teams con Cloud Shell icono.](media/cloud-shell-icon-select.png)

1. Cuando se le solicite, elija **PowerShell**.

    ![Captura de pantalla del aviso de Azure Cloud Shell.](media/cloud-shell.png)

1. Ejecute el siguiente comando para iniciar una sesión de PowerShell de Teams:

    ```powershell
    Connect-MicrosoftTeams
    ```

Cuando haya completado estos pasos, estará listo para ejecutar los comandos de PowerShell de Teams.

> [!IMPORTANT]
> Si desea usar cmdlets Cs*, primero debe conectarse a Teams mediante el ``Connect-MicrosoftTeams -UseDeviceAuthentication`` comando.

## <a name="manage-policies-via-powershell"></a>Administrar directivas a través de PowerShell

> [!NOTE]
> - Skype Empresarial Conector en línea se está consolidando en PowerShell de Teams. Actualmente está disponible en versión preliminar pública. Con el tiempo, los cmdlets de Skype Empresarial Online que se aplican a Teams estarán disponibles de forma nativa en el módulo PowerShell de Teams. Los pasos de instalación están disponibles en el artículo [Instalar Teams PowerShell](teams-powershell-install.md) .
> - Los cmdlets estarán disponibles en la sesión de PowerShell una vez que se conecte a Skype Empresarial Online. Para obtener más información, consulte [Administrar Skype Empresarial en línea con Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Busque los cmdlets para administrar directivas en el [módulo de cmdlets de Skype Empresarial](/powershell/module/teams).

Una directiva es un grupo de opciones de configuración que se pueden aplicar pormenorizadamente a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las propias directivas y, a continuación, asignar esas directivas a los usuarios. La estructura general es la siguiente:

- **Comandos GET** (por ejemplo, ``Get-CsTeamsMeetingPolicy``): Devuelve los documentos de directiva que está disponible para asignar en su organización, incluidas las directivas creadas por Microsoft para su uso, así como las directivas personalizadas que ha creado.
  - Para buscar solo las directivas personalizadas que ha creado en su organización, use ``-Filter "tag:*"``.

- **Comandos NUEVOS** (por ejemplo, ``New-CsTeamsMeetingPolicy``): crea nuevas directivas para que la organización las asigne a los usuarios de la organización. No todas las directivas admiten la creación de directivas personalizadas. A menudo, esto es para asegurarse de que las directivas que usa en su organización tienen una combinación compatible de opciones de configuración.

- **Comandos SET** (por ejemplo, ``Set-CsTeamsMeetingPolicy``): establece valores concretos en una directiva determinada. Algunas directivas no tienen comandos SET disponibles o contienen parámetros que no se pueden personalizar en la directiva. Las descripciones de PowerShell indican qué parámetros no se pueden personalizar.
  - Para editar la directiva que se asignará de forma predeterminada a los usuarios de la organización que no tienen asignada una directiva personalizada, ejecute ``Set-Cs<PolicyName> -Identity Global``.

- **Comandos REMOVE** (por ejemplo, ``Remove-CsTeamsMeetingPolicy``): elimina una directiva personalizada que se ha creado en el espacio empresarial. Si elimina una directiva personalizada que se haya asignado a al menos un usuario de su organización, dicho usuario volverá a la directiva global.
  - No puedes quitar realmente la directiva global de tu organización, pero si quieres restablecer la directiva global de tu organización a la configuración predeterminada proporcionada por Microsoft, ejecuta ``Remove-Cs<PolicyName> -Identity Global``.

- **Comando GRANT** (por ejemplo, ``Grant-CsTeamsMeetingPolicy``): Asigna una directiva a un usuario determinado.
  - Para quitar una asignación de directiva personalizada y hacer que el usuario vuelva a la directiva predeterminada de su organización, ejecute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> No todas las directivas permiten la creación de directivas personalizadas y algunas directivas tienen configuraciones que no se pueden personalizar (por lo que puede ver la configuración, pero no puede establecer un valor personalizado durante ``set-`` y ``new-``). La documentación de cada cmdlet indica si los parámetros están disponibles para su uso por parte de los clientes.

Parámetros comunes:

- **Identidad**: Para ``Get-``, ``Set-``, ``New-``, y ``Remove-``, el parámetro **Identity** siempre hará referencia a una instancia de directiva específica. Para ``Grant``, el parámetro **Identity** hace referencia a un objeto de usuario específico al que se aplica la directiva.

## <a name="manage-configurations-via-powershell"></a>Administrar configuraciones a través de PowerShell

Busque los cmdlets para administrar la configuración en el [módulo de cmdlets de Skype Empresarial](/powershell/module/skype).

Las configuraciones son cubos de configuraciones que se mantienen en el servicio y que no se pueden especificar a nivel de usuario. La configuración siempre se aplica en toda la organización. La configuración global es la única configuración eficaz de su organización. Cada tipo de configuración incluye dos cmdlets principales:

- ``Get-Cs<ConfigurationName>`` (por ejemplo, ``Get-CsTeamsClientConfiguration``):

- Comandos SET (por ejemplo, ``Set-CsTeamsClientConfiguration``): establecer propiedades en la configuración de ese tipo. Especifique los parámetros que desea modificar.
    > [!NOTE]
    > Puede hacer referencia a la configuración que está modificando de una de estas dos maneras: especificando -**Identity Global** o ejecutando ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer cada rol de administrador?

Lea [Usar roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md) para comprender qué roles de administrador pueden ejecutar cada cmdlet de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Instalar PowerShell de Teams](teams-powershell-install.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet para Teams](/powershell/teams/?view=teams-ps)

[referencia de cmdlet de Skype Empresarial](/powershell/skype/intro?view=skype-ps)

[Usar roles de administrador para administrar Teams](using-admin-roles.md)
