---
title: 'Lync Server 2013: configuración de anuncios para números sin asignar'
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
ms.openlocfilehash: 6442ed90050df22df77c41773619bedb5ee3ff72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="b1333-102">Configuración de anuncios para números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1333-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="b1333-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="b1333-104">La aplicación de anuncio es una característica de Enterprise Voice que permite configurar lo que ocurre con las llamadas a extensiones sin asignar (extensiones que son válidas para la organización, pero que no están asignadas a una persona o un teléfono).</span><span class="sxs-lookup"><span data-stu-id="b1333-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="b1333-105">Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="b1333-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="b1333-106">La aplicación de anuncio se instala como una característica de la aplicación de grupo de respuesta en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b1333-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b1333-107">Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="b1333-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="b1333-108">Esta sección le guiará a través de la configuración de los anuncios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b1333-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="b1333-109">Se da por hecho que ya ha leído las secciones de planeación relacionadas con los anuncios y ha implementado un servidor Enterprise Edition o un servidor Standard Edition con Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b1333-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b1333-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b1333-110">In This Section</span></span>

  - [<span data-ttu-id="b1333-111">Requisitos previos y roles de configuración del anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="b1333-112">Proceso de implementación de la aplicación de anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="b1333-113">Crear un anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="b1333-114">Configurar la tabla de números sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="b1333-115">Opcional Comprobar la implementación del anuncio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1333-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1333-116">See Also</span></span>


[<span data-ttu-id="b1333-117">Planeación de características de administración de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1333-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

