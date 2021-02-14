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
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852181"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Administrar Teams con Microsoft Teams PowerShell

Este artículo le muestra cómo usar Microsoft Teams PowerShell para administrar Teams y Skype Empresarial. 

Use esta guía junto con la referencia de [cmdlet de Microsoft Teams y](https://docs.microsoft.com/powershell/teams/?view=teams-ps) la referencia de cmdlet de Skype [Empresarial.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Crear y administrar equipos con PowerShell

Los cmdlets para crear y administrar equipos se encuentran en el módulo PowerShell de [Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Los equipos están a través de grupos de Office 365, por lo que al crear un equipo, puede crear un grupo. Hay un conjunto de cmdlets para operaciones en el equipo principal y su configuración (, , ), la administración de usuarios del equipo ( , ), así como cmdlets para administrar los ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` canales ``new-teamchannel`` del equipo ( , ``remove-teamchannel`` ). Todos estos cmdlets se pueden ejecutar como usuarios finales, pero solo funcionarán en los equipos de los que es propietario o miembro. Si es administrador global o administrador de servicios de Teams, podrá actuar en todos los equipos de su organización.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> El **GroupId usado** en los cmdlets del módulo PowerShell de Microsoft Teams es el mismo que la propiedad **Identity** devuelta por el módulo ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Administrar directivas a través de PowerShell

> [!NOTE]
> - Skype Empresarial Online Connector se consolida en Teams PowerShell. Actualmente está disponible en la versión preliminar pública. A tiempo, los cmdlets de Skype Empresarial Online que se apliquen a Teams estarán disponibles de forma nativa en el módulo PowerShell de Teams. Los pasos de instalación están disponibles en el [artículo instalar Equipos de PowerShell.](teams-powershell-install.md)
>
> - Los cmdlets estarán disponibles en la sesión de PowerShell una vez que se conecte a Skype Empresarial Online. Para obtener más información, consulte [Administrar Skype Empresarial Online con PowerShell de Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Busque los cmdlets para administrar directivas en el módulo [de cmdlet de Skype Empresarial.](https://www.microsoft.com/download/details.aspx?id=39366)

Una directiva es un grupo de opciones de configuración que se puede aplicar pormenorísticamente a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las directivas propiamente dichas y, después, asignar dichas directivas a los usuarios. La estructura general es:

- **Comandos GET** (por ejemplo, ): Devuelve los documentos de directivas que tiene disponibles asignar en su organización, incluidas las directivas creadas por Microsoft para que las use, así como las directivas personalizadas que ha ``Get-CsTeamsMeetingPolicy`` creado.
   - Para buscar solo las directivas personalizadas que ha creado en su organización, use ``-Filter "tag:*"`` .

- **Comandos** NUEVOS (por ejemplo, ): Crea directivas para que su organización las asigne ``New-CsTeamsMeetingPolicy`` a los usuarios de su organización. No todas las directivas admiten la creación de directivas personalizadas. A menudo esto es para asegurarse de que las directivas que usa en su organización tienen una combinación compatible de opciones de configuración.

- **Comandos SET** (por ejemplo, ``Set-CsTeamsMeetingPolicy`` ): Establece valores concretos en una directiva determinada. Algunas directivas no tienen comandos SET disponibles o contienen parámetros que no se pueden personalizar en la directiva. Las descripciones de PowerShell le dicen qué parámetros no se pueden personalizar. 
   - Para editar la directiva que se asignará de forma predeterminada a los usuarios de su organización que no tienen asignada una directiva personalizada, ejecute ``Set-Cs<PolicyName> -Identity Global`` .

- **Quitar** comandos (por ejemplo, ``Remove-CsTeamsMeetingPolicy`` ): Elimina una directiva personalizada que se ha creado en su espacio empresarial. Si elimina una directiva personalizada que se ha asignado a al menos un usuario de su organización, dicho usuario volverá a la directiva global.
   - En realidad no puede quitar la directiva global de su organización, pero si desea restablecer la directiva global de su organización a la configuración predeterminada proporcionada por Microsoft, ejecute ``Remove-Cs<PolicyName> -Identity Global`` .

- **Comando** GRANT (por ejemplo, ``Grant-CsTeamsMeetingPolicy`` ): asigna una directiva a un usuario determinado.
   - Para quitar una asignación de directiva personalizada y hacer que el usuario vuelva a la directiva predeterminada de su organización, ejecute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> No todas las directivas permiten crear directivas personalizadas y algunas directivas tienen configuraciones que no puede personalizar (por lo que puede ver la configuración, pero no puede establecer un valor personalizado durante ``set-`` y ``new-`` ). La documentación de cada cmdlet indica si los parámetros están disponibles para que los clientes los usen.

Parámetros comunes:

- **Identity**: For , y , el parámetro Identity siempre hará referencia ``Get-`` a una instancia de directiva ``Set-`` ``New-`` ``Remove-`` específica.  Para, el parámetro Identity hace referencia a un objeto de usuario específico al ``Grant`` que se está aplicando la directiva. 

## <a name="manage-configurations-via-powershell"></a>Administrar configuraciones a través de PowerShell

Busque los cmdlets para administrar la configuración en el módulo [de cmdlet de Skype Empresarial.](https://www.microsoft.com/en-us/download/details.aspx?id=39366)

Las configuraciones son cubos de configuración que se mantienen en el servicio y que no se pueden especificar en un nivel de usuario. La configuración se aplica siempre en toda la organización. La configuración global es la única configuración eficaz de su organización. Cada tipo de configuración incluye dos cmdlets principales:

- ``Get-Cs<ConfigurationName>`` (por ejemplo, ``Get-CsTeamsClientConfiguration`` ):

- Comandos SET (por ejemplo, ``Set-CsTeamsClientConfiguration`` ): establecen propiedades en la configuración de ese tipo. Especifique los parámetros que desea modificar.
   > Puede hacer referencia a la configuración que está modificando de una de estas dos formas: especificando -**Identidad global** o ejecutando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer cada rol de administrador?

Lea [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md) y comprender qué roles de administrador pueden ejecutar cada cmdlet de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Instalación de Teams powerShell](teams-powershell-install.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet para Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar roles de administrador para administrar Teams](using-admin-roles.md)
