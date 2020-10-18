---
title: 'Lync Server 2013: solicitar certificados de antemano (opcional)'
description: 'Lync Server 2013: solicitar certificados de antemano (opcional).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579036"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="f6e29-103">Solicitar certificados de antemano (opcional) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6e29-103">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6e29-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f6e29-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f6e29-105">Los certificados son necesarios para todos los servidores internos que ejecutan Lync Server 2013, incluidos cada servidor front-end Enterprise Edition, un servidor Standard Edition, un director, un servidor perimetral y un servidor de mediación independiente.</span><span class="sxs-lookup"><span data-stu-id="f6e29-105">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="f6e29-106">Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública.</span><span class="sxs-lookup"><span data-stu-id="f6e29-106">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="f6e29-107">Para obtener más información sobre los requisitos de certificado y el uso de una entidad de certificación pública, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="f6e29-107">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="f6e29-108">El programa de instalación de Lync Server 2013 incluye el Asistente para certificados, que facilita las tareas de solicitar, asignar e instalar certificados durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f6e29-108">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="f6e29-109">Si desea solicitar certificados antes de instalar servidores (por ejemplo, para ahorrar tiempo durante la implementación real de servidores), puede hacerlo con un equipo en el que estén instaladas las herramientas administrativas de Lync Server 2013 o mediante un procedimiento de solicitud de certificado definido en la organización, siempre que se asegure de que los certificados son exportables y contienen todos los nombres alternativos de sujeto necesarios.</span><span class="sxs-lookup"><span data-stu-id="f6e29-109">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="f6e29-110">Solicitar certificados por adelantado es opcional.</span><span class="sxs-lookup"><span data-stu-id="f6e29-110">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="f6e29-111">Si no los solicita por adelantado, debe solicitarlos como parte de la configuración de cada servidor que requiera un certificado.</span><span class="sxs-lookup"><span data-stu-id="f6e29-111">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="f6e29-112">Esta documentación sobre la implementación proporciona procedimientos para usar el Asistente para certificados para solicitar certificados como parte del proceso de instalación, como se describe en [configurar certificados para servidores en Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para el Director en Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [instalar los archivos para el servidor de mediación en las secciones de Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de esta documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f6e29-112">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="f6e29-113">Si solicita certificados por adelantado, deberá modificar los procedimientos de implementación de certificados en estas secciones según convenga para importar y asignar los certificados, en lugar de solicitarlos durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="f6e29-113">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6e29-114">Lync Server 2013 incluye compatibilidad con certificados SHA-256 para conexiones de clientes que ejecutan los sistemas operativos Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 y Windows 7, y Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="f6e29-114">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="f6e29-115">Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="f6e29-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

