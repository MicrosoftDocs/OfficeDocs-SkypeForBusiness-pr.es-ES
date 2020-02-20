---
title: Recomenda Crear directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77688be2f2b1ba547f79e45ca89dd529e24318c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="06e65-102">Recomenda Crear directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="06e65-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06e65-103">_**Última modificación del tema:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="06e65-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="06e65-104">Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia cuando usa Lync 2013 y el identificador de conferencia de acceso telefónico local que usa un participante de la Conferencia de acceso telefónico local para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="06e65-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="06e65-105">El formato del identificador de conferencia es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="06e65-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="06e65-106">Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias.</span><span class="sxs-lookup"><span data-stu-id="06e65-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="06e65-107">En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="06e65-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="06e65-108">Si aplica esta sugerencia, los Id. de conferencia, por lo general, se mantendrán cortos.</span><span class="sxs-lookup"><span data-stu-id="06e65-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="06e65-109">Sin embargo, una vez que el número de directorios de conferencia (entre los grupos de servidores) supera los 9, la longitud del identificador de conferencia aumentará para admitir conferencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="06e65-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="06e65-110">Crear un directorio de conferencia</span><span class="sxs-lookup"><span data-stu-id="06e65-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="06e65-111">En el shell de administración de Lync Server, escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="06e65-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="06e65-112">Por ejemplo, el siguiente ejemplo crea un directorio de conferencia con la identidad 42, hospedada en el grupo atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="06e65-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06e65-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e65-113">See Also</span></span>


[<span data-ttu-id="06e65-114">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06e65-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="06e65-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="06e65-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

