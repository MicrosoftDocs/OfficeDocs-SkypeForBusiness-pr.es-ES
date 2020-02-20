---
title: 'Lync Server 2013: configurar Lync Server 2013 para que funcione con la mensajería unificada en Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 043015fb30ca21a697a9758a5fbb4d916b006046
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="32398-102">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="32398-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="32398-103">_**Última modificación del tema:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="32398-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="32398-104">Para realizar este paso hace falta la utilidad de integración de Mensajería unificada de Exchange (OcsUmUtil.exe).</span><span class="sxs-lookup"><span data-stu-id="32398-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="32398-105">Esta herramienta se encuentra en el servidor de Lync Server 2013 en el.. \\Archivos de\\programa archivos\\comunes carpeta de soporte\\de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32398-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="32398-106">Ejecución de la utilidad de integración de MU de Exchange</span><span class="sxs-lookup"><span data-stu-id="32398-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="32398-107">La utilidad de integración de Mensajería unificada de Exchange se debe ejecutar desde una cuenta de usuario con las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="32398-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="32398-108">Pertenencia a los grupos RTCUniversalServerAdmins y RtcUniversalUserAdmins (que incluyen permisos para leer la configuración de Mensajería unificada de Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="32398-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="32398-109">Derechos de usuario dentro del dominio para crear objetos de contacto en el contenedor de la unidad organizativa (OU) especificada.</span><span class="sxs-lookup"><span data-stu-id="32398-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="32398-110">Al ejecutar la utilidad de integración de Mensajería unificada de Exchange, se realizan las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="32398-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="32398-111">Se crean objetos de contacto para cada número de operador automático y acceso de suscriptor que vayan a usar los usuarios de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="32398-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="32398-112">Comprueba que el nombre de cada plan de marcado de voz de empresa coincida con el contexto de teléfono correspondiente del plan de marcado de mensajería unificada (UM).</span><span class="sxs-lookup"><span data-stu-id="32398-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="32398-113">Esta coincidencia solo es necesaria si el plan de marcado de mensajería unificada se ejecuta en una versión de Exchange *anterior* a Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="32398-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32398-114">Antes de ejecutar la utilidad de integración de mensajería unificada de Exchange, asegúrese de que ha hecho lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="32398-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="32398-115">Cree uno o más planes de marcado de mensajería unificada de Exchange, como se describe en la documentación del producto de Exchange.</span><span class="sxs-lookup"><span data-stu-id="32398-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="32398-116">Para Microsoft Exchange Server 2010, vea &quot;crear un plan&quot; de marcado de <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>mensajería unificada en.</span><span class="sxs-lookup"><span data-stu-id="32398-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="32398-117">Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), vea &quot;cómo crear un plan&quot; de marcado de URI de SIP de <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>mensajería unificada en.</span><span class="sxs-lookup"><span data-stu-id="32398-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="32398-118">Cree uno o varios planes de marcado de Lync Server correspondiente, tal y como se describe en <a href="lync-server-2013-create-a-dial-plan.md">Create a Dial plan in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="32398-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="32398-119">Si usa una versión de Exchange anterior a Microsoft Exchange Server 2010 SP1, debe escribir el nombre de dominio completo (FQDN) del plan de marcado SIP de mensajería unificada de Exchange correspondiente en el campo <STRONG>nombre sencillo</STRONG> del plan de marcado de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32398-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="32398-120">Si usa Microsoft Exchange Server 2010 SP1 o el último Service Pack, esta coincidencia de nombres de plan de marcado no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="32398-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="32398-121">Crear un operador automático y asegurarse de que tanto el número de acceso del suscriptor y el número del operador automático están en formato E.164.</span><span class="sxs-lookup"><span data-stu-id="32398-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="32398-122">Para ejecutar la utilidad de integración de MU de Exchange</span><span class="sxs-lookup"><span data-stu-id="32398-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="32398-123">En un servidor front-end, abra un símbolo del sistema y escriba **CD%\\CommonProgramFiles% soporte de\\Microsoft Lync Server 2013**y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="32398-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="32398-124">Escriba **OcsUmUtil.exe** y pulse Entrar.</span><span class="sxs-lookup"><span data-stu-id="32398-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="32398-125">Haga clic en **Cargar datos** para buscar todos los bosques de Exchange de confianza.</span><span class="sxs-lookup"><span data-stu-id="32398-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="32398-126">En la lista **Planes de marcado de SIP**, seleccione un plan de marcado de SIP de MU para el que desee crear objetos de contacto y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="32398-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="32398-p104">En el cuadro **Contacto**, acepte la unidad organizativa predeterminada o haga clic en **Examinar** para iniciar el **Selector de unidad organizativa**. En el cuadro **Selector de unidad organizativa**, puede seleccionar una unidad organizativa y hacer clic en **Aceptar**, o puede hacer clic en **Crear nueva unidad organizativa** para crear una nueva unidad organizativa en la raíz o en cualquier otra unidad organizativa del dominio (por ejemplo, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com") y, a continuación, hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32398-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32398-129">El nombre distintivo (DN) de la unidad organizativa que ha seleccionado o creado se muestra ahora en el cuadro <STRONG>Unidad organizativa</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="32398-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="32398-130">En el cuadro **Nombre**, acepte el nombre del plan de marcado predeterminado o escriba un nuevo nombre para mostrar para el objeto de contacto que está creando.</span><span class="sxs-lookup"><span data-stu-id="32398-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32398-131">Por ejemplo, si va a crear un objeto de contacto de acceso de suscriptor, podría denominarlo simplemente Acceso de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="32398-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="32398-132">En el cuadro **Dirección SIP**, acepte la dirección SIP predeterminada o escriba una nueva dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="32398-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32398-133">Si escribe una nueva dirección SIP, esta debe empezar por <STRONG>SIP:</STRONG> (es decir, "SIP:" incluidos los dos puntos).</span><span class="sxs-lookup"><span data-stu-id="32398-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="32398-134">En la lista **servidor o grupo** de servidores, seleccione el servidor Standard Edition o el grupo de servidores front-end en el que se va a habilitar el objeto de contacto.</span><span class="sxs-lookup"><span data-stu-id="32398-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32398-135">Preferiblemente, el grupo de servidores que seleccione debe ser el mismo que el servidor en el que se han implementado los usuarios habilitados para Enterprise Voice y MU de Exchange.</span><span class="sxs-lookup"><span data-stu-id="32398-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="32398-136">En la lista **Número de teléfono**, seleccione **Escriba el número de teléfono** o **Use este número piloto de mensajería unificada de Exchange** y escriba un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="32398-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="32398-137">En la lista **Tipo de contacto**, seleccione el tipo de contacto que desea crear y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32398-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="32398-138">Repita los pasos del 1 al 10 para los objetos de contacto adicionales que desee crear.</span><span class="sxs-lookup"><span data-stu-id="32398-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32398-p105">Debe crear al menos un contacto para cada operador automático. Si desea tener acceso externo, necesita también un contacto Acceso de suscriptor y especificar números DID (llamada directa a la extensión).</span><span class="sxs-lookup"><span data-stu-id="32398-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="32398-p106">Para comprobar que se han creado los objetos de contacto, abra Usuarios y equipos de Active Directory y seleccione la unidad organizativa en la que se crearon los objetos. Los objetos de contacto deben aparecer en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="32398-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="32398-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="32398-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

