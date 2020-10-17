---
title: 'Lync Server 2013: administración de la configuración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de390f21c76a9636fc9ba2d6a7d3ee017681b6ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507837"
---
# <a name="configuration-management-in-lync-server-2013"></a><span data-ttu-id="41c26-102">Administración de la configuración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41c26-102">Configuration management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41c26-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="41c26-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="41c26-104">La administración de la configuración es el proceso de registrar y realizar un seguimiento de los activos de hardware y software y la información de configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="41c26-104">Configuration management is the process of recording and tracking hardware and software assets and system configuration information.</span></span> <span data-ttu-id="41c26-105">Por lo general, se usa para realizar un seguimiento de las licencias de software, mantener una compilación estándar de hardware y software para los equipos cliente y los servidores, y definir los estándares de nomenclatura para nuevos equipos.</span><span class="sxs-lookup"><span data-stu-id="41c26-105">It is generally used to track software licenses, maintain a standard hardware and software build for client computers and servers, and define naming standards for new computers.</span></span> <span data-ttu-id="41c26-106">La administración de la configuración generalmente abarca las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="41c26-106">Configuration management generally covers the following categories:</span></span>

  - <span data-ttu-id="41c26-107">**Hardware**     Esta categoría realiza un seguimiento de las piezas de equipamiento que posee la organización de ti, Dónde está ubicado el equipo y quién usa el equipo.</span><span class="sxs-lookup"><span data-stu-id="41c26-107">**Hardware**   This category tracks the pieces of equipment that the IT organization owns, where equipment is located, and who uses equipment.</span></span> <span data-ttu-id="41c26-108">Esta información permite a una organización planear y presupuestar las actualizaciones, mantener compilaciones de hardware estándar, informar sobre el valor de los activos de TI con fines de contabilidad y ayudar a evitar el robo.</span><span class="sxs-lookup"><span data-stu-id="41c26-108">This information enables an organization to plan and budget for upgrades, maintain standard hardware builds, report on the value of IT assets for accounting purposes, and help prevent theft.</span></span>

  - <span data-ttu-id="41c26-109">**Software**     de Esta categoría realiza un seguimiento del software instalado en cada equipo, los números de versión y el lugar donde se encuentran las licencias.</span><span class="sxs-lookup"><span data-stu-id="41c26-109">**Software**   This category tracks software that is installed on each computer, the version numbers, and where the licenses are held.</span></span> <span data-ttu-id="41c26-110">Esta información ayuda a planear actualizaciones, garantizar que el software tiene una licencia y detectar la presencia de software no autorizado (y sin licencia).</span><span class="sxs-lookup"><span data-stu-id="41c26-110">This information helps plan upgrades, to ensure that software is licensed, and detect the presence of unauthorized (and unlicensed) software.</span></span>

  - <span data-ttu-id="41c26-111">**Compilaciones estándar**     Esta categoría realiza un seguimiento de la compilación estándar actual para los equipos cliente y los servidores, y si los equipos cliente y los servidores cumplen este estándar.</span><span class="sxs-lookup"><span data-stu-id="41c26-111">**Standard Builds**   This category tracks the current standard build for the client computers and servers and whether the client computers and servers meet this standard.</span></span> <span data-ttu-id="41c26-112">Definir e imponer compilaciones estándar ayuda al personal de soporte técnico, ya que el personal debe mantener un número limitado de versiones de cada elemento de software.</span><span class="sxs-lookup"><span data-stu-id="41c26-112">Defining and enforcing standard builds helps support staff because the staff is required to maintain only a limited number of versions of each piece of software.</span></span>

  - <span data-ttu-id="41c26-113">**Actualizaciones acumulativas y revisiones**     Esta categoría realiza un seguimiento de los Service Pack que se han probado y aprobado para su uso y los equipos que están actualizados.</span><span class="sxs-lookup"><span data-stu-id="41c26-113">**Cumulative Updates and Hotfixes**   This category tracks which service packs are tested and approved for use and which computers are up to date.</span></span> <span data-ttu-id="41c26-114">Esta información es importante para reducir el riesgo de que los equipos se pongan en peligro y para detectar los usuarios que han instalado actualizaciones no aprobadas.</span><span class="sxs-lookup"><span data-stu-id="41c26-114">This information is important to reduce the risk of computers being compromised and to detect users who have installed unapproved updates.</span></span>

  - <span data-ttu-id="41c26-115">Información de configuración **del sistema**     Esta categoría realiza un seguimiento de la función de un sistema, la interacción entre los elementos del sistema y los procesos que dependen de un sistema que se ejecuta sin problemas.</span><span class="sxs-lookup"><span data-stu-id="41c26-115">**System Configuration Information**   This category tracks the function of a system, the interaction between system elements, and the processes that depend on a system that is running smoothly.</span></span> <span data-ttu-id="41c26-116">Por ejemplo, se puede configurar un servidor proxy de terceros en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="41c26-116">For example, third-party proxy server may be configured on a single server.</span></span> <span data-ttu-id="41c26-117">Se debe comprender la dependencia del servidor proxy en este servidor y es posible que se necesiten planes de contingencia si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="41c26-117">The proxy server’s dependence on this server should be understood and contingency plans may be required if there is a failure.</span></span> <span data-ttu-id="41c26-118">Si el servidor proxy se puede configurar para que también se comunique con otro servidor front-end, es probable que cambien las dependencias y los planes de contingencia.</span><span class="sxs-lookup"><span data-stu-id="41c26-118">If the proxy server can be configured to also communicate with another front-end server, dependencies and contingency plans will probably change.</span></span>

