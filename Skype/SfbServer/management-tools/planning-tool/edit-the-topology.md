---
title: Editar la topología en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Después de completar las preguntas de entrevista iniciales, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio. Para ello, en la página Topología global, haga clic con el botón secundario en el sitio que desea editar.
ms.openlocfilehash: 9a345c753195c32907d078d5ee4a267b8b96d6b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093188"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="58fcc-104">Editar la topología en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="58fcc-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="58fcc-105">Después de completar las preguntas de entrevista iniciales, puede editar el nombre de dominio completo (FQDN) y las direcciones IP del sitio.</span><span class="sxs-lookup"><span data-stu-id="58fcc-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="58fcc-106">Para ello, en la página **Topología global**, haga clic con el botón secundario en el sitio que desea editar.</span><span class="sxs-lookup"><span data-stu-id="58fcc-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="58fcc-107">La herramienta de planeación muestra la topología del sitio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="58fcc-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="58fcc-108">En la parte inferior de la página del sitio hay cuatro pestañas:</span><span class="sxs-lookup"><span data-stu-id="58fcc-108">At the bottom of the site page are four tabs:</span></span>

![Topología de sitio de herramienta de planeación](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="58fcc-110">Topología de sitio: la página que se muestra actualmente con una visión general visual de la topología según se recomienda.</span><span class="sxs-lookup"><span data-stu-id="58fcc-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="58fcc-111">Diagrama de red perimetral: la página Diagrama de red perimetral es donde el diseñador realiza la mayor parte del trabajo en la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="58fcc-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="58fcc-112">El diagrama muestra la configuración de red de una topología recomendada de Skype Empresarial Server 2015, con entradas editables para direcciones IP y FQDN para servidores, grupos de servidores y equilibradores de carga de hardware y sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="58fcc-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="58fcc-113">Informe de administración perimetral: el informe de administración perimetral contiene un total de cuatro informes:</span><span class="sxs-lookup"><span data-stu-id="58fcc-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Página Informe de administración perimetral](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="58fcc-115">Informe de resumen: un informe general de la configuración de la configuración de red perimetral.</span><span class="sxs-lookup"><span data-stu-id="58fcc-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="58fcc-116">Si edita los valores de la página **Diagrama** de red perimetral para los valores TCP/IP y FQDN de topología de los que se usarán en la implementación real, esas direcciones y nombres se representarán aquí.</span><span class="sxs-lookup"><span data-stu-id="58fcc-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="58fcc-117">De lo contrario, aparecerá el texto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="58fcc-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="58fcc-118">Informe de certificado: el informe de certificado enumerará el nombre del sujeto y los nombres alternativos de sujeto para los certificados necesarios para la topología.</span><span class="sxs-lookup"><span data-stu-id="58fcc-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="58fcc-119">Informe de firewall: el informe de firewall enumera la información necesaria para configurar firewalls perimetrales en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="58fcc-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="58fcc-120">Esto incluye las direcciones IP (los valores predeterminados o modificados), el rol de servidor, la IP y el puerto de origen, la DIRECCIÓN IP y el puerto de destino, el protocolo de transporte, el protocolo de aplicación y las notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="58fcc-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="58fcc-121">Informe DNS: el informe DNS muestra información relevante para las entradas DNS que debe crear.</span><span class="sxs-lookup"><span data-stu-id="58fcc-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="58fcc-122">También se incluye el tipo de registro, el FQDN, la dirección IP y los comentarios necesarios para que obtener un funcionamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="58fcc-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="58fcc-123">Resumen del sitio: el resumen del sitio presenta una introducción a las selecciones realizadas respondiendo a las preguntas iniciales de la entrevista o rellenando los valores de **Sitios de diseño.**</span><span class="sxs-lookup"><span data-stu-id="58fcc-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="58fcc-124">También se presenta información de capacidad.</span><span class="sxs-lookup"><span data-stu-id="58fcc-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="58fcc-125">La información de la página Resumen del sitio está personalizada para cada diseño y puede que no contenga todas las secciones o toda la información que se indica aquí.</span><span class="sxs-lookup"><span data-stu-id="58fcc-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="58fcc-126">Editar el diagrama de configuración de red</span><span class="sxs-lookup"><span data-stu-id="58fcc-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="58fcc-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="58fcc-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="58fcc-128">La mayor parte del trabajo que realiza un diseñador en la herramienta de planeación de Skype Empresarial Server 2015 consiste en definir las entradas de las direcciones IP y los nombres de dominio completos (FQDN) para las entradas del diagrama de red.</span><span class="sxs-lookup"><span data-stu-id="58fcc-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="58fcc-129">La información que se introduce en esta página se traslada a los informes y otra información contenida en la Herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="58fcc-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagrama de red de herramientas de planeación](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="58fcc-131">La Herramienta de planeación crea un diagrama de red con texto predeterminado para direcciones IP y FQDN.</span><span class="sxs-lookup"><span data-stu-id="58fcc-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="58fcc-132">Para editar el diagrama de red y los valores de entrada:</span><span class="sxs-lookup"><span data-stu-id="58fcc-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="58fcc-133">Seleccione una sección de la red en la que desee comenzar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="58fcc-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="58fcc-134">Por ejemplo, haga doble clic en el texto, **access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="58fcc-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="58fcc-135">En el cuadro de diálogo que se abre, escriba el FQDN real del servidor access1.contoso.com y la dirección IP real, reemplazando la 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="58fcc-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="58fcc-136">Haga clic en **Aceptar** para guardar las entradas.</span><span class="sxs-lookup"><span data-stu-id="58fcc-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="58fcc-137">Continúe con la edición de direcciones IP y FQDN y proporcione direcciones IP virtuales para equilibradores de carga de hardware o entradas de servidores para el equilibrio de carga del Sistema de nombres de dominio (DNS) para servidores incluidos en grupos.</span><span class="sxs-lookup"><span data-stu-id="58fcc-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="58fcc-p111">Una característica útil de la herramienta de planeación es que puede asignar de forma gradual un rango de direcciones IP y nombres de host de servidor, en lugar de requerir que el diseñador edite por separado cada servidor de un grupo. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="58fcc-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="58fcc-140">Haga doble clic en los servidores front-end agrupados.</span><span class="sxs-lookup"><span data-stu-id="58fcc-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="58fcc-141">Cuando se abra el cuadro de diálogo, seleccione **¿Desea usar las direcciones IP y el FQDN como puntos de inicio para todos los servidores equivalentes de este clúster?**.</span><span class="sxs-lookup"><span data-stu-id="58fcc-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="58fcc-142">Por ejemplo, el valor inicial del primer servidor es fe0101.contoso.com y una dirección IP de 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="58fcc-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="58fcc-143">Escriba fe0.contoso.com en FQDN del servidor **front-end**, escriba 192.168.21.131 en Dirección IP del servidor **front-end** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="58fcc-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="58fcc-144">La característica de incremento automático actualiza todos los servidores del grupo a fe01 a fe06 y todas las direcciones IP de 192.168.21.131 a 136.</span><span class="sxs-lookup"><span data-stu-id="58fcc-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="58fcc-145">Después de completar todas las ediciones, guarde la topología completando los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="58fcc-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="58fcc-146">Para guardar el diseño de la herramienta de planeación, haga clic **en** Archivo y, a continuación, haga clic en Guardar topología **o** Guardar topología **como**.</span><span class="sxs-lookup"><span data-stu-id="58fcc-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="58fcc-147">Si aparece el cuadro de diálogo **Guardar herramienta de planeación como**, escriba el nombre del archivo en **Nombre de archivo** y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="58fcc-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="58fcc-148">Ver también</span><span class="sxs-lookup"><span data-stu-id="58fcc-148">See also</span></span>
<span data-ttu-id="58fcc-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="58fcc-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="58fcc-150">Edición del diseño</span><span class="sxs-lookup"><span data-stu-id="58fcc-150">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)