---
title: 'Lync Server 2013: implementación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5fcba91b3017faff29ad8d1bcce20d51a32bd1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498987"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="7ed3d-102">Implementación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-102">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ed3d-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="7ed3d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="7ed3d-104">La implementación del software de comunicaciones de Lync Server 2013 incluye la preparación de los servicios de dominio de Active Directory, la implementación de los servidores front-end y otros componentes internos de Lync Server 2013 principales y la implementación de los roles de servidor adicionales y las características que su organización puede necesitar, como el acceso de usuarios externos y la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="7ed3d-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="7ed3d-105">En esta documentación se describen tres escenarios para implementar Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="7ed3d-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="7ed3d-106">Nueva implementación de Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7ed3d-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="7ed3d-107">Nueva implementación de Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7ed3d-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="7ed3d-108">Nueva implementación de Lync Server 2013 Standard Edition o Enterprise Edition en una implementación existente de Lync Server 2010 Standard Edition o Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7ed3d-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="7ed3d-109">Para obtener información acerca de la implementación de Lync Server 2013 en un entorno de Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2 existente, consulte la documentación de [migración](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="7ed3d-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ed3d-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7ed3d-110">In This Section</span></span>

  - [<span data-ttu-id="7ed3d-111">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="7ed3d-112">Implementar el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="7ed3d-113">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="7ed3d-114">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="7ed3d-115">Implementación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="7ed3d-116">Configurar las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="7ed3d-117">Planeación e implementación de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="7ed3d-118">Implementación de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="7ed3d-119">Implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="7ed3d-120">Implementación de clientes y dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="7ed3d-121">Planeación e implementación de almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="7ed3d-122">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="7ed3d-123">Actualización de la versión de evaluación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="7ed3d-124">Implementación del control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="7ed3d-125">Implementación de la movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="7ed3d-126">Configuración de la integración con Office Web Apps Server y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="7ed3d-127">Configuración de mantenimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ed3d-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

