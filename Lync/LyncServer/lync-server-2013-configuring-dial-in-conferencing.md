---
title: 'Lync Server 2013: configurar conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990f22cc08d25d8b78263f4594d8345be5b29c5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="a14b6-102">Configurar las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a14b6-103">_**Última modificación del tema:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="a14b6-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="a14b6-104">Esta sección le guiará a través de la configuración de la Conferencia de acceso telefónico local 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a14b6-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a14b6-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a14b6-105">In This Section</span></span>

  - [<span data-ttu-id="a14b6-106">Requisitos previos y permisos de configuración para conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="a14b6-107">Lista de comprobación para la implementación de la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="a14b6-108">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="a14b6-109">Asegurarse de que los planes de marcado Lync Server 2013 tienen regiones asignadas</span><span class="sxs-lookup"><span data-stu-id="a14b6-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="a14b6-110">Opcional Comprobar la configuración de la Directiva de PIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="a14b6-111">Configurar la Directiva de conferencias para el acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="a14b6-112">Configurar los números de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="a14b6-113">Opcional Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="a14b6-114">Opcional Modificar la asignación de teclas para comandos DTMF en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="a14b6-115">Opcional Habilitar y deshabilitar la Unión a Conferencia y dejar anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="a14b6-116">Opcional Comprobar la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="a14b6-117">Implementación del complemento de conferencia en línea para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="a14b6-118">Configurar las opciones de cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="a14b6-119">Recomenda Crear directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="a14b6-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="a14b6-120">Opcional Le damos la bienvenida a los usuarios a conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="a14b6-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a14b6-121">Related Sections</span></span>

[<span data-ttu-id="a14b6-122">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a14b6-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

