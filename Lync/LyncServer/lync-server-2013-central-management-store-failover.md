---
title: Lync Server 2013 conmutación por error del almacén de administración central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508047"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="33229-102">Conmutación por error del almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33229-102">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33229-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="33229-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="33229-104">El almacén de administración central contiene datos de configuración sobre los servidores y los servicios de la implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="33229-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="33229-105">Proporciona un almacenamiento sólido y esquematizado de los datos necesarios para definir, configurar, mantener, administrar, describir y usar una implementación de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="33229-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="33229-106">También valida los datos para garantizar la coherencia de la configuración.</span><span class="sxs-lookup"><span data-stu-id="33229-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="33229-107">Cada implementación de Lync incluye un almacén de administración central, hospedado por el servidor back-end de un grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="33229-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="33229-108">Cuando establece un emparejamiento de grupo de servidores que incluye el grupo que hospeda el almacén de administración central, se configura una base de datos de almacén de administración central de copia de seguridad en el grupo de copia de seguridad y los servicios de almacén de administración central se instalan en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="33229-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="33229-109">En cualquier momento, una de las dos bases de datos del almacén de administración central es Active Master y la otra es un modo de espera.</span><span class="sxs-lookup"><span data-stu-id="33229-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="33229-110">El contenido se replica por parte del servicio de copia de seguridad desde el maestro activo a la base de datos en espera.</span><span class="sxs-lookup"><span data-stu-id="33229-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="33229-111">Durante una conmutación por error de un grupo de servidores que implica a los grupos que hospedan el almacén de administración central, el administrador debe conmutar por error el almacén de administración central antes de realizar la conmutación por error del grupo</span><span class="sxs-lookup"><span data-stu-id="33229-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="33229-112">Una vez reparado el desastre, no es necesario realizar una conmutación por recuperación del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="33229-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="33229-113">Después de la reparación, el almacén de administración central del grupo de copia de seguridad original puede permanecer como maestro activo.</span><span class="sxs-lookup"><span data-stu-id="33229-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="33229-114">Los objetivos de ingeniería para la conmutación por error del almacén de administración central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para el objetivo de punto de recuperación (RPO).</span><span class="sxs-lookup"><span data-stu-id="33229-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

