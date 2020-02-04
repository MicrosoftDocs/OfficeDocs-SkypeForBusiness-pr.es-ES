---
title: 'Lync Server 2013: Instalar componentes del servidor Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="0d895-102">Instalar componentes del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d895-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d895-103">_**Última modificación del tema:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="0d895-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="0d895-104">Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que es un administrador local y miembro del grupo RTCUniversalReadOnlyAdmins en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d895-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="0d895-105">El Asistente para la implementación de Lync Server se usa para instalar los componentes necesarios para cada rol de Lync Server y para activar el servidor.</span><span class="sxs-lookup"><span data-stu-id="0d895-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="0d895-106">Este artículo le guiará a través de los pasos de implementación de un servidor Standard Edition o de un servidor front-end en su infraestructura de Lync.</span><span class="sxs-lookup"><span data-stu-id="0d895-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="0d895-107">Para instalar los componentes de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0d895-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="0d895-108">Si el Asistente para la implementación de Lync Server no se está ejecutando, inícielo en el servidor en el que desea instalar Lync.</span><span class="sxs-lookup"><span data-stu-id="0d895-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="0d895-109">Haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0d895-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="0d895-110">En el Asistente para la implementación, confirme que el **paso 1: instalar el almacén de configuración local** tiene una marca de verificación verde, lo que significa que este servidor tiene una copia local de la tienda instalada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d895-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="0d895-111">Si no está activado, debe instalar el almacén de configuración local en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0d895-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="0d895-112">Siga los pasos de [instalar el almacén de configuración local en Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) y, a continuación, vuelva aquí.</span><span class="sxs-lookup"><span data-stu-id="0d895-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="0d895-113">Cuando esté listo para instalar los componentes de Lync Server 2013 en el servidor, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar los componentes de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0d895-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="0d895-114">En la página **configurar los componentes de Lync Server** , haga clic en **siguiente** para configurar los componentes definidos en la topología publicada.</span><span class="sxs-lookup"><span data-stu-id="0d895-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="0d895-115">La página **Commands Execute** mostrará un resumen de comandos e información de instalación a medida que se realiza la configuración.</span><span class="sxs-lookup"><span data-stu-id="0d895-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="0d895-116">Cuando finalice, puede usar la lista para seleccionar un registro que quiera ver y, luego, hacer clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="0d895-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="0d895-117">Cuando termine la instalación de los componentes de Lync Server 2013 y haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.</span><span class="sxs-lookup"><span data-stu-id="0d895-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d895-118">Si se le pide que reinicie el servidor (lo que puede ocurrir si es necesario instalar la experiencia de escritorio de Windows), lo hace definitivamente.</span><span class="sxs-lookup"><span data-stu-id="0d895-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="0d895-119">Cuando el equipo esté en funcionamiento, tendrá que realizar estos pasos de nuevo, empezando desde el paso tres que se indican anteriormente (básicamente, ejecute el paso 2 en el Asistente de implementación una vez más).</span><span class="sxs-lookup"><span data-stu-id="0d895-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

