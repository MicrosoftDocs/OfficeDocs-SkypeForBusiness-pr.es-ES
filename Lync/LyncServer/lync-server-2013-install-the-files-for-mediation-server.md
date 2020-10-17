---
title: 'Lync Server 2013: instalar los archivos del servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7fd5613b39fd17724c9b62152f9d9401fbc072
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498597"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="0835b-102">Instalar los archivos del servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0835b-102">Install the files for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0835b-103">_**Última modificación del tema:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="0835b-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="0835b-104">Para completar correctamente este procedimiento, debe iniciar sesión en el servidor, como mínimo, como administrador local y usuario de dominio que pertenezca al menos al grupo RTCUniversalReadOnlyAdmins.</span><span class="sxs-lookup"><span data-stu-id="0835b-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="0835b-105">Use los pasos de este tema para ejecutar el Asistente para la implementación de Lync Server 2013 para instalar los archivos del servidor de mediación en un equipo que haya agregado a un grupo de servidores de mediación cuando usó el generador de topologías para definir y publicar el grupo.</span><span class="sxs-lookup"><span data-stu-id="0835b-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="0835b-106">Al instalar el servidor de mediación de archivos, también se instala y se asigna el certificado que requiere cada equipo en un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="0835b-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="0835b-107">En este sitio, si ya ha implementado servidores de mediación combinados en los grupos de servidores front-end o el servidor Standard Edition, puede omitir este tema y continuar con la [configuración de troncos en Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="0835b-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0835b-108">En este tema se supone que ya se ha definido y publicado un grupo de servidores de mediación independiente, como se describe en <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">definir un servidor de mediación en el generador de topologías en Lync server 2013</A> y <A href="lync-server-2013-publish-the-topology.md">publicar la topología en Lync Server 2013</A> en la documentación de implementación. y que ha comprobado que los equipos del grupo de servidores de mediación cumplen los requisitos previos descritos en <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">requisitos previos de software para telefonía ip empresarial en Lync Server 2013</A> y los <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">requisitos previos de seguridad y configuración para telefonía IP empresarial en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0835b-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="0835b-109">Para instalar los archivos de un grupo de servidores de mediación independiente</span><span class="sxs-lookup"><span data-stu-id="0835b-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="0835b-110">En el medio de instalación, haga clic con el botón secundario en \<installation media\> \*\* \\ setup \\ AMD64 \\Setup.exe\*\*y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="0835b-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="0835b-111">En la página **Ubicación de instalación** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0835b-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="0835b-112">En la página contrato de licencia para el **usuario final** **, haga clic en Acepto y**, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0835b-112">On the **End User License Agreement** page, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="0835b-113">(Obligatorio para continuar).</span><span class="sxs-lookup"><span data-stu-id="0835b-113">(Required to continue.)</span></span>

4.  <span data-ttu-id="0835b-114">En la página **Asistente para la implementación de Lync server 2010** , haga clic en **instalar o actualizar el sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0835b-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="0835b-115">Junto a **paso 1: instalar almacén de configuración local**, haga clic en **Ejecutar**y siga las instrucciones que aparecen en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0835b-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="0835b-116">En la página **configurar réplica local del almacén de administración central** , acepte la opción predeterminada **recuperar directamente del almacén de administración central**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0835b-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="0835b-117">En la página **ejecución de comandos** , cuando el estado de la tarea se muestre como **completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0835b-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="0835b-118">Junto a **paso 2: configurar o quitar componentes de Lync Server**, haga clic en **Ejecutar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0835b-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="0835b-119">En la página **ejecución de comandos** , cuando el estado de la tarea se muestre como **completado**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0835b-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="0835b-120">Junto a **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0835b-120">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span> <span data-ttu-id="0835b-121">Siga las instrucciones que aparecen en la pantalla y acepte la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0835b-121">Follow the instructions on the screen, accepting the default settings.</span></span> <span data-ttu-id="0835b-122">El servidor de mediación requiere un certificado y, por lo tanto, se ejecutará el **paso 3** dos veces: una para emitir el certificado requerido y una vez más para asignarlo.</span><span class="sxs-lookup"><span data-stu-id="0835b-122">The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="0835b-123">Una vez que el certificado se haya emitido y asignado correctamente, junto al **paso 4: iniciar servicios**, haga clic en **Ejecutar**y siga las instrucciones que aparecen en pantalla.</span><span class="sxs-lookup"><span data-stu-id="0835b-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="0835b-124">Cuando se haya completado correctamente el **paso 4** , reinicie el servidor e inicie sesión en el servidor como miembro del grupo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="0835b-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="0835b-125">En el equipo en el que ejecuta el panel de control de Lync Server, compruebe en la página de **topología** del panel de control de Lync Server que el estado de servicio del servidor de mediación se muestra como una marca de verificación verde.</span><span class="sxs-lookup"><span data-stu-id="0835b-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="0835b-126">Si en su lugar aparece una X roja, seleccione el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="0835b-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="0835b-127">En el menú **acción** , haga clic en **iniciar todos los servicios**.</span><span class="sxs-lookup"><span data-stu-id="0835b-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="0835b-128">Si agregó más de un equipo al grupo de servidores de mediación, realice los pasos de este procedimiento en todos los demás equipos del grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="0835b-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="0835b-129">Si no necesita instalar archivos para el servidor de mediación para otros equipos, siga los procedimientos que se describen en [Configuring troncos in Lync Server 2013](lync-server-2013-configuring-trunks.md) para establecer la configuración de la conexión troncal entre este grupo de servidores de mediación (o todos los servidores de mediación de un sitio) y su homólogo.</span><span class="sxs-lookup"><span data-stu-id="0835b-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0835b-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0835b-130">See Also</span></span>


[<span data-ttu-id="0835b-131">Requisitos de certificado para servidores internos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0835b-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

