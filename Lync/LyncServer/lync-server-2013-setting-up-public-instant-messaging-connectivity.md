---
title: 'Lync Server 2013: configuración de conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="ae1d3-102">Configuración de la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae1d3-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae1d3-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ae1d3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ae1d3-p101">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, no puede usar al Asistente para la implementación de Lync Server para solicitar el certificado. En su lugar, realice los pasos del siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="ae1d3-106">Configuración de la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="ae1d3-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="ae1d3-p102">En un servidor front-end, abra el Generador de topologías. Expanda grupos perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales. Seleccione Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="ae1d3-p103">En Editar propiedades en General, seleccione Habilitar federación para este grupo de servidores perimetrales (Puerto 5061). Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="ae1d3-p104">Haga clic en Acción, seleccione Topología y, finalmente, Publicar. Cuando se le solicite en Publicar la topología, seleccione Siguiente. Una vez completado el proceso de publicación, haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="ae1d3-p105">En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en Instalar o en Actualizar Lync Server System y, a continuación, en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar nuevamente.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="ae1d3-p106">En los componentes de Lync Server de instalación, haga clic en Siguiente. La pantalla de resumen mostrará las acciones que se ejecutan. Una vez que se termine la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="ae1d3-122">Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para que admita la conectividad de mensajería instantánea pública con AOL</span><span class="sxs-lookup"><span data-stu-id="ae1d3-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="ae1d3-123">Cuando la plantilla requerida está disponible para la entidad emisora de certificados, utilice el siguiente cmdlet de Windows PowerShell de en el servidor perimetral para solicitar el certificado</span><span class="sxs-lookup"><span data-stu-id="ae1d3-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="ae1d3-124">El nombre de certificado predeterminado de la plantilla usada para Lync Server es servidor Web.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="ae1d3-125">Especifique el nombre \<\> de la plantilla solo si necesita usar una plantilla que sea diferente de la plantilla predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ae1d3-126">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del Asistente para certificados para solicitar que el certificado se asigne al perímetro externo para el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="ae1d3-127">Esto es porque la plantilla de la entidad emisora de certificados (CA) de servidor Web que utiliza el Asistente para certificados para solicitar un certificado no es compatible con la configuración del cliente de EKU.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="ae1d3-128">Antes de usar Windows PowerShell para crear el certificado, el administrador de la entidad de certificación debe crear e implementar una nueva plantilla que admita EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="ae1d3-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

