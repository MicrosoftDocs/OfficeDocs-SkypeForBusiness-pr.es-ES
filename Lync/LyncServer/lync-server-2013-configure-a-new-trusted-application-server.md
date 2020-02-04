---
title: 'Lync Server 2013: configurar un nuevo servidor de aplicaciones de confianza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="75490-102">Configurar un nuevo servidor de aplicaciones de confianza en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75490-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75490-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="75490-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="75490-104">Una aplicación de confianza es una aplicación basada en el SDK del núcleo de la API administrada de Microsoft Unified Communications (UCMA) 3,0 en el que confía Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75490-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="75490-105">Para obtener más información acerca de las aplicaciones de UCMA, consulte "documentación de SDK de comunicaciones [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)unificadas de la API de Core 3,0" en.</span><span class="sxs-lookup"><span data-stu-id="75490-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="75490-106">Para obtener información sobre cómo configurar Microsoft Outlook Web Access (OWA) y Lync Server 2013, consulte "configurar la integración de Outlook Web App y Lync Server 2010" en la documentación de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75490-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="75490-107">Para publicar, habilitar o deshabilitar correctamente una topología al agregar o quitar un rol de servidor, debe haber iniciado sesión como un usuario que sea miembro de los grupos administradores de dominio y RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="75490-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="75490-108">También es posible delegar los permisos de administrador apropiados y los derechos para agregar roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="75490-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="75490-109">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="75490-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="75490-110">Para otros cambios de configuración, solo es necesario pertenecer al grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="75490-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="75490-111">Para configurar un servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="75490-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="75490-112">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="75490-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="75490-113">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="75490-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="75490-114">Seleccione **Descargar topología de la implementación existente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75490-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="75490-115">En el cuadro de diálogo **Guardar topología como** , haga clic en el archivo del generador de topología que desea usar y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="75490-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="75490-116">En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza**y luego haga clic en **nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="75490-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="75490-117">Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza, seleccione si va a ser un servidor único o de varios servidores y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75490-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="75490-118">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75490-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="75490-119">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="75490-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="75490-120">Seleccione el nodo superior de **Lync Server 2013**y, a continuación, en el menú **acciones** , haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="75490-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="75490-121">El **grupo de aplicaciones de confianza** se creó correctamente y se asoció con el grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="75490-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

