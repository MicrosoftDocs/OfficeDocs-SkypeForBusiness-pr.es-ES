---
title: Crear directorios de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: obtenga información sobre cómo crear directorios de conferencias en Skype Empresarial Server.'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119479"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="8fda2-103">Crear directorios de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8fda2-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="8fda2-104">**Resumen:** Obtenga información sobre cómo crear directorios de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8fda2-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="8fda2-105">Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Skype Empresarial y el identificador de conferencia de solo numérico que usa un participante de conferencia de acceso telefónico local para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="8fda2-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="8fda2-106">Crear un directorio de conferencias</span><span class="sxs-lookup"><span data-stu-id="8fda2-106">Create a conference directory</span></span>

<span data-ttu-id="8fda2-107">Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias.</span><span class="sxs-lookup"><span data-stu-id="8fda2-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="8fda2-108">En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8fda2-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="8fda2-109">Con esta directriz, los IDs de conferencia generalmente se pueden mantener pequeños.</span><span class="sxs-lookup"><span data-stu-id="8fda2-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="8fda2-110">Sin embargo, una vez que el número de directorios de conferencia (en todos los grupos) supere los 9, la longitud del id. de conferencia aumentará para admitir conferencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="8fda2-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="8fda2-111">El formato de un identificador de conferencia es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fda2-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="8fda2-112">Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory.**</span><span class="sxs-lookup"><span data-stu-id="8fda2-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="8fda2-113">Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="8fda2-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="8fda2-114">Para obtener más información, [vea New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8fda2-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
