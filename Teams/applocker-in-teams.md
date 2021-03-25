---
title: Directivas de control de AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120852"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="7f4f7-103">Directivas de control de aplicaciones de AppLocker en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f4f7-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="7f4f7-104">En este artículo se explica cómo habilitar la aplicación cliente de escritorio de Teams con directivas de control de aplicaciones de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="7f4f7-105">El uso de AppLocker está diseñado para restringir la ejecución de programas y scripts por usuarios no administrativos.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="7f4f7-106">Para obtener más información y instrucciones sobre AppLocker, vea [¿Qué es AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="7f4f7-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="7f4f7-107">El proceso para habilitar Teams con AppLocker requiere la creación de directivas de descripción de permitidos basadas en AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="7f4f7-108">Las directivas se crean con software de administración de directivas de grupo o con el uso de cmdlets de Windows PowerShell para AppLocker (consulte la referencia técnica de [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="7f4f7-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="7f4f7-109">La directiva de AppLocker se guarda en formato XML y se puede editar con cualquier texto o editor XML.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="7f4f7-110">Lista de permitidos de Teams con AppLocker</span><span class="sxs-lookup"><span data-stu-id="7f4f7-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="7f4f7-111">Las reglas de AppLocker se organizan en colecciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="7f4f7-112">Las reglas de AppLocker se aplican a la aplicación de destino y son los componentes que la directiva de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="7f4f7-113">Para permitir Teams, le recomendamos que use las reglas de condición de [publisher,](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ya que todos los archivos de la aplicación de Teams están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="7f4f7-114">No se recomienda el uso de reglas de ruta de acceso porque el directorio de instalación de Teams se puede escribir por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="7f4f7-115">Tampoco recomendamos el uso de reglas hash porque las reglas tendrían que actualizarse cada vez que se actualice la aplicación cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="7f4f7-116">Puesto que los archivos ejecutables de escritorio de Teams están firmados digitalmente, la condición del editor identifica un archivo de aplicación en función de su firma digital y atributos de versión incrustados.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="7f4f7-117">La firma digital contiene información sobre la empresa que creó el archivo de aplicación (el editor).</span><span class="sxs-lookup"><span data-stu-id="7f4f7-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="7f4f7-118">La información de versión, que se obtiene del recurso binario, incluye el nombre del producto del que forma parte el archivo y el número de versión del archivo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f4f7-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="7f4f7-119">Ejemplo de reglas de condición del editor</span><span class="sxs-lookup"><span data-stu-id="7f4f7-119">Example of publisher condition rules</span></span>

<span data-ttu-id="7f4f7-120">Para la aplicación cliente de Teams (todos los archivos, todas las versiones) agregue lo siguiente a las reglas ejecutables & reglas DLL:</span><span class="sxs-lookup"><span data-stu-id="7f4f7-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="7f4f7-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7f4f7-121">Related topics</span></span>
<span data-ttu-id="7f4f7-122">[¿Qué es AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="7f4f7-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>