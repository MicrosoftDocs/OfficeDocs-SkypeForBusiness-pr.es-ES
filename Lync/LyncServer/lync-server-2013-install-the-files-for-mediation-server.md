---
title: 'Lync Server 2013: instalar los archivos para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="7f404-102">Instalar los archivos de Media Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f404-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f404-103">_**Última modificación del tema:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="7f404-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="7f404-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor por lo menos como administrador local y usuario de dominio que pertenezca, como mínimo, al grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="7f404-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="7f404-105">Siga los pasos que se indican en este tema para ejecutar el Asistente para la implementación de Lync Server 2013 para instalar los archivos del servidor de mediación en un equipo que haya agregado a un grupo de servidores de mediación cuando usó el generador de topología para definir y publicar el grupo.</span><span class="sxs-lookup"><span data-stu-id="7f404-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="7f404-106">Al instalar el servidor de mediación de archivos, también puede instalar y asignar el certificado requerido por cada equipo de un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7f404-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="7f404-107">En este sitio, si ya ha implementado servidores de mediación colocados en las agrupaciones front-end o en el servidor Standard Edition, puede omitir este tema y, en su lugar, seguir configurando [troncos en Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="7f404-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f404-108">En este tema se supone que ya ha definido y publicado un grupo de servidores de mediación independiente, tal como se describe en <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir un servidor de mediación en el generador de topología en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la implementación y que ha verificado que los equipos del grupo de servidores de mediación cumplen los requisitos previos descritos en los <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos previos de software de telefonía IP empresarial en Lync Server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de configuración y seguridad de Telefonía IP empresarial en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f404-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="7f404-109">Para instalar los archivos de un grupo de servidores de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="7f404-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="7f404-110">En el medio de instalación, haga clic \<con el\>botón derecho en instalación de medios**\\de instalación\\AMD64\\Setup. exe**y luego haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7f404-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="7f404-111">En la página **Ubicación de la instalación**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f404-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="7f404-p102">En la página **Contrato de licencia para el usuario final**, seleccione **Aceptar** y, a continuación, haga clic en **Aceptar**. (Es necesario para poder continuar).</span><span class="sxs-lookup"><span data-stu-id="7f404-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="7f404-114">En la página **Asistente para la implementación de Lync server 2010** , haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7f404-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="7f404-115">Junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="7f404-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="7f404-116">En la página **Configurar réplica local del almacén de administración central**, acepte la opción predeterminada **Recuperar directamente de almacén de administración central**; a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f404-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="7f404-117">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7f404-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="7f404-118">Junto al **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7f404-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="7f404-119">En la página **Ejecutando comandos**, cuando el estado sea **Completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7f404-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="7f404-p103">Junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**. Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada. El servidor de mediación requiere un certificado, por eso el **Paso 3** se debe ejecutar dos veces: una para emitir el certificado requerido y una más para asignarlo.</span><span class="sxs-lookup"><span data-stu-id="7f404-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="7f404-123">Una vez se ha emitido y asignado correctamente el certificado, junto a **Paso 4: Iniciar servicios**, haga clic en **Ejecutar** y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="7f404-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="7f404-124">Tras completar correctamente el **Paso 4**, reinicie el servidor e inicie sesión en él como miembro del grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="7f404-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="7f404-125">En el equipo en el que esté ejecutando el panel de control de Lync Server, compruebe en la página **topología** del panel de control de Lync Server que el estado del servicio del servidor de mediación se muestra como una marca de verificación verde.</span><span class="sxs-lookup"><span data-stu-id="7f404-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="7f404-126">Si en lugar de ello aparece una X de color rojo, seleccione el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7f404-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="7f404-127">En el menú **Acción**, haga clic en **Iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="7f404-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="7f404-128">Si ha agregado más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7f404-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="7f404-129">Si no necesita instalar archivos para el servidor de mediación de cualquier otro equipo, siga los procedimientos de [configuración de troncos en Lync Server 2013](lync-server-2013-configuring-trunks.md) para establecer la configuración de la conexión troncal entre este grupo de servidores de mediación (o todo el medio de mediación). Servidores en un sitio) y sus pares.</span><span class="sxs-lookup"><span data-stu-id="7f404-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f404-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f404-130">See Also</span></span>


[<span data-ttu-id="7f404-131">Requisitos de certificado para Servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f404-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

