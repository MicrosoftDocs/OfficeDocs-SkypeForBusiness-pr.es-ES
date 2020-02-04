---
title: 'Lync Server 2013: Compatibilidad de servicios de dominio de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="8429f-102">Compatibilidad de servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8429f-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8429f-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8429f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8429f-104">Lync Server 2013 usa el almacén de administración central para almacenar los datos de configuración de servidores y servicios, en lugar de depender de los servicios de dominio de Active Directory para esta información, como en el pasado.</span><span class="sxs-lookup"><span data-stu-id="8429f-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="8429f-105">Lync Server 2013 sigue almacenando lo siguiente en AD DS:</span><span class="sxs-lookup"><span data-stu-id="8429f-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="8429f-106">**Extensiones de esquema**</span><span class="sxs-lookup"><span data-stu-id="8429f-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="8429f-107">Extensiones de objetos de usuario</span><span class="sxs-lookup"><span data-stu-id="8429f-107">User object extensions</span></span>
    
      - <span data-ttu-id="8429f-108">Extensiones de Lync Server 2010 y las clases de Office Communications Server 2007 R2 para mantener la compatibilidad con versiones anteriores compatibles</span><span class="sxs-lookup"><span data-stu-id="8429f-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="8429f-109">**Datos** (almacenados en el esquema extendido de Lync Server 2013 y en las clases existentes)</span><span class="sxs-lookup"><span data-stu-id="8429f-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="8429f-110">URI de SIP del usuario y otros parámetros de usuario</span><span class="sxs-lookup"><span data-stu-id="8429f-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="8429f-111">Objetos de contacto para aplicaciones (por ejemplo, la aplicación de grupo de respuesta y la aplicación de operador de conferencia)</span><span class="sxs-lookup"><span data-stu-id="8429f-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="8429f-112">Datos publicados para la compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="8429f-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="8429f-113">Un punto de control de servicio (SCP) para el almacén de administración central</span><span class="sxs-lookup"><span data-stu-id="8429f-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="8429f-114">Cuenta de autenticación Kerberos (un objeto de equipo opcional)</span><span class="sxs-lookup"><span data-stu-id="8429f-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="8429f-115">En esta sección se describen los requisitos de compatibilidad de AD DS para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8429f-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="8429f-116">Para obtener más información sobre la compatibilidad de topología, consulte [topologías de Active Directory admitidas en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8429f-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="8429f-117">Sistemas operativos de controlador de dominio compatibles</span><span class="sxs-lookup"><span data-stu-id="8429f-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="8429f-118">Lync Server 2013 admite controladores de dominio que ejecutan los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="8429f-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="8429f-119">Sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8429f-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="8429f-120">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8429f-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="8429f-121">Sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8429f-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="8429f-122">Sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8429f-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="8429f-123">Windows Server 2008 Enterprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="8429f-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="8429f-124">Las versiones de 32 o 64 bits del sistema operativo Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="8429f-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="8429f-125">Las versiones de 32 o 64 bits del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="8429f-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="8429f-126">Nivel funcional de bosque y dominio</span><span class="sxs-lookup"><span data-stu-id="8429f-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="8429f-127">Debe elevar todos los dominios en los que implementa Lync Server 2013 a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8429f-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="8429f-128">Todos los bosques en los que implemente Lync Server 2013 deben elevarse al nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o al menos Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="8429f-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="8429f-129">Compatibilidad con controladores de dominio de solo lectura</span><span class="sxs-lookup"><span data-stu-id="8429f-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="8429f-130">Lync Server 2013 admite implementaciones de servicios de dominio de Active Directory que incluyen controladores de dominio de solo lectura o servidores de catálogo global de solo lectura, siempre que haya controladores de dominio de escritura disponibles.</span><span class="sxs-lookup"><span data-stu-id="8429f-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="8429f-131">Nombres de dominio</span><span class="sxs-lookup"><span data-stu-id="8429f-131">Domain Names</span></span>

<span data-ttu-id="8429f-132">Lync Server no es compatible con los dominios con etiqueta única.</span><span class="sxs-lookup"><span data-stu-id="8429f-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="8429f-133">Por ejemplo, un bosque con un dominio raíz denominado **contoso. local** es compatible, pero no se admite un dominio raíz denominado **local** .</span><span class="sxs-lookup"><span data-stu-id="8429f-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="8429f-134">Para obtener más información, consulte el artículo 300684 de Microsoft Knowledge base, "información sobre la configuración de Windows para dominios con nombres DNS [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)de etiqueta única" en.</span><span class="sxs-lookup"><span data-stu-id="8429f-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8429f-135">Lync Server no permite cambiar el nombre de los dominios.</span><span class="sxs-lookup"><span data-stu-id="8429f-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="8429f-136">Si necesita cambiar el nombre de un dominio donde se ha implementado Lync Server, primero debe desinstalar Lync Server, después cambiar el nombre del dominio y, a continuación, volver a instalar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8429f-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="8429f-137">Entornos AD DS bloqueados</span><span class="sxs-lookup"><span data-stu-id="8429f-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="8429f-138">En un entorno de AD DS bloqueado, los usuarios y los objetos de equipos a menudo se colocan en unidades organizativas (OU) específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y habilitar el uso de objetos de directiva de grupo (GPO) para aplicar directivas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8429f-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="8429f-139">Lync Server 2013 se puede implementar en un entorno de Active Directory bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8429f-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="8429f-140">Para obtener más información sobre lo que se necesita para implementar Lync Server en un entorno bloqueado, consulte [preparar los servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="8429f-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

