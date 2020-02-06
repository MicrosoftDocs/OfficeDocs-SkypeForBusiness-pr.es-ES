---
title: Crear directorios de conferencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Resumen: Aprenda a crear directorios de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 368248f18291b049b3478f20d3de4a11d4ae6f1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818571"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="98d85-103">Crear directorios de conferencia en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="98d85-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="98d85-104">**Resumen:** Aprenda a crear directorios de conferencia en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="98d85-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="98d85-105">Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia cuando se usa Skype empresarial y el identificador de conferencia de acceso telefónico local que usa un participante de conferencia de acceso telefónico local para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="98d85-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="98d85-106">Crear un directorio de conferencia</span><span class="sxs-lookup"><span data-stu-id="98d85-106">Create a conference directory</span></span>

<span data-ttu-id="98d85-107">Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias.</span><span class="sxs-lookup"><span data-stu-id="98d85-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="98d85-p101">En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los id. de conferencia, por lo general, se mantendrán cortos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.</span><span class="sxs-lookup"><span data-stu-id="98d85-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="98d85-111">El formato de un identificador de conferencia es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="98d85-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="98d85-p102">Para crear un directorio de conferencia, use el cmdlet **New-CsConferenceDirectory**. Por ejemplo, el siguiente comando crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="98d85-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="98d85-114">Para obtener más información, vea [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="98d85-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

