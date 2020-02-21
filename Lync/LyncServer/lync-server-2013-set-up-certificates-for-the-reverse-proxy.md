---
title: 'Lync Server 2013: configurar certificados para el proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c7a4e6ede9afe8d521d8dea3bd9350801588b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="b532d-102">Configurar certificados para el proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b532d-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b532d-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b532d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b532d-p101">Todos los servidores proxy inversos requieren un certificado de servidor web para usarlos en el servicio de escucha. El certificado de servidor web debe ser emitido por una entidad de certificación (CA) pública.</span><span class="sxs-lookup"><span data-stu-id="b532d-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="b532d-106">Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="b532d-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="b532d-107">Para configurar un certificado de servicios web para el servidor proxy inverso</span><span class="sxs-lookup"><span data-stu-id="b532d-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="b532d-108">Debe haber configurado previamente el servidor proxy inverso, incluida la configuración del certificado de servicios web.</span><span class="sxs-lookup"><span data-stu-id="b532d-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="b532d-109">Si no lo hizo antes de iniciar la implementación de los servidores perimetrales, use los procedimientos descritos en Configuring [Reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para crear una solicitud e instalar el certificado de servicios web y, a continuación, cree cada regla de publicación web y configúrela para usar el certificado.</span><span class="sxs-lookup"><span data-stu-id="b532d-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

