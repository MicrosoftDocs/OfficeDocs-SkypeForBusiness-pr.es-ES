---
title: 'Lync Server 2013: instalar servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2738367bbbf2c81d5d5b0d084fffa9e992410f18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="00279-102">Instalar servidores perimetrales para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00279-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00279-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="00279-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="00279-104">Instale Lync Server 2013 en servidores perimetrales mediante el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00279-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="00279-105">Cuando se ejecuta el Asistente para la implementación en cada servidor perimetral, se puede llevar a cabo la mayor parte de las tareas necesarias para configurar el servidor en cuestión.</span><span class="sxs-lookup"><span data-stu-id="00279-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="00279-106">Para implementar Lync Server 2013 en un servidor perimetral, debe haber ejecutado el generador de topologías para definir y publicar la topología del servidor perimetral y exportarla a medios disponibles desde el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="00279-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="00279-107">Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) y [exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="00279-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="00279-108">Después de usar el Asistente para la implementación para instalar cada servidor perimetral, instalar y asignar los certificados necesarios e iniciar los servicios necesarios, puede completar la configuración con la información de [configuración de compatibilidad para el acceso de usuarios externos en Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) para habilitar y configurar el acceso de usuarios externos y la información en [comprobar la implementación perimetral en Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) para validar la configuración, incluida la conectividad de cliente</span><span class="sxs-lookup"><span data-stu-id="00279-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="00279-109">Para instalar un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="00279-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="00279-110">Inicie sesión en el equipo en el que desea instalar el servidor perimetral como miembro del grupo Administradores o con una cuenta que tenga derechos o permisos de usuario similares.</span><span class="sxs-lookup"><span data-stu-id="00279-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="00279-111">Asegúrese de que el archivo de configuración de la topología que ha creado mediante el generador de topologías y, a continuación, de que se ha exportado y copiado a un medio externo está disponible en el servidor perimetral (por ejemplo, acceso a la unidad USB en la que copió el archivo de configuración de la topología o Compruebe acceso al recurso compartido de red en el que copió el archivo).</span><span class="sxs-lookup"><span data-stu-id="00279-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="00279-112">Inicie el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="00279-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00279-p102">Si recibe un mensaje en el que se indica que es necesario instalar Microsoft Visual C++ Redistributable, haga clic en <STRONG>Sí</STRONG>. En el siguiente cuadro de diálogo, puede aceptar la <STRONG>Ubicación de instalación</STRONG> predeterminada o bien hacer clic en <STRONG>Examinar</STRONG> para seleccionar otra. Tras ello, haga clic en <STRONG>Instalar</STRONG>. En el siguiente cuadro de diálogo, active la casilla <STRONG>Acepto los términos del contrato de licencia</STRONG> y haga clic en <STRONG>Aceptar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="00279-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="00279-116">En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="00279-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="00279-117">Una vez que el asistente ha averiguado el estado de la implementación, en **Paso 1. Instalar almacén de configuración local**, haga clic en **Ejecutar** y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00279-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="00279-118">En el cuadro de diálogo **Configurar réplica local del almacén de administración central**, haga clic en **Importar desde un archivo (recomendado en servidores perimetrales)**, vaya a la ubicación del archivo de configuración de la topología exportado, seleccione el archivo .zip, haga clic en **Abrir** y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="00279-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="00279-119">El Asistente para la implementación lee la información de configuración de este archivo y escribe el archivo de configuración XML en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="00279-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="00279-120">Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="00279-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="00279-121">En el Asistente para la implementación, haga clic en **paso 2: configurar o quitar componentes de Lync Server** para instalar los componentes perimetrales de lync Server 2013 que se han especificado en el archivo de configuración XML que se almacena en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="00279-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="00279-122">Una vez finalizada la instalación, use la información de [configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar y asignar los certificados necesarios antes de iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="00279-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

