---
title: Descripción de PowerShell para Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Aprenda a usar los controles de PowerShell para administrar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20e85b2f45977a0a78d0d358c2e8aaa01b9257e4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235136"
---
# <a name="teams-powershell-overview"></a>Descripción de PowerShell para Teams

Microsoft Teams tiene un amplio conjunto de herramientas para que los administradores de ti administren el producto a través del centro de administración de Microsoft Teams, los controles de PowerShell y las API de gráficos. Esta guía explica cómo estructuramos nuestros cmdlets de PowerShell para que los usen los administradores de ti y proporciona punteros a documentación adicional. Tenga en cuenta que los distintos roles de administrador de Teams tienen acceso a diferentes cmdlets. Para obtener más información, consulte [usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>¿Qué módulos necesita usar?

Los controles de PowerShell para administrar equipos se encuentran en dos módulos de PowerShell diferentes: 
- [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) : el módulo de Teams PowerShell contiene todos los cmdlets que necesita para crear y administrar Teams.  
- [Módulo de PowerShell de Skype empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=39366): el módulo de PowerShell de Skype empresarial contiene los cmdlets para administrar directivas, configuraciones y otras herramientas de Teams. 

La documentación de referencia para los controles de PowerShell le indicará qué módulo contiene el cmdlet que está investigando. (Al final, los dos módulos se combinarán).

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer cada rol de administrador?

Leer [use los roles de administrador de Microsoft Teams para administrar los equipos](using-admin-roles.md) con el fin de comprender qué cmdlets de PowerShell diferentes roles de administrador podrán aprovechar.

## <a name="creating-and-managing-teams-via-powershell"></a>Crear y administrar equipos a través de PowerShell

Los cmdlets para crear y administrar equipos se encuentran en el [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

Los equipos están respaldados por grupos de O365, por lo que al crear un equipo, se crea un grupo. Hay un conjunto de cmdlets para operar en el equipo principal y su configuración``new-team``(, ``get-team``, ``set-team``), administrar usuarios de equipo (``add-teamuser``, ``remove-teamuser``), así como cmdlets para administrar los canales del equipo (``new-teamchannel``, ``remove-teamchannel``). Todos estos cmdlets se pueden ejecutar como usuarios finales, pero solo funcionarán en los equipos de los que es miembro o de quien es miembro. Si es un administrador global o un administrador de servicios de equipo, podrá actuar en todos los equipos de su organización.

> El **GROUPID** usado en los cmdlets del módulo Microsoft Teams PowerShell es el mismo **** que la propiedad Identity ``Get-UnifiedGroup`` devuelta por el módulo de PowerShell de Exchange.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Diferencias entre la versión preliminar y el módulo disponible en general de Microsoft Teams PowerShell

Cuando publicamos nuestra versión general disponible de nuestro módulo de PowerShell, se dejaron algunos cmdlets en el módulo beta, tal y como se describe en la tabla siguiente.

| Cmdlet | Disponible en vista previa | Disponible en 1,0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Sí | Sí |
| Connect-MicrosoftTeams | Sí | Sí |
| Disconnect-MicrosoftTeams | Sí | Sí |
| Get-Team | Sí | Sí |
| Get-TeamChannel | Sí | Sí |
| Get-TeamFunSettings | Antes de la versión 1,0 | No |
| Get-TeamGuestSettings | Antes de la versión 1,0 | No |
| Get-TeamHelp | Sí | Sí |
| Get-TeamMemberSettings | Antes de la versión 1,0 | No |
| Get-TeamMessagingSettings | Antes de la versión 1,0 | No |
| Get-TeamUser | Sí | Sí |
| Nuevo: equipo | Sí | Sí |
| Nuevo: TeamChannel | Sí | Sí |
| Quitar equipo | Sí | Sí |
| Remove-TeamChannel | Sí | Sí |
| Remove-TeamUser | Sí | Sí |
| Set-Team | Sí | Sí |
| Set-TeamChannel | Sí | Sí |
| Set-TeamFunSettings | Antes de la versión 1,0 | No |
| Set-TeamGuestSettings | Antes de la versión 1,0 | No |
| Set-TeamMemberSettings | Antes de la versión 1,0 | No |
| Set-TeamMessagingSettings | Antes de la versión 1,0 | No |
| Set-TeamPicture | Sí | No, planificado |


## <a name="managing-policies-via-powershell"></a>Administración de directivas a través de PowerShell

Los cmdlets para administrar directivas se encuentran en el [módulo de cmdlet de Skype empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Una directiva es un grupo de opciones que se pueden aplicar de forma granular a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las directivas en sí y, a continuación, asignar esas directivas a los usuarios. La estructura general es la siguiente:

- Comandos GET (por ejemplo, ``Get-CsTeamsMeetingPolicy``): devuelva los documentos de directiva que están disponibles para que los asigne en su organización, tanto las directivas creadas por Microsoft para usted como las directivas personalizadas que haya creado.
   > Si desea buscar solo las directivas personalizadas que ha creado en su organización, puede usar ``-Filter "tag:*"``.

- NUEVOS comandos (por ejemplo, ``New-CsTeamsMeetingPolicy``): le permita crear nuevas directivas para su organización que estarán disponibles para asignarlas a los usuarios de su organización. No todas las directivas admiten la creación de directivas personalizadas. A menudo, esto sirve para asegurarse de que las directivas que usa en su organización tengan una combinación de configuración compatible.

- ESTABLECER comandos (por ejemplo, ``Set-CsTeamsMeetingPolicy``): permite establecer valores concretos en una directiva determinada. Algunas directivas no tienen comandos SET disponibles o contienen parámetros que no se pueden personalizar en la Directiva. Cada descripción de PowerShell llamará a los parámetros que no se pueden personalizar. 
   > Para editar la Directiva que se asignará de forma predeterminada a los usuarios de su organización que no tienen una directiva personalizada asignada ``Set-Cs<PolicyName> -Identity Global``, ejecute.

- QUITAR comandos (por ejemplo, ``Remove-CsTeamsMeetingPolicy``): puede usar este cmdlet para eliminar una directiva personalizada que se haya creado en su inquilino. Si elimina una directiva personalizada que se ha asignado al menos a un usuario de su organización, ese usuario revertirá a la directiva global.
   > En realidad, no puede quitar la directiva global de su organización, pero si desea restablecer la directiva global de su organización a la configuración predeterminada proporcionada por Microsoft, puede ejecutar ``Remove-Cs<PolicyName> -Identity Global``.

- Comando GRANT (por ejemplo, ``Grant-CsTeamsMeetingPolicy``): permite asignar una directiva a un usuario en particular.
   > Para quitar una asignación de directiva personalizada y hacer que el usuario vuelva a la directiva predeterminada de su organización, ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``ejecute.

> [!TIP]
> No todas las directivas permiten la creación de directivas personalizadas y algunas directivas tienen una configuración que no se puede personalizar (por lo que se puede ver la configuración, pero no ``set-`` se ``new-``puede establecer un valor personalizado durante y). La documentación del cmdlet específico llamará si los parámetros no están disponibles para su uso por parte de los clientes.

Parámetros comunes:

- **Identity**: para ``Get-``, ``Set-``, ``New-``, y ``Remove-``, el parámetro **Identity** siempre hará referencia a una instancia de Policy específica. En ``Grant``el caso de, el parámetro **Identity** hace referencia a un objeto de usuario específico al que se aplica la Directiva.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Administración de configuraciones a través de PowerShell

Los cmdlets para administrar la configuración están en el [módulo de cmdlet de Skype empresarial](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Las configuraciones son cubos de configuración mantenidos en el servicio que no se pueden especificar en un nivel de usuario. La configuración siempre se aplica en toda la organización. Su configuración global es la única configuración eficaz de su organización. Cada tipo de configuración incluye dos cmdlets principales:

- ``Get-Cs<ConfigurationName>``(por ejemplo, ``Get-CsTeamsClientConfiguration``): 

- ESTABLECER comandos (por ejemplo, ``Set-CsTeamsClientConfiguration``): establezca las propiedades en la configuración de ese tipo. Especifique los parámetros que desea modificar.
   > Puede hacer referencia a la configuración que está modificando de una de estas dos maneras: especificando-**Identity global**o ejecutando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Otras herramientas de PowerShell

Puede encontrar instrucciones detalladas sobre cómo usar todos los controles de PowerShell para administrar Microsoft Teams y Skype empresarial, incluyendo descripciones detalladas de la configuración de cada Directiva, en la [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) y [Skype para Referencia del cmdlet empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Más información

- [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md)
