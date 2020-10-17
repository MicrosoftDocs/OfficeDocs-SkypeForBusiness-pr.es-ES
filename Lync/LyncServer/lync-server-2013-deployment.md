---
title: 'Lync Server 2013: implementación'
description: 'Lync Server 2013: implementación.'
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
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555366"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="dbc5e-103">Implementación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc5e-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="dbc5e-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="dbc5e-105">La implementación del software de comunicaciones de Lync Server 2013 incluye la preparación de los servicios de dominio de Active Directory, la implementación de los servidores front-end y otros componentes internos de Lync Server 2013 principales y la implementación de los roles de servidor adicionales y las características que su organización puede necesitar, como el acceso de usuarios externos y la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dbc5e-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="dbc5e-106">En esta documentación se describen tres escenarios para implementar Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="dbc5e-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="dbc5e-107">Nueva implementación de Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dbc5e-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="dbc5e-108">Nueva implementación de Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="dbc5e-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="dbc5e-109">Nueva implementación de Lync Server 2013 Standard Edition o Enterprise Edition en una implementación existente de Lync Server 2010 Standard Edition o Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dbc5e-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="dbc5e-110">Para obtener información acerca de la implementación de Lync Server 2013 en un entorno de Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2 existente, consulte la documentación de [migración](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="dbc5e-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dbc5e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dbc5e-111">In This Section</span></span>

  - [<span data-ttu-id="dbc5e-112">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="dbc5e-113">Implementar el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="dbc5e-114">Implementar la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="dbc5e-115">Implementación de la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="dbc5e-116">Implementación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="dbc5e-117">Configurar las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="dbc5e-118">Planeación e implementación de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="dbc5e-119">Implementación de sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="dbc5e-120">Implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="dbc5e-121">Implementación de clientes y dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="dbc5e-122">Planeación e implementación de almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="dbc5e-123">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="dbc5e-124">Actualización de la versión de evaluación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="dbc5e-125">Implementación del control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="dbc5e-126">Implementación de la movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="dbc5e-127">Configuración de la integración con Office Web Apps Server y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="dbc5e-128">Configuración de mantenimiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc5e-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

