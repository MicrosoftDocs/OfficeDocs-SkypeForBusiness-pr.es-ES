---
title: 'Lync Server 2013: implementar el portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a7f3589f809fa9dfcbfa872653fb4cb8161ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522917"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="18ffa-102">Implementación del portal web administrativo de Lync Room System en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ffa-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18ffa-103">_**Última modificación del tema:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="18ffa-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="18ffa-104">El portal web administrativo de Microsoft Lync Server 2013 Lync Room System (LRS) es un portal web que las organizaciones pueden usar para mantener sus salas de conferencias de Lync Room System.</span><span class="sxs-lookup"><span data-stu-id="18ffa-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="18ffa-105">Los administradores pueden usar el portal web administrativo LRS para supervisar el estado de LRS, por ejemplo, mediante la supervisión de los dispositivos de audio y vídeo que están conectados.</span><span class="sxs-lookup"><span data-stu-id="18ffa-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="18ffa-106">Con este portal, los administradores pueden recopilar información de diagnóstico de forma remota para supervisar el estado de la sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="18ffa-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="18ffa-107">El portal web administrativo LRS se implementa en cada servidor front-end de Lync.</span><span class="sxs-lookup"><span data-stu-id="18ffa-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="18ffa-108">En esta guía se proporcionan instrucciones para los administradores sobre cómo instalar y configurar el portal web administrativo LRS.</span><span class="sxs-lookup"><span data-stu-id="18ffa-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="18ffa-109">Está destinada a los administradores que tienen conocimiento de la administración de Lync Server y que tienen derechos de usuario administrador para modificar la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18ffa-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="18ffa-110">Después de implementar el portal web administrativo de LRS en el servidor, los administradores pueden comprobar el estado de todos los salones LRS iniciando sesión en el sitio desde sus propios equipos o portátiles.</span><span class="sxs-lookup"><span data-stu-id="18ffa-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18ffa-111">Al instalar el portal web administrativo LRS en una implementación de Microsoft Lync Server 2013, debe usar el <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">portal web administrativo del sistema Microsoft Lync Room para Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="18ffa-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="18ffa-112">Hay disponible una nueva versión del portal web administrativo LRS para Skype empresarial Server 2015, pero no se debe instalar esta versión a menos que haya implementado Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="18ffa-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="18ffa-113">Descargue el <A href="https://go.microsoft.com/fwlink/?linkid=544807">portal web administrativo del sistema Microsoft Lync Room para Skype empresarial Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="18ffa-113">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="18ffa-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="18ffa-114">In This Section</span></span>

[<span data-ttu-id="18ffa-115">Configuración del entorno de Lync Server 2013 para el portal web administrativo del sistema Lync Room</span><span class="sxs-lookup"><span data-stu-id="18ffa-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="18ffa-116">Instalación del portal web administrativo del sistema Lync Room en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ffa-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="18ffa-117">Usar el portal web administrativo del sistema Lync Room en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ffa-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18ffa-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18ffa-118">See Also</span></span>


[<span data-ttu-id="18ffa-119">Implementación de conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ffa-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

