---
title: 'Lync Server 2013: configurar directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 339eba57121b475732794b15c2c5d16dced303ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="be1cb-102">Configurar directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1cb-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be1cb-103">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="be1cb-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="be1cb-104">Una *directiva de voz* habilita un conjunto de características y asocia uno o más registros de uso RTC para definir las características de llamada y los permisos para los usuarios a los que se asigna la directiva.</span><span class="sxs-lookup"><span data-stu-id="be1cb-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="be1cb-p101">El ámbito de la directiva de voz puede ser *Sitio* (que define las características y permisos predeterminados para un sitio de red) o *Usuario* (que define las características y los permisos que se van a asignar a cada usuario o cada grupo). A los usuarios que no tengan asignada una directiva de voz se les asignará automáticamente una directiva global, que es la directiva de voz predeterminada que se instala con el producto.</span><span class="sxs-lookup"><span data-stu-id="be1cb-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be1cb-107">Para obtener más información, consulte <A href="lync-server-2013-voice-policies.md">directivas de voz en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="be1cb-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be1cb-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="be1cb-108">In This Section</span></span>

  - [<span data-ttu-id="be1cb-109">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1cb-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="be1cb-110">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1cb-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="be1cb-111">Configurar el escape de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be1cb-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

