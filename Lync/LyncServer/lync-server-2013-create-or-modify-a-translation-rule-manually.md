---
title: 'Lync Server 2013: crear o modificar una regla de traducción de forma manual'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="2ad15-102">Crear o modificar una regla de traducción de forma manual en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ad15-103">_**Última modificación del tema:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="2ad15-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="2ad15-104">Siga estos pasos si desea definir una regla de traducción escribiendo una expresión regular para el patrón y la regla de traducción coincidentes.</span><span class="sxs-lookup"><span data-stu-id="2ad15-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="2ad15-105">También puede introducir un conjunto de valores en la herramienta **generar una regla de traducción** y habilitar el panel de control de Lync Server para generar la regla de traducción y el patrón de coincidencia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2ad15-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="2ad15-106">Para obtener más información, consulte [crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2ad15-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="2ad15-107">Para definir una regla de conversión de forma manual</span><span class="sxs-lookup"><span data-stu-id="2ad15-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="2ad15-108">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ad15-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2ad15-109">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2ad15-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2ad15-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ad15-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ad15-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ad15-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ad15-112">Para empezar a definir una regla de traducción, siga los pasos que se indican en [configurar un tronco con la omisión de medios en Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) hasta el paso 10 o [configurar un tronco sin evitar los medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) a paso 9.</span><span class="sxs-lookup"><span data-stu-id="2ad15-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="2ad15-113">En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="2ad15-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="2ad15-114">(Opcional) En **Descripción**, escriba una descripción de la regla de conversión, por ejemplo, **US International long-distance dialing**.</span><span class="sxs-lookup"><span data-stu-id="2ad15-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="2ad15-115">Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.</span><span class="sxs-lookup"><span data-stu-id="2ad15-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="2ad15-116">Especifique lo siguiente en **Escribir una expresión regular**:</span><span class="sxs-lookup"><span data-stu-id="2ad15-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="2ad15-117">En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="2ad15-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="2ad15-118">En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="2ad15-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="2ad15-119">Por ejemplo, si escribe \*\* ^ \\+\\(d{9}\\+) $\*\* en **coincidencia con este patrón** y **011 $1** en la **regla de traducción**, la regla traducirá + 441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="2ad15-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="2ad15-120">Haga clic en **Aceptar** para guardar la regla de conversión.</span><span class="sxs-lookup"><span data-stu-id="2ad15-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="2ad15-121">Haga clic en **Aceptar** para guardar la configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="2ad15-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="2ad15-122">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="2ad15-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ad15-123">Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ad15-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2ad15-124">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad15-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ad15-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad15-125">See Also</span></span>


[<span data-ttu-id="2ad15-126">Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="2ad15-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="2ad15-128">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="2ad15-129">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="2ad15-130">Opciones de omisión de multimedia global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad15-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

