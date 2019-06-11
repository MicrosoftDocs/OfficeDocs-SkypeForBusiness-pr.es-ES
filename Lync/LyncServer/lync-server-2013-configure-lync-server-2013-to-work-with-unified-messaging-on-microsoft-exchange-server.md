---
title: 'Lync Server 2013: Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="7154c-102">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="7154c-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="7154c-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="7154c-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="7154c-104">Este paso requiere la utilidad de integración de mensajería unificada de Exchange (OcsUmUtil. exe).</span><span class="sxs-lookup"><span data-stu-id="7154c-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="7154c-105">Esta herramienta se encuentra en el servidor de Lync Server 2013, en... \\Archivos\\comunes de programa\\archivos comunes carpeta de\\soporte técnico de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7154c-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="7154c-106">Ejecución de la utilidad de integración de MU de Exchange</span><span class="sxs-lookup"><span data-stu-id="7154c-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="7154c-107">La utilidad de integración de MU de Exchange debe ejecutarse desde una cuenta de usuario con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="7154c-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="7154c-108">Pertenencia a los grupos RTCUniversalServerAdmins y RtcUniversalUserAdmins (que incluye permisos para leer la configuración de mensajería unificada de Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="7154c-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="7154c-109">Derechos de usuario dentro del dominio para crear objetos de contacto en el contenedor de unidades organizativas (OU) especificadas.</span><span class="sxs-lookup"><span data-stu-id="7154c-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="7154c-110">Al ejecutar la herramienta de integración de mensajería unificada de Exchange, se realizan las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7154c-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="7154c-111">Crea objetos de contacto para cada número de acceso de suscriptor y de operador automático que usarán los usuarios de voz de telefonía.</span><span class="sxs-lookup"><span data-stu-id="7154c-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="7154c-112">Comprueba que el nombre de cada plan de marcado de voz de empresa coincida con su contexto de teléfono del plan de marcado de mensajería unificada (UM) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7154c-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="7154c-113">Esta coincidencia es necesaria solo si el plan de marcado de MU se está ejecutando en una versión de Exchange *anterior* a Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="7154c-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7154c-114">Antes de ejecutar la utilidad de integración de MU de Exchange, asegúrese de que ha hecho lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7154c-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="7154c-115">Cree uno o varios planes de marcado de mensajería unificada de Exchange, como se describe en la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7154c-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="7154c-116">Para Microsoft Exchange Server 2010, consulte &quot;crear un plan&quot; de marcado de <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>MU en.</span><span class="sxs-lookup"><span data-stu-id="7154c-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="7154c-117">Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot;cómo crear un plan&quot; de marcado URI SIP Messaging Messaging en <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span><span class="sxs-lookup"><span data-stu-id="7154c-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="7154c-118">Cree uno o varios de los planes de marcado de Lync Server correspondientes, tal y como se describe en <a href="lync-server-2013-create-a-dial-plan.md">crear un plan de marcado en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7154c-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="7154c-119">Si está usando una versión de Exchange anterior a Microsoft Exchange Server 2010 SP1, debe escribir el nombre de dominio completo (FQDN) del plan de marcado SIP de mensajería unificada de Exchange (UM) correspondiente en el nombre simple del plan de marcado de Lync Server 2013 <STRONG> </STRONG>campo.</span><span class="sxs-lookup"><span data-stu-id="7154c-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="7154c-120">Si está usando Microsoft Exchange Server 2010 SP1 o el Service Pack más reciente, la coincidencia de nombres de plan de marcado no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="7154c-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="7154c-121">Cree un operador automático y asegúrese de que tanto el número de acceso del suscriptor como el número de operador automático estén en formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="7154c-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="7154c-122">Para ejecutar la utilidad de integración de mensajería unificada de Exchange</span><span class="sxs-lookup"><span data-stu-id="7154c-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="7154c-123">En un servidor front-end, abra un símbolo del sistema y escriba **CD%\\CommonProgramFiles% Microsoft Lync\\Server 2013 support**y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="7154c-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="7154c-124">Escriba **OcsUmUtil. exe**y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="7154c-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="7154c-125">Haga clic en **cargar datos** para buscar todos los bosques de confianza de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7154c-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="7154c-126">En la lista de los **planes de marcado SIP** , seleccione un plan de marcado SIP de mensajería unificada para el que desee crear objetos de contacto y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7154c-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="7154c-127">En el cuadro **contacto** , acepte la unidad organizativa predeterminada o haga clic en **examinar** para iniciar el **selector de Uo**.</span><span class="sxs-lookup"><span data-stu-id="7154c-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="7154c-128">En el cuadro **selector de ou** , seleccione una unidad organizativa y haga clic en **Aceptar**, o bien haga clic en crear una **nueva** unidad organizativa para crear una nueva unidad organizativa en la raíz o en cualquier otra unidad organizativa del dominio (por ejemplo, "ou = RTC Special Accounts, DC = fourthcoffee, DC = com") y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7154c-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7154c-129">El nombre distintivo (DN) de la OU que ha seleccionado o creado se muestra ahora en el cuadro <STRONG>unidad organizativa</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="7154c-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="7154c-130">En el cuadro **nombre** , acepte el nombre del plan de marcado predeterminado o escriba un nuevo nombre para mostrar para el objeto de contacto que está creando.</span><span class="sxs-lookup"><span data-stu-id="7154c-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7154c-131">Por ejemplo, si va a crear un objeto de contacto de acceso de suscriptor, es posible que simplemente le asigne el nombre de acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="7154c-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="7154c-132">En el cuadro **dirección SIP** , acepte la dirección SIP predeterminada o escriba una nueva.</span><span class="sxs-lookup"><span data-stu-id="7154c-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7154c-133">Si escribe una dirección SIP nueva, debe comenzar con <STRONG>SIP:</STRONG> (es decir, "SIP:" incluyendo los dos puntos).</span><span class="sxs-lookup"><span data-stu-id="7154c-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="7154c-134">En la lista **servidor o grupo** de servidores, seleccione el servidor Standard Edition o el grupo de servidores front-end en el que se va a habilitar el objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="7154c-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7154c-135">Preferiblemente, el grupo que seleccione es el mismo grupo en el que se implementan los usuarios habilitados para telefonía IP empresarial y mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="7154c-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="7154c-136">En la lista **número de teléfono** , seleccione **Escriba el número de teléfono** o **use este número piloto de la mensajería unificada de Exchange** y, a continuación, escriba un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="7154c-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="7154c-137">En la lista **tipo de contacto** , seleccione el tipo de contacto que desea crear y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7154c-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="7154c-138">Repita los pasos 1 a 10 para obtener objetos de contacto adicionales que desee crear.</span><span class="sxs-lookup"><span data-stu-id="7154c-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7154c-139">Debes crear al menos un contacto para cada operador automático.</span><span class="sxs-lookup"><span data-stu-id="7154c-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="7154c-140">Si desea obtener acceso externo, también necesitará un contacto de acceso de suscriptor y especificar números de marcado directo directo (sí).</span><span class="sxs-lookup"><span data-stu-id="7154c-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="7154c-141">Para comprobar que los objetos de contacto se han creado, abra usuarios y equipos de Active Directory y seleccione la OU en la que se crearon los objetos.</span><span class="sxs-lookup"><span data-stu-id="7154c-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="7154c-142">Los objetos de contacto deberían aparecer en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="7154c-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="7154c-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7154c-143"></span></span></div>

