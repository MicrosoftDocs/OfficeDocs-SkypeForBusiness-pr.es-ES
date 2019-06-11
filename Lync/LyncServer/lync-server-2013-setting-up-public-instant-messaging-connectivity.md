---
title: 'Lync Server 2013: Establecer conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="054d0-102">Establecer conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="054d0-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="054d0-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="054d0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="054d0-104">Si su organización desea admitir la conectividad de mensajería instantánea (mi) pública con AOL, no puede usar el Asistente para la implementación de Lync Server para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="054d0-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="054d0-105">En su lugar, realice los pasos del procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="054d0-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="054d0-106">Configuración de la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="054d0-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="054d0-107">En un servidor front-end, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="054d0-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="054d0-108">Expanda agrupaciones perimetrales y haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="054d0-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="054d0-109">Seleccione Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="054d0-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="054d0-110">En propiedades de edición, en general, seleccione Habilitar Federación para este grupo perimetral (puerto 5061).</span><span class="sxs-lookup"><span data-stu-id="054d0-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="054d0-111">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="054d0-111">Click OK.</span></span>

3.  <span data-ttu-id="054d0-112">Haga clic en acción, seleccione topología, seleccione publicar.</span><span class="sxs-lookup"><span data-stu-id="054d0-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="054d0-113">Cuando se le solicite al publicar la topología, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="054d0-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="054d0-114">Una vez finalizada la publicación, haga clic en finalizar.</span><span class="sxs-lookup"><span data-stu-id="054d0-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="054d0-115">En el servidor perimetral, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="054d0-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="054d0-116">Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="054d0-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="054d0-117">Vuelva a hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="054d0-117">Click Run Again.</span></span>

5.  <span data-ttu-id="054d0-118">En instalación de los componentes de Lync Server, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="054d0-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="054d0-119">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="054d0-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="054d0-120">Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="054d0-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="054d0-121">Haga clic en finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="054d0-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="054d0-122">Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL</span><span class="sxs-lookup"><span data-stu-id="054d0-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="054d0-123">Cuando la plantilla requerida esté disponible para la CA, use el siguiente cmdlet de Windows PowerShell de en el servidor perimetral para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="054d0-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="054d0-124">El nombre de certificado predeterminado de la plantilla usada para Lync Server es servidor Web.</span><span class="sxs-lookup"><span data-stu-id="054d0-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="054d0-125">Especifique el nombre \<\> de la plantilla únicamente si necesita usar una plantilla distinta de la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="054d0-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="054d0-126">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del asistente de certificados para solicitar que el certificado se asigne al borde externo del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="054d0-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="054d0-127">Esto se debe a que la plantilla de servidor Web de la entidad de certificación (CA) que usa el Asistente para solicitar un certificado no admite la configuración de EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="054d0-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="054d0-128">Antes de usar Windows PowerShell para crear el certificado, el administrador de la CA debe crear e implementar una nueva plantilla que admita EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="054d0-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

