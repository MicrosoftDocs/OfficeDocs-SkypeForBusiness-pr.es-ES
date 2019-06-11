---
title: 'Lync Server 2013: información general sobre el analizador de procedimientos recomendados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a304f33071b8be13c61c3f930f196113ac3af6de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="23d9e-102">Información general del analizador de procedimientos recomendados de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23d9e-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23d9e-103">_**Última modificación del tema:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="23d9e-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="23d9e-104">Puede usar Lync Server 2013, analizador de procedimientos recomendados para identificar y resolver problemas con la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="23d9e-105">Lync Server 2013, Best Practices Analyzer recopila información de configuración de los componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="23d9e-106">Con el acceso adecuado a la red, el analizador de procedimientos recomendados puede examinar los servidores que ejecutan servicios de dominio de Active Directory, mensajería unificada de Exchange Server (UM) y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="23d9e-107">Puede usar el analizador de procedimientos recomendados para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23d9e-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="23d9e-108">Realizar comprobaciones de manera proactiva, verificando que la configuración se establece de acuerdo con los procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="23d9e-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="23d9e-109">Detectar automáticamente las actualizaciones necesarias para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="23d9e-110">Genere una lista de problemas, como las opciones de configuración que no sean óptimas, las opciones no admitidas, las actualizaciones perdidas o los procedimientos que no recomendamos.</span><span class="sxs-lookup"><span data-stu-id="23d9e-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="23d9e-111">Ayuda para solucionar y corregir problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="23d9e-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="23d9e-112">El analizador de procedimientos recomendados proporciona las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="23d9e-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="23d9e-113">Requisitos mínimos de instalación.</span><span class="sxs-lookup"><span data-stu-id="23d9e-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="23d9e-114">Documentación en línea sobre problemas notificados, incluyendo sugerencias para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="23d9e-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="23d9e-115">Información de configuración que puede guardar para una revisión posterior.</span><span class="sxs-lookup"><span data-stu-id="23d9e-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="23d9e-116">Análisis del sistema de última generación.</span><span class="sxs-lookup"><span data-stu-id="23d9e-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="23d9e-117">El analizador de procedimientos recomendados usa un conjunto de archivos de configuración XML para determinar la información que se debe recopilar de su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="23d9e-118">Además de comprobar los servicios de dominio de Active Directory, comprueba fuentes como el registro del sistema operativo Windows Server y la configuración del instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="23d9e-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="23d9e-119">El analizador de procedimientos recomendados compara los datos que recopila con un conjunto de reglas predefinidas para la configuración y las configuraciones de las implementaciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="23d9e-120">Después de comparar los datos recopilados con las reglas predefinidas, la herramienta informa de los problemas.</span><span class="sxs-lookup"><span data-stu-id="23d9e-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="23d9e-121">Para cada problema que informa, el analizador de procedimientos recomendados proporciona información sobre lo que se encontró en el entorno de Lync Server 2013 y la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="23d9e-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="23d9e-122">El analizador de procedimientos recomendados también proporciona vínculos a información más detallada sobre los problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="23d9e-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d9e-123">Lync Server 2013, analizador de procedimientos recomendados, recopila información de configuración solo de componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d9e-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="23d9e-124">Puede usar las versiones anteriores de la herramienta para examinar entornos anteriores.</span><span class="sxs-lookup"><span data-stu-id="23d9e-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="23d9e-125">Para obtener más información, consulte <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">requisitos para ejecutar el analizador de procedimientos recomendados en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23d9e-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

