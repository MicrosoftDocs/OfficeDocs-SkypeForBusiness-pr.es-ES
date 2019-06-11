---
title: 'Lync Server 2013: implementar el portal web administrativo del sistema de Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="eaaa2-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaaa2-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaaa2-103">_**Última modificación del tema:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="eaaa2-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="eaaa2-104">El portal web administrativo de Microsoft Lync Server 2013 Lync Room System (LRS) es un portal web que las organizaciones pueden usar para mantener las salas de conferencias del sistema de la sala de Lync.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="eaaa2-105">Los administradores pueden usar el portal web administrativo LRS para supervisar el estado LRS, por ejemplo, mediante la supervisión de los dispositivos de audio o vídeo que están conectados.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="eaaa2-106">Con este portal, los administradores también pueden recopilar información de diagnóstico de forma remota para supervisar el estado de las salas de conferencias.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="eaaa2-107">El portal web administrativo LRS se implementa en todos los servidores front-end de Lync.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="eaaa2-108">Esta guía proporciona instrucciones para los administradores sobre cómo instalar y configurar el portal web administrativo LRS.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="eaaa2-109">Está destinada a los administradores que tienen conocimiento de la administración de Lync Server y que tienen derechos de usuario administrador para modificar la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="eaaa2-110">Después de implementar el portal web administrativo de LRS en el servidor, los administradores pueden comprobar el estado de todos los salones LRS iniciando sesión en el sitio desde sus propios equipos o portátiles.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eaaa2-111">Al instalar el portal web administrativo LRS en una implementación de Microsoft Lync Server 2013, debe usar el <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portal web administrativo del sistema de Microsoft Lync para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="eaaa2-112">Hay una nueva versión del portal web administrativo de LRS disponible para Skype empresarial Server 2015, pero no debe instalar esta versión a menos que haya implementado Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="eaaa2-113">Descargue el <A href="http://go.microsoft.com/fwlink/?linkid=544807">portal web administrativo del sistema de Microsoft Lync Room para Skype empresarial Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="eaaa2-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eaaa2-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eaaa2-114">In This Section</span></span>

[<span data-ttu-id="eaaa2-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="eaaa2-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="eaaa2-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaaa2-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="eaaa2-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaaa2-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eaaa2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaaa2-118">See Also</span></span>


[<span data-ttu-id="eaaa2-119">Implementar conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaaa2-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

