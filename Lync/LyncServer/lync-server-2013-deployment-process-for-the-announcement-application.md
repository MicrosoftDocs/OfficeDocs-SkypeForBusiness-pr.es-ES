---
title: 'Lync Server 2013: proceso de implementación de la aplicación de anuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55e0c65bfbbed55a8d7f9c3be4f7a586581c2307
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="05d2d-102">Proceso de implementación de la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05d2d-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05d2d-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="05d2d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="05d2d-104">En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación de anuncio.</span><span class="sxs-lookup"><span data-stu-id="05d2d-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="05d2d-105">Debe implementar la telefonía IP empresarial antes de configurar los anuncios.</span><span class="sxs-lookup"><span data-stu-id="05d2d-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="05d2d-106">Los componentes requeridos por la aplicación de anuncio se instalan y habilitan al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="05d2d-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="05d2d-107">Proceso de implementación de anuncios</span><span class="sxs-lookup"><span data-stu-id="05d2d-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05d2d-108">Fase</span><span class="sxs-lookup"><span data-stu-id="05d2d-108">Phase</span></span></th>
<th><span data-ttu-id="05d2d-109">Pasos</span><span class="sxs-lookup"><span data-stu-id="05d2d-109">Steps</span></span></th>
<th><span data-ttu-id="05d2d-110">Roles</span><span class="sxs-lookup"><span data-stu-id="05d2d-110">Roles</span></span></th>
<th><span data-ttu-id="05d2d-111">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="05d2d-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05d2d-112">Configurar opciones de anuncio</span><span class="sxs-lookup"><span data-stu-id="05d2d-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="05d2d-113">Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS).</span><span class="sxs-lookup"><span data-stu-id="05d2d-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="05d2d-114">Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="05d2d-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="05d2d-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="05d2d-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="05d2d-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="05d2d-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="05d2d-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="05d2d-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="05d2d-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="05d2d-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="05d2d-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="05d2d-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="05d2d-120"><a href="lync-server-2013-create-an-announcement.md">Crear un anuncio en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="05d2d-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="05d2d-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar la tabla de números sin asignar en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="05d2d-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05d2d-122">Comprobar la implementación de anuncios</span><span class="sxs-lookup"><span data-stu-id="05d2d-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="05d2d-123">Escuche los anuncios para comprobar que la configuración funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="05d2d-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="05d2d-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Opcional Comprobar la implementación del anuncio en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="05d2d-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

