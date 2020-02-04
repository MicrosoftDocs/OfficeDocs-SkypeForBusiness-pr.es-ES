---
title: 'Lync Server 2013: Importar un archivo de configuración de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f00b1eb3406c1a3d425727820da8686f96f1dae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="e14cc-102">Importar un archivo de configuración de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e14cc-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e14cc-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e14cc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e14cc-104">Si desea guardar la configuración de enrutamiento de voz sin publicarla, siga estos pasos para usar los comandos exportar e importar del panel de control de Lync Server para guardar y recuperar una instantánea de su configuración de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="e14cc-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="e14cc-105">Al importar un archivo de configuración de enrutamiento de voz (. vcfg), pero se han realizado cambios en la configuración de enrutamiento de voz en el servidor mientras tanto, las páginas del grupo de **enrutamiento de voz** en el panel de control de Lync Server indicarán que hay cambios no confirmados en el enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="e14cc-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="e14cc-106">Estos cambios no confirmados son las diferencias entre las dos configuraciones que requieren reconciliación.</span><span class="sxs-lookup"><span data-stu-id="e14cc-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="e14cc-107">Si ha realizado cambios no confirmados en la configuración de cualquier página del grupo, los cambios se guardan en el archivo de configuración de voz exportado (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="e14cc-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="e14cc-108">Esto le permite realizar cambios en la configuración del enrutamiento de voz durante varias sesiones antes de publicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e14cc-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="e14cc-109">Para importar una configuración de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="e14cc-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="e14cc-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e14cc-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e14cc-111">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e14cc-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e14cc-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e14cc-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e14cc-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e14cc-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e14cc-114">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="e14cc-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="e14cc-115">En el menú **Acciones**, haga clic en **Importar configuración**.</span><span class="sxs-lookup"><span data-stu-id="e14cc-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="e14cc-116">Busque el archivo de configuración que desee importar y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e14cc-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="e14cc-117">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="e14cc-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e14cc-118">Siempre que importe un archivo de configuración de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e14cc-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e14cc-119">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e14cc-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e14cc-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e14cc-120">See Also</span></span>


[<span data-ttu-id="e14cc-121">Exportar un archivo de configuración de la ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e14cc-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="e14cc-122">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e14cc-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

