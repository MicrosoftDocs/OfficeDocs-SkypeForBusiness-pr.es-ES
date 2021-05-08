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
description: Aprenda a administrar Microsoft Teams con Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238976"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Administrar Teams con Microsoft Teams PowerShell

En este artículo se muestra cómo usar Microsoft Teams PowerShell para administrar Teams y Skype Empresarial. 

Use esta guía junto con la referencia Microsoft Teams [cmdlet y](/powershell/teams/?view=teams-ps) Skype Empresarial [de cmdlet.](/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Crear y administrar equipos con PowerShell

Los cmdlets para crear y administrar equipos se encuentran en el [módulo Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams los grupos Office 365, por lo que al crear un equipo, crea un grupo. Hay un conjunto de cmdlets para operar en el equipo principal y su configuración ( , , ), la administración de usuarios del equipo ( , ), así como cmdlets para administrar los ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` canales ``new-teamchannel`` del equipo ( , ``remove-teamchannel`` ). Todos estos cmdlets se pueden ejecutar como usuarios finales, pero solo funcionarán en los equipos de los que es propietario o de los que es miembro. Si es administrador global o administrador Teams, podrá actuar en todos los equipos de su organización.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> El **GroupId** usado en los cmdlets Microsoft Teams módulos de PowerShell es el mismo que la propiedad **Identity** devuelta por en el módulo Exchange ``Get-UnifiedGroup`` PowerShell.

## <a name="manage-policies-via-powershell"></a>Administrar directivas a través de PowerShell

> [!NOTE]
> - Skype Empresarial Online Connector se consolida en Teams PowerShell. Actualmente está disponible en versión preliminar pública. Con el tiempo, Skype Empresarial cmdlets en línea que se apliquen a Teams estarán disponibles de forma nativa en el módulo Teams PowerShell. Los pasos de instalación están disponibles en el [artículo Instalar Teams PowerShell.](teams-powershell-install.md)
>
> - Los cmdlets estarán disponibles en la sesión de PowerShell una vez que se conecte a Skype Empresarial Online. Para obtener más información, vea [Administrar Skype Empresarial Online con Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Busque los cmdlets para administrar directivas en [el módulo Skype Empresarial cmdlet](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Una directiva es un grupo de configuraciones que se pueden aplicar granularmente a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las propias directivas y, después, asignar esas directivas a los usuarios. La estructura general es:

- **Comandos GET** (por ejemplo, ): Devuelve los documentos de directiva que están disponibles para asignar en su organización, incluidas las directivas creadas por Microsoft para que las use, así como las directivas personalizadas que ha ``Get-CsTeamsMeetingPolicy`` creado.
   - Para buscar solo las directivas personalizadas que ha creado en su organización, use ``-Filter "tag:*"`` .

- **Comandos NUEVO** (por ejemplo, ): Crea nuevas directivas para que su organización ``New-CsTeamsMeetingPolicy`` asigne a los usuarios de su organización. No todas las directivas admiten la creación de directivas personalizadas. A menudo, esto es para asegurarse de que las directivas que usa en su organización tienen una combinación de configuración compatible.

- **Comandos SET** (por ejemplo, ``Set-CsTeamsMeetingPolicy`` ): Establece valores específicos en una directiva determinada. Algunas directivas no tienen comandos SET disponibles o contienen parámetros que no se pueden personalizar en la directiva. Las descripciones de PowerShell le dicen qué parámetros no se pueden personalizar. 
   - Para editar la directiva que se asignará de forma predeterminada a los usuarios de su organización que no tengan asignada una directiva personalizada, ejecute ``Set-Cs<PolicyName> -Identity Global`` .

- **Comandos** REMOVE (por ejemplo, ): Elimina una directiva personalizada que ``Remove-CsTeamsMeetingPolicy`` se ha creado en el espacio empresarial. Si elimina una directiva personalizada que se ha asignado a al menos un usuario de su organización, ese usuario volverá a la directiva global.
   - En realidad, no puede quitar la directiva global de su organización, pero si desea restablecer la directiva global de su organización a la configuración predeterminada proporcionada por Microsoft, ejecute ``Remove-Cs<PolicyName> -Identity Global`` .

- **Comando GRANT** (por ejemplo, ``Grant-CsTeamsMeetingPolicy`` ): Asigna una directiva a un usuario determinado.
   - Para quitar una asignación de directiva personalizada y hacer que el usuario vuelva a la directiva predeterminada de su organización, ejecute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> No todas las directivas permiten crear directivas personalizadas y algunas tienen configuraciones que no puede personalizar (por lo que puede ver la configuración, pero no puede establecer un valor personalizado durante ``set-`` y ``new-`` ). La documentación de cada cmdlet indica si los parámetros están disponibles para su uso por los clientes.

Parámetros comunes:

- **Identidad:** ``Get-`` Para ``Set-`` , y , el ``New-`` parámetro Identidad siempre hará referencia a una instancia de directiva ``Remove-`` específica.  Para , el parámetro Identity hace referencia a un objeto de usuario específico al que se está ``Grant`` aplicando la directiva. 

## <a name="manage-configurations-via-powershell"></a>Administrar configuraciones a través de PowerShell

Busque los cmdlets para administrar la configuración en [el módulo Skype Empresarial cmdlet](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).

Las configuraciones son cubos de configuración que se mantienen en el servicio que no se pueden especificar a nivel de usuario. Configuración aplicar siempre en toda la organización. La configuración global es la única configuración eficaz de su organización. Cada tipo de configuración incluye dos cmdlets principales:

- ``Get-Cs<ConfigurationName>`` (por ejemplo, ``Get-CsTeamsClientConfiguration`` ):

- Comandos SET (por ejemplo, ``Set-CsTeamsClientConfiguration`` ): establecer propiedades en la configuración de ese tipo. Especifique los parámetros que desea modificar.
   > Puede hacer referencia a la configuración que está modificando de dos maneras: especificando -**Identidad global** o ejecutando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer cada rol de administrador?

Lea [Usar Microsoft Teams de administrador para](using-admin-roles.md) administrar Teams comprender qué roles de administrador pueden ejecutar cada cmdlet de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Instalar Teams PowerShell](teams-powershell-install.md)

[Teams Notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Referencia de cmdlet para Teams](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)

[Usar roles de administrador para administrar Teams](using-admin-roles.md)