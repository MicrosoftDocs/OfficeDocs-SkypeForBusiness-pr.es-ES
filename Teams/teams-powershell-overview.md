---
title: Información general de PowerShell de los equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: article
ms.service: msteams
description: Aprenda a usar los controles de PowerShell para administrar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 181655609fd031da177a21e10684186ca5c52066
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "24025286"
---
# <a name="teams-powershell-overview"></a>Información general de PowerShell de los equipos

Microsoft Teams tiene un amplio conjunto de herramientas para los administradores de TI a administrar el producto a través de la Microsoft Teams & Skype para el centro de administración de negocio, los controles de PowerShell y las API de gráfico. Esta guía explica cómo se estructura nuestros cmdlets de PowerShell para los administradores de TI a utilizar y proporciona punteros a la documentación adicional. Tenga en cuenta que distintas funciones de administración de los equipos tienen acceso a los cmdlets de diferentes. Para obtener más información, vea [roles de administrador de equipos de uso de Microsoft para administrar los equipos](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>¿Qué módulos necesita usar?

Los controles de PowerShell para administrar Microsoft Teams están en dos módulos diferentes de PowerShell: el [módulo de PowerShell de los equipos de Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3) (vista previa pública) y la [Skype para el módulo de PowerShell de negocio](https://www.microsoft.com/en-us/download/details.aspx?id=39366). El módulo de PowerShell de equipos contiene todos los cmdlets que se necesita para crear y administrar los equipos de sí mismos, mientras que el Skype para el módulo de PowerShell de negocio contiene los controles de administración de directivas, las configuraciones y otras herramientas de los equipos. Los documentos de referencia para los controles de PowerShell le indicará qué módulo contiene el cmdlet que va a investigar. (Al final, los dos módulos se combinarán.)

## <a name="what-can-each-admin-role-do"></a>¿Qué puede hacer con cada rol de administrador?

[Roles de administrador de equipos de uso de Microsoft para administrar los equipos](using-admin-roles.md) para comprender qué roles de administrador diferentes de los cmdlets de PowerShell podrán sacar provecho de lectura.

## <a name="creating-and-managing-teams-via-powershell"></a>Creación y administración de los equipos a través de PowerShell

Los cmdlets para crear y administrar los equipos se encuentran en el [módulo de PowerShell de los equipos de Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3). 

Los equipos se realizan mediante grupos de O365, por lo que cuando se crea un equipo, para crear un grupo. Hay un conjunto de cmdlets proporcionados para el funcionamiento en el equipo principal y su configuración (``new-team``, ``get-team``, ``set-teamfunsettings``), así como los cmdlets para la administración de los canales del equipo (``new-teamchannel``, ``remove-teamchannel``). Todos estos cmdlets se pueden ejecutar como los usuarios finales, pero que van a funcionar sólo en los equipos que posee o es un miembro de. Si es un administrador Global o administrador de servicio de los equipos, podrá actuar en todos los equipos de la organización.

> **GroupId** usado en el módulo de cmdlets de PowerShell de los equipos de Microsoft es el mismo que la propiedad de **identidad** devuelta por ``Get-UnifiedGroup`` en el módulo de PowerShell de Exchange.

## <a name="managing-policies-via-powershell"></a>Administración de directivas a través de PowerShell

Los cmdlets de administración de directivas se encuentran en el [Skype para el módulo de cmdlet de negocio](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Una directiva es un grupo de opciones de configuración que se puede aplicar de forma granular a usuarios individuales. Cada tipo de directiva tiene su propio conjunto de cmdlets para crear, ver, eliminar y actualizar las propias directivas y, a continuación, asignar dichas directivas a usuarios. La estructura general es:

- Comandos GET (por ejemplo, ``Get-CsTeamsMeetingPolicy``): devolver los documentos de directiva que están disponibles para asignar en la organización, las directivas creadas por Microsoft para su uso y las directivas personalizadas que haya creado.
   > Si desea buscar sólo las directivas personalizadas que haya creado en su organización, puede usar ``-Filter "tag:*"``.

- NUEVOS comandos (por ejemplo, ``New-CsTeamsMeetingPolicy``): permiten crear nuevas directivas para la organización que, a continuación, se encuentran disponibles que se asignará a los usuarios de su organización. No todas las directivas de admiten la creación de directivas personalizadas. A menudo es asegurarse de que las directivas de que uso en la organización tienen una combinación de configuración admitida.

- CONJUNTO de comandos (por ejemplo, ``Set-CsTeamsMeetingPolicy``): permite establecer determinados valores en una directiva determinada. Algunas de las directivas no tienen el conjunto de comandos disponibles, o contengan parámetros que no se puede personalizar en la directiva. Cada descripción de PowerShell llamará a los parámetros que no se puede personalizar. 
   > Para editar la directiva de forma predeterminada se asignará a los usuarios de la organización que no tienen asignada una directiva personalizada, ejecute ``Set-Cs<PolicyName> -Identity Global``.

- QUITAR comandos (por ejemplo, ``Remove-CsTeamsMeetingPolicy``): puede usar este cmdlet para eliminar una directiva personalizada que se ha creado en el inquilino. Si elimina una directiva personalizada que se ha asignado al menos un usuario en la organización, que el usuario se revertirá a la directiva global.
   > En realidad no se puede quitar la directiva global de la organización, pero si desea restablecer la directiva global de la organización a la configuración predeterminada proporcionada por Microsoft, puede ejecutar ``Remove-Cs<PolicyName> -Identity Global``.

- Comando GRANT (por ejemplo, ``Grant-CsTeamsMeetingPolicy``): permite asignar una directiva a un usuario determinado.
   > Para quitar una asignación de directivas personalizadas y hacer que el usuario retroceder a la directiva predeterminada de la organización, ejecute ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> No todas las directivas de permiten directivas personalizadas que se creará y algunas de las directivas tienen una configuración que no se puede personalizar (por lo que puede ver la configuración, pero no se puede establecer un valor personalizado durante ``set-`` y ``new-``). La documentación del cmdlet específico llamará a si los parámetros no están disponibles para su uso por los clientes.

Parámetros comunes:

- **Identidad**: para ``Get-``, ``Set-``, ``New-``, y ``Remove-``, el parámetro **Identity** siempre hará referencia a una instancia de directiva específicos. Para ``Grant``, el parámetro **Identity** hace referencia a un objeto de usuario específico al que se aplica la directiva.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Administrar configuraciones a través de PowerShell

Los cmdlets para la administración de la configuración se encuentran en el [Skype para el módulo de cmdlet de negocio](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Las configuraciones son depósitos de configuración que se mantienen en el servicio que no se puede especificar un nivel de usuario. Configuración siempre se aplica en toda la organización. La configuración global es la configuración sólo eficaz en la organización. Cada tipo de configuración se suministra con dos cmdlets principales:

- ``Get-Cs<ConfigurationName>``(por ejemplo, ``Get-CsTeamsClientConfiguration``): 

- CONJUNTO de comandos (por ejemplo, ``Set-CsTeamsClientConfiguration``): establecer las propiedades de la configuración de ese tipo. Especificar los parámetros que desea modificar.
   > Puede hacer referencia a la configuración que está modificando en una de estas dos formas: especificando -**Identity Global**, o bien ejecutando ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Otras herramientas de PowerShell

Puede encontrar instrucciones detalladas sobre cómo usar todos los controles de PowerShell para administrar Microsoft Teams y Skype para la empresa, como una descripción detallada de la configuración de cada directiva, en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps) y [Skype para Referencia del cmdlet de negocio](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>Más información

- [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)
- [Skype para referencia del cmdlet de negocio](https://docs.microsoft.com/en-us/powershell/skype/intro?view=skype-ps)
- [Usar las funciones de administración de Microsoft Teams para administrar los equipos](using-admin-roles.md)
