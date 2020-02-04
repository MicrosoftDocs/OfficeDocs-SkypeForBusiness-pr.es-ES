---
title: 'Lync Server 2013: Configuración de anuncios para números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d7e8ad1aa4fcfe3db9aabee61e317810707194
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="85089-102">Configuración de anuncios para números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85089-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="85089-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="85089-104">La aplicación de anuncios es una característica de voz empresarial que le permite configurar lo que sucede con las llamadas a extensiones no asignadas (extensiones que son válidas para su organización, pero que no están asignadas a una persona o teléfono).</span><span class="sxs-lookup"><span data-stu-id="85089-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="85089-105">Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="85089-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="85089-106">La aplicación de anuncios se instala como una característica de la aplicación de grupo de respuesta en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="85089-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="85089-107">Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="85089-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="85089-108">Esta sección le guiará a través de la configuración de los anuncios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85089-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="85089-109">Se da por hecho que ya ha leído las secciones de planificación relacionadas con los anuncios y ha implementado un servidor Enterprise Edition o un servidor Standard Edition con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="85089-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85089-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="85089-110">In This Section</span></span>

  - [<span data-ttu-id="85089-111">Requisitos previos y roles para configurar anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="85089-112">Proceso de implementación para la aplicación de anuncios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="85089-113">Crear un anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="85089-114">Configurar la tabla de números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="85089-115">Faculta Comprobar la implementación de la presentación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85089-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="85089-116">See Also</span></span>


[<span data-ttu-id="85089-117">Planeamiento de las características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85089-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

