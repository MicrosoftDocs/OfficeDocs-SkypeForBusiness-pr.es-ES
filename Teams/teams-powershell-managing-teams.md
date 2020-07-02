---
title: Administrar equipos con Microsoft Teams PowerShell
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
description: Aprenda a administrar Microsoft Teams con Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944147"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Administrar equipos con Microsoft Teams PowerShell

En este artículo se muestra cómo usar Microsoft Teams PowerShell para administrar equipos y Skype empresarial. 

Use esta guía junto con la [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) y la [Referencia del cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Crear y administrar equipos con PowerShell

Los cmdlets para crear y administrar equipos se encuentran en el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Los equipos están respaldados por grupos de Office 365, por lo que al crear un equipo, se crea un grupo. Hay un conjunto de cmdlets para operar en el equipo principal y su configuración ( ``new-team`` , ``get-team`` , ``set-team`` ), administrar usuarios de equipo ( ``add-teamuser`` , ``remove-teamuser`` ), así como cmdlets para administrar los canales del equipo ( ``new-teamchannel`` , ``remove-teamchannel`` ). Todos estos cmdlets se pueden ejecutar como usuarios finales, pero solo funcionarán en los equipos de los que es miembro o de quien es miembro. Si es un administrador global o un administrador de servicios de equipo, podrá actuar en todos los equipos de su organización.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> El **GROUPID** usado en los cmdlets del módulo Microsoft Teams PowerShell es el mismo que la propiedad **Identity** devuelta por ``Get-UnifiedGroup`` el módulo de PowerShell de Exchange.

## <a name="manage-policies-via-powershell"></a>Administrar directivas a través de PowerShell

> [!NOTE]
> - El conector de Skype empresarial online se está consolidando en Teams PowerShell. Actualmente está disponible en la versión preliminar pública. En el tiempo, los cmdlets de Skype empresarial online que se aplican a los equipos estarán disponibles de forma nativa en el módulo de PowerShell de Teams. Los pasos de instalación están disponibles en el artículo [instalar Teams PowerShell](teams-powershell-install.md) .
>
> - Los cmdlets estarán disponibles en la sesión de PowerShell una vez que se conecte a Skype empresarial online. Para obtener más información, vea [administrar Skype empresarial online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Busque los cmdlets para administrar directivas en el [módulo de cmdlet de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=39366).

Una directiva es un grupo de opciones que se pueden aplicar de forma granular a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las directivas en sí y, a continuación, asignar esas directivas a los usuarios. La estructura general es la siguiente:

- **Obtener** comandos (por ejemplo, ``Get-CsTeamsMeetingPolicy`` ): devuelve los documentos de directiva que están disponibles para que los asigne en su organización, incluidas las directivas creadas por Microsoft para su uso, así como las directivas personalizadas que haya creado.
   - Para buscar solo las directivas personalizadas que ha creado en su organización, use ``-Filter "tag:*"`` .

- **Nuevos** comandos (por ejemplo, ``New-CsTeamsMeetingPolicy`` ): crea nuevas directivas para que su organización las asigne a los usuarios de su organización. No todas las directivas admiten la creación de directivas personalizadas. A menudo, esto sirve para asegurarse de que las directivas que usa en su organización tengan una combinación de configuración compatible.

- **Establecer** comandos (por ejemplo, ``Set-CsTeamsMeetingPolicy`` ): establece valores concretos en una directiva determinada. Algunas directivas no tienen comandos SET disponibles, o bien contienen parámetros que no se pueden personalizar en la Directiva. Las descripciones de PowerShell le indican qué parámetros no se pueden personalizar. 
   - Para editar la Directiva que se asignará de forma predeterminada a los usuarios de su organización que no tienen una directiva personalizada asignada, ejecute ``Set-Cs<PolicyName> -Identity Global`` .

- **Quitar** comandos (por ejemplo, ``Remove-CsTeamsMeetingPolicy`` ): elimina una directiva personalizada que se ha creado en su espacio empresarial. Si elimina una directiva personalizada que se ha asignado al menos a un usuario de su organización, ese usuario revertirá a la directiva global.
   - En realidad, no se puede quitar la directiva global de la organización, pero si desea restablecer la directiva global de su organización a la configuración predeterminada proporcionada por Microsoft, ejecute ``Remove-Cs<PolicyName> -Identity Global`` .

- Comando **Grant** (por ejemplo, ``Grant-CsTeamsMeetingPolicy`` ): asigna una directiva a un usuario en particular.
   - Para quitar una asignación de directiva personalizada y hacer que el usuario vuelva a la directiva predeterminada de su organización, ejecute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> No todas las directivas permiten la creación de directivas personalizadas y algunas directivas tienen una configuración que no se puede personalizar (por lo que se puede ver la configuración, pero no se puede establecer un valor personalizado durante ``set-`` y ``new-`` ). La documentación de cada cmdlet llama si los parámetros están disponibles para su uso por parte de los clientes.

Parámetros comunes:

- **Identity**: para ``Get-`` , ``Set-`` , ``New-`` , y ``Remove-`` , el parámetro **Identity** siempre hará referencia a una instancia de Policy específica. En ``Grant`` el caso de, el parámetro **Identity** hace referencia a un objeto de usuario específico al que se aplica la Directiva.

## <a name="manage-configurations-via-powershell"></a>Administrar configuraciones a través de PowerShell

Busque los cmdlets para administrar su configuración en el [módulo de cmdlet de Skype empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Las configuraciones son cubos de configuración mantenidos en el servicio que no se pueden especificar en un nivel de usuario. La configuración siempre se aplica en toda la organización. Su configuración global es la única configuración eficaz de su organización. Cada tipo de configuración incluye dos cmdlets principales:

- ``Get-Cs<ConfigurationName>``(por ejemplo, ``Get-CsTeamsClientConfiguration`` ):

- ESTABLECER comandos (por ejemplo, ``Set-CsTeamsClientConfiguration`` ): establezca las propiedades en la configuración de ese tipo. Especifique los parámetros que desea modificar.
   > Puede hacer referencia a la configuración que está modificando de una de estas dos maneras: especificando-**Identity global**o ejecutando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer cada rol de administrador?

Leer [use los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md) con el fin de comprender los roles de administrador que pueden ejecutar cada cmdlet de PowerShell.

## <a name="related-topics"></a>Temas relacionados

[Instalar Teams PowerShell](teams-powershell-install.md)

[Notas de la versión de Teams PowerShell](teams-powershell-release-notes.md)

[Referencia de cmdlet para Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar roles de administrador para administrar Teams](using-admin-roles.md)