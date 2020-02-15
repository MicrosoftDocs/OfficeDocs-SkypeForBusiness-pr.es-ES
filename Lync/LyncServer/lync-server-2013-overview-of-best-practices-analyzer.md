---
title: 'Lync Server 2013: información general sobre el analizador de procedimientos recomendados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85bee37f748f0356458770c742f26e704132ad6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="fad22-102">Información general sobre el analizador de procedimientos recomendados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fad22-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fad22-103">_**Última modificación del tema:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="fad22-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="fad22-104">Puede usar Lync Server 2013, Best Practices Analyzer para identificar y resolver los problemas con la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="fad22-105">El analizador de procedimientos recomendados de Lync Server 2013 recopila información de configuración de los componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="fad22-106">Con el acceso a la red adecuado, el analizador de procedimientos recomendados puede examinar los servidores que ejecutan servicios de dominio de Active Directory, mensajería unificada de Exchange Server (MU) y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="fad22-107">Puede usar el Analizador de procedimientos recomendados para realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="fad22-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="fad22-108">Efectuar comprobaciones de forma proactiva, que comprueben si la configuración se ha definido según los mejores procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="fad22-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="fad22-109">Detectar automáticamente las actualizaciones necesarias para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="fad22-110">Generar una lista de cuestiones, como valores de configuración inferiores a los óptimos, opciones no compatibles, actualizaciones que faltan o procedimientos no recomendados.</span><span class="sxs-lookup"><span data-stu-id="fad22-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="fad22-111">Ayudar a solucionar problemas y resolver problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="fad22-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="fad22-112">El Analizador de procedimientos recomendados dispone de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="fad22-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="fad22-113">Requisitos previos de instalación mínimos.</span><span class="sxs-lookup"><span data-stu-id="fad22-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="fad22-114">Documentación en línea sobre las cuestiones notificadas, como sugerencias para la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="fad22-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="fad22-115">Información de configuración que se puede guardar para repasarla posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fad22-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="fad22-116">Análisis del sistema de última generación.</span><span class="sxs-lookup"><span data-stu-id="fad22-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="fad22-117">El analizador de procedimientos recomendados usa un conjunto de archivos de configuración XML para determinar la información que se va a recopilar de su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="fad22-118">Además de comprobar los Servicios de dominio de Active Directory, también comprueba orígenes como la configuración y el registro del sistema operativo de Windows Server en Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="fad22-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="fad22-119">El analizador de procedimientos recomendados compara los datos que recopila con un conjunto de reglas predefinidas para la configuración y las configuraciones de las implementaciones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="fad22-120">Después de comparar los datos recopilados con las reglas predefinidas, la herramienta notifica los problemas.</span><span class="sxs-lookup"><span data-stu-id="fad22-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="fad22-121">Para cada problema que informa, el analizador de procedimientos recomendados proporciona información sobre lo que se encontró en el entorno de Lync Server 2013 examinado y la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="fad22-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="fad22-122">También proporciona vínculos a información más detallada sobre los problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="fad22-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fad22-123">El analizador de procedimientos recomendados de Lync Server 2013 recopila información de configuración solo de los componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fad22-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="fad22-124">Puede usar las versiones anteriores de la herramienta para explorar entornos anteriores.</span><span class="sxs-lookup"><span data-stu-id="fad22-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="fad22-125">Para obtener información detallada, consulte <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for Running Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fad22-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

