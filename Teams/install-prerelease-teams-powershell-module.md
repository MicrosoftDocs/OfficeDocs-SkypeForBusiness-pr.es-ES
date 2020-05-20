---
title: Instalar la versión preliminar del módulo de PowerShell de Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Siga estos pasos para instalar la versión preliminar del módulo Teams PowerShell desde la galería de pruebas de PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321773"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Instalar la versión preliminar del módulo de PowerShell de Teams

En este artículo se describe cómo instalar la última versión preliminar del módulo Teams PowerShell desde la [Galería de pruebas de PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Necesitará la versión preliminar del módulo de PowerShell de Teams, en aquellos casos en los que los cmdlets para administrar una característica de Teams no se admiten en la versión de general disponible del módulo y solo están disponibles en la versión preliminar.

Siga estos pasos para instalar la versión preliminar más reciente del módulo de PowerShell de Teams en la galería de pruebas de PowerShell.

> [!NOTE]
> No instale el módulo de Teams PowerShell desde la galería de pruebas de PowerShell en paralelo con una versión del módulo de la [Galería de PowerShell pública](https://www.powershellgallery.com/packages/MicrosoftTeams/). Siga estos pasos para desinstalar primero el módulo de PowerShell de Teams de la galería de PowerShell pública y, a continuación, instale la última versión del módulo desde la galería de pruebas de PowerShell.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para desinstalar el módulo de PowerShell de Teams de la galería pública de PowerShell:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Cierre todas las sesiones de PowerShell existentes.
5. Inicie el módulo de Windows PowerShell de nuevo y, a continuación, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como una fuente de confianza:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Actualice a la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell

Si ya ha instalado el módulo de Teams PowerShell desde la galería de pruebas de PowerShell, siga estos pasos para actualizar a la última versión.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para actualizar la versión del módulo de PowerShell instalada actualmente desde la galería de pruebas de PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Temas relacionados

- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
