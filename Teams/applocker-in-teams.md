---
title: Directivas de control de AppLocker
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bcb75eb28730b4387ebcee0be869f1f91cc31c5
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137430"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="aeae6-103">Directivas de control de aplicaciones de AppLocker en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aeae6-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="aeae6-104">En este artículo se explica cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="aeae6-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="aeae6-105">El uso de AppLocker está diseñado para restringir la ejecución de programas y scripts por parte de usuarios no administrativos.</span><span class="sxs-lookup"><span data-stu-id="aeae6-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="aeae6-106">Para obtener más información y orientación en AppLocker, consulte [¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="aeae6-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="aeae6-107">El proceso de habilitar equipos con AppLocker requiere la creación de políticas de listas blancas basadas en AppLocker.</span><span class="sxs-lookup"><span data-stu-id="aeae6-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="aeae6-108">Las directivas se crean con el software de administración de directivas de grupo y/o el uso de cmdlets de Windows PowerShell para AppLocker (consulte la [referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="aeae6-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="aeae6-109">La Directiva de AppLocker se guarda en formato XML y puede editarse con cualquier editor de texto o XML.</span><span class="sxs-lookup"><span data-stu-id="aeae6-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="aeae6-110">Listas blancas de equipos con AppLocker</span><span class="sxs-lookup"><span data-stu-id="aeae6-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="aeae6-111">Las reglas de AppLocker se organizan en colecciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="aeae6-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="aeae6-112">Las reglas de AppLocker se aplican a la aplicación de destino y son los componentes que conforman la Directiva de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="aeae6-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="aeae6-113">Para los equipos de la lista blanca, le recomendamos que use las [reglas de condición de Publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , ya que todos los archivos de la aplicación Teams están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="aeae6-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="aeae6-114">No recomendamos el uso de reglas de ruta de acceso porque el directorio de instalación de Teams es grabable para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aeae6-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="aeae6-115">Tampoco recomendamos el uso de Reglas Hash porque las reglas deberían actualizarse cada vez que se actualice la aplicación cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="aeae6-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="aeae6-116">Como los archivos ejecutables de escritorio de Teams están firmados digitalmente, la condición Publisher identifica un archivo de aplicación en función de sus atributos de firma digital y versión insertada.</span><span class="sxs-lookup"><span data-stu-id="aeae6-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="aeae6-117">La firma digital contiene información sobre la empresa que creó el archivo de la aplicación (el publicador).</span><span class="sxs-lookup"><span data-stu-id="aeae6-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="aeae6-118">La información de versión, que se obtiene del recurso binario, incluye el nombre del producto del que forma parte el archivo y el número de versión del archivo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aeae6-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="aeae6-119">Ejemplo de reglas de condición de editor</span><span class="sxs-lookup"><span data-stu-id="aeae6-119">Example of publisher condition rules</span></span>

<span data-ttu-id="aeae6-120">Para la aplicación cliente de Teams (todos los archivos, todas las versiones), agregue lo siguiente a las reglas ejecutables & reglas de DLL:</span><span class="sxs-lookup"><span data-stu-id="aeae6-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="aeae6-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aeae6-121">Related topics</span></span>
<span data-ttu-id="aeae6-122">[¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="aeae6-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
