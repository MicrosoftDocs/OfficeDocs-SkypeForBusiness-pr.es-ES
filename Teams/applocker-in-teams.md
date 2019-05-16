---
title: Directivas de control de aplicación de AppLocker en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Obtenga información sobre cómo habilitar la aplicación de cliente de escritorio de los equipos con directivas de control de aplicación de AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063216"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="88cdc-103">Directivas de control de aplicación de AppLocker en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88cdc-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="88cdc-104">En este artículo se explica cómo habilitar la aplicación de cliente de escritorio de los equipos con directivas de control de aplicación de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="88cdc-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="88cdc-105">Uso de AppLocker está diseñada para restringir la ejecución de programa y secuencias de comandos por los usuarios que no sean administrativos.</span><span class="sxs-lookup"><span data-stu-id="88cdc-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="88cdc-106">Para obtener más información y orientación sobre AppLocker, consulte [¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="88cdc-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="88cdc-107">El proceso para permitir a los equipos con AppLocker requiere la creación de las directivas de AppLocker-based lista blanca.</span><span class="sxs-lookup"><span data-stu-id="88cdc-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="88cdc-108">Las directivas se crean con software de administración de directiva de grupo o el uso de cmdlets de Windows PowerShell para AppLocker (vea la [referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="88cdc-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="88cdc-109">La directiva de AppLocker se guarda en formato XML y se puede editar con cualquier editor de XML o de texto.</span><span class="sxs-lookup"><span data-stu-id="88cdc-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="88cdc-110">Lista blanca de los equipos con AppLocker</span><span class="sxs-lookup"><span data-stu-id="88cdc-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="88cdc-111">Las reglas de AppLocker se organizan en colecciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="88cdc-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="88cdc-112">Las reglas de AppLocker se aplican a la aplicación de destino y que son los componentes que componen la directiva de AppLocker.</span><span class="sxs-lookup"><span data-stu-id="88cdc-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="88cdc-113">Para los equipos de la lista blanca, se recomienda usar las [reglas de condición de publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ya que todos los archivos de aplicación de los equipos están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="88cdc-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="88cdc-114">No se recomienda el uso de las reglas de ruta de acceso porque el directorio de instalación de los equipos se puede escribir el usuario.</span><span class="sxs-lookup"><span data-stu-id="88cdc-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="88cdc-115">También se no recomienda el uso de reglas de hash porque las reglas tendría que se actualizan cada vez que se actualiza la aplicación de los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="88cdc-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="88cdc-116">Dado que los archivos ejecutables de escritorio de los equipos están firmados digitalmente, la condición de publisher identifica un archivo de aplicación basado en los atributos de versión incrustado y su firma digital.</span><span class="sxs-lookup"><span data-stu-id="88cdc-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="88cdc-117">La firma digital contiene información acerca de la compañía que creó el archivo de aplicación (el publicador).</span><span class="sxs-lookup"><span data-stu-id="88cdc-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="88cdc-118">La información de versión, se obtiene desde el recurso binario, incluye el nombre del producto que el archivo forma parte de y el número de versión de archivo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="88cdc-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="88cdc-119">Ejemplo de las reglas de condición de publisher</span><span class="sxs-lookup"><span data-stu-id="88cdc-119">Example of publisher condition rules</span></span>

<span data-ttu-id="88cdc-120">Para la aplicación de cliente de los equipos (todos los archivos, todas las versiones):</span><span class="sxs-lookup"><span data-stu-id="88cdc-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="88cdc-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="88cdc-121">Related topics</span></span>
<span data-ttu-id="88cdc-122">[¿Qué es AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referencia técnica de AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="88cdc-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>