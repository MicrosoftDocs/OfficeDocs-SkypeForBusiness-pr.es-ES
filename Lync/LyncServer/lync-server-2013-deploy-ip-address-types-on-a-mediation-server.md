---
title: 'Lync Server 2013: implementar tipos de direcciones IP en un servidor de mediación'
description: 'Lync Server 2013: implemente tipos de direcciones IP en un servidor de mediación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa3be8d1ef12629dc185f98b95d2db0e565cf18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559786"
---
# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="6bf29-103">Implementar tipos de direcciones IP en un servidor de mediación para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf29-103">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf29-104">_**Última modificación del tema:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="6bf29-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="6bf29-105">Mediante el generador de topologías, lleve a cabo los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="6bf29-105">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="6bf29-106">Para implementar tipos de direcciones IP en un servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="6bf29-106">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="6bf29-107">En el generador de topologías, en **grupos de mediación**, haga clic con el botón secundario en el servidor dentro de un grupo y, después, seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6bf29-107">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="6bf29-108">(También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="6bf29-108">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="6bf29-p102">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bf29-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="6bf29-111">**Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="6bf29-111">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="6bf29-112">![Página de propiedades generales de Lync Server con FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Página de propiedades generales de Lync Server con FQDN")</span><span class="sxs-lookup"><span data-stu-id="6bf29-112">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="6bf29-p103">**Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6bf29-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6bf29-115">Esta es la opción recomendada para las configuraciones de IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="6bf29-115">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="6bf29-p104">**Limitar el uso del servicio a las direcciones especificadas**. Seleccione esta opción para especificar una dirección concreta para usarla en el nuevo servidor. Si selecciona esta opción, debe indicar un valor de dirección IP principal.</span><span class="sxs-lookup"><span data-stu-id="6bf29-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="6bf29-p105">**Dirección IP principal**. Escriba una dirección IP que va a utilizar el servidor para todas las comunicaciones excepto la red telefónica conmutada (RTC) pública. La dirección IP escrita debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6bf29-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="6bf29-122">**Dirección IP de RTC**.</span><span class="sxs-lookup"><span data-stu-id="6bf29-122">**PSTN IP address**.</span></span> <span data-ttu-id="6bf29-123">Definir una dirección IP RTC cuando un servidor de mediación es independiente.</span><span class="sxs-lookup"><span data-stu-id="6bf29-123">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="6bf29-124">Esta dirección debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6bf29-124">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6bf29-125">La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de dirección IP de RTC para Lync Server 2013 no es compatible con roles de servidor de mediación combinados.</span><span class="sxs-lookup"><span data-stu-id="6bf29-125">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="6bf29-126">Para obtener más información sobre las configuraciones de NIC admitidas para Lync Server 2013, vea <A href="lync-server-2013-server-hardware-platforms.md">plataformas de hardware de servidor para Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6bf29-126">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

