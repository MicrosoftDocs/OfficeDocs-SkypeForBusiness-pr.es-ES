---
title: Requisitos previos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f81299b2efdde3be262439528409d89abf369f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509137"
---
# <a name="prerequisites"></a><span data-ttu-id="79323-102">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="79323-102">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79323-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="79323-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="79323-104">Hay varios requisitos de configuración de hardware, software y sistema que necesitará para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79323-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="79323-105">Requisitos de hardware del cliente</span><span class="sxs-lookup"><span data-stu-id="79323-105">Client Hardware Requirements</span></span>

<span data-ttu-id="79323-106">Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 en su implementación de Lync Server 2013, para cada 4.500 usuarios cuya carga desee simular, necesitará al menos un equipo dedicado que cumpla los siguientes requisitos mínimos de hardware:</span><span class="sxs-lookup"><span data-stu-id="79323-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="79323-107">adaptador de red de 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="79323-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="79323-108">8 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="79323-108">8-GB ram</span></span>

  - <span data-ttu-id="79323-109">2 unidades de procesamiento central (CPU) de doble núcleo</span><span class="sxs-lookup"><span data-stu-id="79323-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="79323-110">Requisitos de software del cliente</span><span class="sxs-lookup"><span data-stu-id="79323-110">Client Software Requirements</span></span>

<span data-ttu-id="79323-111">Para ejecutar la herramienta de esfuerzo y rendimiento de Lync Server 2013 en su implementación de Lync Server 2013, los sistemas operativos compatibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="79323-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="79323-112">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="79323-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="79323-113">Sistema operativo Windows Server 2008 (edición de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="79323-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="79323-114">El equipo cliente debe cumplir con los siguientes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="79323-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="79323-115">Debe tener instalado el motor en tiempo de ejecución de [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) .</span><span class="sxs-lookup"><span data-stu-id="79323-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="79323-116">En Windows Server 2008/Windows Server 2012, la característica experiencia de escritorio debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="79323-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="79323-117">Debe tener instalado el [paquete redistribuible de Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64).</span><span class="sxs-lookup"><span data-stu-id="79323-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="79323-118">Una implementación de Lync Server 2013 totalmente configurada.</span><span class="sxs-lookup"><span data-stu-id="79323-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="79323-119">Las bibliotecas de API administrada de comunicaciones unificadas de Microsoft (UCMA) 4,0 se incluyen en el paquete de instalación, por lo que el UCMA no es necesario y no debe instalarse en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="79323-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="79323-120">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="79323-120">Configuration Requirements</span></span>

<span data-ttu-id="79323-121">Los equipos que ejecutarán la herramienta de esfuerzo y rendimiento de Lync Server 2013 deben configurarse de acuerdo con los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="79323-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="79323-122">Debe iniciar sesión como miembro del grupo de administradores local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="79323-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="79323-123">La herramienta de esfuerzo y rendimiento de Lync Server 2013 (LyncPerfTool.exe) no se puede ejecutar en un equipo que también ejecute componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79323-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="79323-124">Debe ejecutar la herramienta de creación de usuarios de Lync Server 2013 (UserProvisioningTool.exe) en el servidor front-end o en el servidor Standard Edition donde residirán las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="79323-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="79323-125">Cuando la herramienta se ejecuta varias veces, cada usuario que esté habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.</span><span class="sxs-lookup"><span data-stu-id="79323-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="79323-126">El tamaño del archivo de paginación debe ser administrado por el sistema o debe ser al menos 1,5 veces la cantidad de RAM del sistema.</span><span class="sxs-lookup"><span data-stu-id="79323-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

