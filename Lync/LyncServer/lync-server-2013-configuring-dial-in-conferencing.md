---
title: 'Lync Server 2013: configurar conferencias de acceso telefónico local'
description: 'Lync Server 2013: configurar la Conferencia de acceso telefónico local.'
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
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557946"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="66d14-103">Configurar las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66d14-104">_**Última modificación del tema:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="66d14-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="66d14-105">Esta sección le guiará a través de la configuración de la Conferencia de acceso telefónico local 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66d14-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66d14-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="66d14-106">In This Section</span></span>

  - [<span data-ttu-id="66d14-107">Requisitos previos y permisos de configuración para conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="66d14-108">Lista de comprobación para la implementación de la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="66d14-109">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="66d14-110">Asegurarse de que los planes de marcado Lync Server 2013 tienen regiones asignadas</span><span class="sxs-lookup"><span data-stu-id="66d14-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="66d14-111">Opcional Comprobar la configuración de la Directiva de PIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="66d14-112">Configurar la Directiva de conferencias para el acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="66d14-113">Configurar los números de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="66d14-114">Opcional Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="66d14-115">Opcional Modificar la asignación de teclas para comandos DTMF en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="66d14-116">Opcional Habilitar y deshabilitar la Unión a Conferencia y dejar anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="66d14-117">Opcional Comprobar la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="66d14-118">Implementación del complemento de conferencia en línea para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="66d14-119">Configurar las opciones de cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="66d14-120">Recomenda Crear directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="66d14-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="66d14-121">Opcional Le damos la bienvenida a los usuarios a conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="66d14-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="66d14-122">Related Sections</span></span>

[<span data-ttu-id="66d14-123">Implementar Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d14-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