<div>

## <a name="implementing-configuration-management"></a><span data-ttu-id="41c26-119">Implementación de la administración de la configuración</span><span class="sxs-lookup"><span data-stu-id="41c26-119">Implementing configuration management</span></span>

<span data-ttu-id="41c26-120">Después de determinar qué elementos necesitan administrar, implemente la administración de la configuración mediante la recopilación de datos y datos de informes.</span><span class="sxs-lookup"><span data-stu-id="41c26-120">After you determine what items need managing, implement configuration management by collecting data and reporting data.</span></span> <span data-ttu-id="41c26-121">El método más sencillo para las organizaciones pequeñas es recopilar datos manualmente (número y modelo de equipos cliente, sistema operativo, software instalado) y guardarlos en un documento de Office Word u Office Excel.</span><span class="sxs-lookup"><span data-stu-id="41c26-121">The simplest approach for small organizations is to collect data manually (number and model of client computers, operating system, installed software) and save it in an Office Word or Office Excel document.</span></span> <span data-ttu-id="41c26-122">Para sistemas de mayor tamaño, más complejo y constante cambio, se debe automatizar el descubrimiento de activos y la recopilación de información detallada.</span><span class="sxs-lookup"><span data-stu-id="41c26-122">For larger, more complex, and constantly changing systems, the discovery of assets and collection of detailed information must be automated.</span></span> <span data-ttu-id="41c26-123">Decida qué información es relevante para su organización y guárdela en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="41c26-123">Decide what information is relevant to your organization and record it in a database.</span></span>

<span data-ttu-id="41c26-124">La base de datos de administración de la configuración es una herramienta útil para el personal de soporte técnico y la administración en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="41c26-124">The configuration management database is a useful tool for support staff and management in the following areas:</span></span>

  - <span data-ttu-id="41c26-125">**Auditorías**     de seguridad La base de datos le permite identificar los servidores que ejecutan Lync Server y los sistemas informáticos que deben tener revisiones aplicadas o que no han podido instalar un Service Pack o las actualizaciones más recientes de antivirus.</span><span class="sxs-lookup"><span data-stu-id="41c26-125">**Security Audits**   The database enables you to identify servers that are running Lync Server and client computer systems that must have hotfixes applied or that have missed the installation of a service pack or the latest antivirus updates.</span></span>

  - <span data-ttu-id="41c26-126">**Instalación**     de software Identificar las versiones de software de cliente y realizar un seguimiento de ellas ayudará a los administradores a planear actualizaciones de la versión y nuevas instalaciones, además de ayudarle con la documentación de licencias y el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="41c26-126">**Software Installation**   Identifying client software versions and tracking them will aid administrators in planning version updates and new installs and also by helping with licensing documentation and compliance.</span></span>

  - <span data-ttu-id="41c26-127">**Información**     de configuración Si mantiene una lista actualizada de todas las opciones de configuración que se cambiaron de forma predeterminada, podrá solucionar problemas de forma rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="41c26-127">**Configuration Information**   If you maintain an up-to-date list of all settings that were changed from their default, then you'll be able to troubleshoot issues quickly and more effectively.</span></span>

  - <span data-ttu-id="41c26-128">**Planeación de actualizaciones**     Si una revisión de capacidad revela que es necesario disponer de espacio de almacenamiento adicional en los servidores de base de datos de Lync, es importante saber si cada servidor tiene un controlador RAID interno.</span><span class="sxs-lookup"><span data-stu-id="41c26-128">**Planning Upgrades**   If a capacity review reveals that additional storage space is required on your Lync database servers, it’s important to know whether each server has an internal RAID controller.</span></span> <span data-ttu-id="41c26-129">Si es así, ¿son el mismo modelo?</span><span class="sxs-lookup"><span data-stu-id="41c26-129">If they do, then are they the same model?</span></span> <span data-ttu-id="41c26-130">¿Tienen el mismo número de discos instalados?</span><span class="sxs-lookup"><span data-stu-id="41c26-130">Do they have the same number of disks installed?</span></span> <span data-ttu-id="41c26-131">La base de datos de administración de la configuración indicará el tipo de disco que se puede instalar, el número y la ruta de actualización en cada caso.</span><span class="sxs-lookup"><span data-stu-id="41c26-131">The configuration management database will indicate the type of disk that can be installed, the number, and the upgrade path in each case.</span></span>

