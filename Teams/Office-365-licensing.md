---
title: Licencias de Office 365 para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "Conozca las distintas licencias de Office 365, cuáles permiten a los usuarios usar Microsoft Teams y cómo habilitarlas o deshabilitarlas."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 401788f354ad57bded48d59a54646d6c10235662
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>Licencias de Office 365 para Microsoft Teams
========================================

Estas suscripciones de Office 365 permiten a los usuarios usar Teams:

|Planes de Pequeña Empresa  |Planes de Empresa  |Planes de Educación  |
|---------|---------|---------|
|Office 365 Empresa Essentials     |Office 365 Enterprise E1         |Office 365 Educación         |
|Office 365 Empresa Premium     |Office 365 Enterprise E3         |Office 365 Educación Plus         |
|     |Office 365 Enterprise E4 (retirada)         |Office 365 Educación E3 (retirada)         |
|     |Office 365 Enterprise E5         |Office 365 Educación E5   
      |Office 365 Enterprise F1 |  |

> [!NOTE]
> Teams también está disponible para organizaciones sin ánimo de lucro. Las licencias gubernamentales no se admiten en este momento, pero se está investigando para admitirlas en el futuro.
        


En cuanto a la funcionalidad **principal** de Teams, no hay diferencias entre las distintas suscripciones de Office 365: la disponibilidad de las capacidades de cumplimiento no depende del nivel de suscripción adecuado. (Para saber más, vea [Plan de capacidades de protección de información y seguridad de Office 365](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408).)

Todos los planes de suscripción que se admiten pueden acceder al cliente web, los clientes de escritorio y las aplicaciones para el móvil de Teams.

Teams no está disponible como un servicio independiente.

<a name="teams-license"></a>Licencia de Teams
-------------

La licencia de Teams está habilitada, de manera predeterminada, para todos los usuarios que tengan suscripciones válidas de Office 365.

![Captura de pantalla de la configuración en la sección de licencias en el Centro de administración de Office 365, donde se ve Microsoft Teams como Activado.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


Teams puede estar activado o desactivado para un tipo de licencia completo dentro de una organización y está activado de forma predeterminada para todos los tipos de licencias, excepto los usuarios invitados. **No es posible activar Teams solo para una parte de un tipo de licencia mediante el conmutador de Teams en el Centro de administración de Office 365.** Si desea activar Teams para algunos miembros de su organización y desactivarlo para otros (por ejemplo, si está planificando un proyecto piloto de Teams con un grupo determinado de usuarios), active el conmutador de licencia de Teams para todos y después desactívelo por usuario.

![Captura de pantalla de la configuración del tipo de licencia/usuario de Teams en la sección de licencias del Centro de administración de Office 365, donde se ve Microsoft Teams como Activado.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**Consejo:** habilitar y deshabilitar Teams como una licencia de carga de trabajo mediante PowerShell se realiza igual que con cualquier otra carga de trabajo. El nombre del plan de servicio es TEAMS1 para Microsoft Teams. (Consulte [Deshabilitar el acceso a los servicios con Office 365 PowerShell](https://technet.microsoft.com/en-us/library/dn771769.aspx) para obtener más información).

**Muestra:** a continuación encontrará una muestra rápida de cómo se deshabilita Microsoft Teams para todos los miembros en un tipo de licencia particular. Primero deberá realizar esto y después habilitarlo individualmente para los usuarios que deben tener acceso por motivos de las pruebas piloto.

*Para mostrar los tipos de planes que tiene en su organización, use el siguiente comando:*

      Get-MsolAccountSku

*Rellene el nombre del plan que incluye el nombre de su organización y el plan de su centro educativo (como ContosoSchool:ENTERPRISEPACK_STUDENT), y después ejecute los siguientes comandos:*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*Para deshabilitar Microsoft Teams para todos los usuarios con una licencia activa para su plan, ejecute el siguiente comando:*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x