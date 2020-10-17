---
title: 'Lync Server 2013: implementar tipos de direcciones IP en un servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5037a723b16758280eec5ec4500e6f561cb9a8bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521637"
---
# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="4a5f6-102">Implementar tipos de direcciones IP en un servidor front-end para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5f6-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5f6-103">_**Última modificación del tema:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="4a5f6-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="4a5f6-104">Mediante el generador de topologías, lleve a cabo los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="4a5f6-105">Para implementar los tipos de direcciones IP en un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="4a5f6-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="4a5f6-p101">En \*\*Grupo de servidores front-end Enterprise Edition \*\*, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="4a5f6-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="4a5f6-p102">En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="4a5f6-110">**Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**</span><span class="sxs-lookup"><span data-stu-id="4a5f6-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="4a5f6-111">![Cuadro de diálogo Propiedades de edición de servidor front-end](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Cuadro de diálogo Propiedades de edición de servidor front-end")</span><span class="sxs-lookup"><span data-stu-id="4a5f6-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="4a5f6-p103">**Use todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4a5f6-114">Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="4a5f6-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="4a5f6-p104">**Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, debe introducir un valor para la **dirección IP principal**.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="4a5f6-p105">**Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida debe coincidir con el formato del tipo de dirección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="4a5f6-121">**Dirección IP de RTC**.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-121">**PSTN IP address**.</span></span> <span data-ttu-id="4a5f6-122">La instalación de tarjetas de interfaz de red (NIC) adicionales para admitir la configuración de dirección IP de RTC para Lync Server 2013 no es compatible con roles de servidor de mediación combinados.</span><span class="sxs-lookup"><span data-stu-id="4a5f6-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="4a5f6-123">Para obtener más información sobre las configuraciones de NIC admitidas para Lync Server 2013, vea [plataformas de hardware de servidor para Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="4a5f6-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