</div>

<div>

## <a name="tools-used-for-configuration-management"></a><span data-ttu-id="41c26-132">Herramientas usadas para la administración de la configuración</span><span class="sxs-lookup"><span data-stu-id="41c26-132">Tools used for configuration management</span></span>

<span data-ttu-id="41c26-133">Hay muchas herramientas para descubrir, auditar y reportar activos.</span><span class="sxs-lookup"><span data-stu-id="41c26-133">There are many tools to discover, audit, and report assets.</span></span> <span data-ttu-id="41c26-134">Algunas de estas herramientas se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="41c26-134">Some of these tools are discussed in this section.</span></span>

  - <span data-ttu-id="41c26-135">**Scripts**     automatizados Puede escribir scripts sencillos para notificar elementos como el sistema operativo, el nivel de Service Pack y si hay software en un conjunto específico de equipos.</span><span class="sxs-lookup"><span data-stu-id="41c26-135">**Automated Scripts**   You can write simple scripts to report items such as the operating system, service pack level, and whether software exists on a specific set of computers.</span></span> <span data-ttu-id="41c26-136">Puede escribir estos scripts para los requisitos exactos de una organización.</span><span class="sxs-lookup"><span data-stu-id="41c26-136">You can write these scripts to an organization’s exact requirements.</span></span> <span data-ttu-id="41c26-137">Sin embargo, el número necesario de scripts y su complejidad puede hacer que los scripts sean caros de crear y mantener.</span><span class="sxs-lookup"><span data-stu-id="41c26-137">However, the required number of scripts and their complexity can make scripts expensive to create and maintain.</span></span>

  - <span data-ttu-id="41c26-138">**Herramientas**     automatizadas Según el tamaño de su empresa y las necesidades de su organización, es posible que quiera considerar el uso de herramientas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="41c26-138">**Automated Tools**   Depending on the size of your business and your organizational needs, you may want to consider using automated tools.</span></span> <span data-ttu-id="41c26-139">Herramientas como Microsoft Endpoint Configuration Manager incorporan plantillas de informes estándar (como el nivel de Service Pack) y también permiten crear informes personalizados, por ejemplo, para una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="41c26-139">Tools such as Microsoft Endpoint Configuration Manager incorporate standard report templates (such as service pack level) and also enable you to create customized reports, for example, for a custom application.</span></span> <span data-ttu-id="41c26-140">Microsoft Endpoint Configuration Manager también se puede usar para informar sobre las configuraciones de hardware y software.</span><span class="sxs-lookup"><span data-stu-id="41c26-140">The Microsoft Endpoint Configuration Manager can also be used to report on hardware and software configurations.</span></span>

</div>

<div>

## <a name="relationship-with-change-management"></a><span data-ttu-id="41c26-141">Relación con la administración de cambios</span><span class="sxs-lookup"><span data-stu-id="41c26-141">Relationship with change management</span></span>

<span data-ttu-id="41c26-142">La administración de la configuración está estrechamente relacionada con la administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="41c26-142">Configuration management is closely related to change management.</span></span> <span data-ttu-id="41c26-143">La administración de la configuración identifica la necesidad de cambiar e identifica y registra que se ha producido un cambio.</span><span class="sxs-lookup"><span data-stu-id="41c26-143">Configuration management identifies the need for change and identifies and records that a change has occurred.</span></span> <span data-ttu-id="41c26-144">Por ejemplo, la base de datos de administración de la configuración se puede usar para identificar los servidores que requieren una revisión.</span><span class="sxs-lookup"><span data-stu-id="41c26-144">For example, the configuration management database can be used to identify servers that require a hotfix.</span></span> <span data-ttu-id="41c26-145">A continuación, la administración de cambios define el proceso para aplicar la revisión.</span><span class="sxs-lookup"><span data-stu-id="41c26-145">Change management then defines the process for applying the hotfix.</span></span>

<span data-ttu-id="41c26-146">Por el contrario, si se implementa una nueva actualización acumulativa, el proceso de administración de cambios debe proporcionar esta información al sistema de administración de la configuración.</span><span class="sxs-lookup"><span data-stu-id="41c26-146">Conversely, if a new cumulative update is rolled out, the change management process should supply this information to the configuration management system.</span></span> <span data-ttu-id="41c26-147">Es probable que las herramientas de administración de la configuración tengan que configurarse para identificar el nuevo software a fin de que puedan descubrir y realizar un seguimiento del lugar y el momento en que se implemente el software.</span><span class="sxs-lookup"><span data-stu-id="41c26-147">The configuration management tools will probably need to be configured to identify the new software so that they can discover and track where and when the software is deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

