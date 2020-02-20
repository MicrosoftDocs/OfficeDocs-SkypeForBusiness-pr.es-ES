---
title: 'Lync Server 2013: configurar la telefonía para un usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d10ec9aea5801f91301e5c054b13bba63f8ef29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="70679-102">Configurar la telefonía para un usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70679-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70679-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="70679-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="70679-104">La configuración de telefonía es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server para el usuario (es decir, si el usuario individual se ha habilitado para Lync Server 2013 y la organización admite telefonía).</span><span class="sxs-lookup"><span data-stu-id="70679-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="70679-105">Entre las opciones de telefonía de usuario de Lync Server se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="70679-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="70679-106">**Audio/vídeo deshabilitado**   el usuario no puede realizar llamadas con audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="70679-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="70679-107">**Solo de PC a PC**   el usuario solo puede realizar llamadas de audio o vídeo de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="70679-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="70679-108">**Telefonía IP**   empresarial el usuario puede usar la infraestructura de Lync Server 2013 para enrutar todas las llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="70679-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="70679-109">También puede realizar llamadas de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="70679-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="70679-110">**Control remoto de llamadas**   el usuario puede usar Lync Server 2013 para controlar el teléfono de escritorio y también puede realizar llamadas de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="70679-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="70679-111">Para obtener más información sobre cómo configurar la telefonía para una organización, vea [Configure Telephony for a User in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="70679-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="70679-112">Para configurar la telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="70679-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="70679-113">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="70679-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70679-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70679-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70679-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70679-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70679-116">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="70679-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="70679-117">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="70679-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="70679-118">En la tabla, haga clic en la cuenta de usuario que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="70679-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="70679-119">En el menú **Editar**, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="70679-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="70679-120">En **Telefonía**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="70679-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="70679-121">Para deshabilitar las llamadas de audio y vídeo del usuario, haga clic en **Audio y vídeo deshabilitados**.</span><span class="sxs-lookup"><span data-stu-id="70679-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="70679-p103">Para habilitar las comunicaciones de audio de equipo a equipo para el usuario, pero no el control remoto de llamadas ni la Telefonía IP empresarial, haga clic en **Solo de equipo a equipo**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="70679-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="70679-124">Para enrutar las llamadas de teléfono del usuario mediante la infraestructura de Lync Server 2010 de acuerdo con la Directiva de clase de servicio, incluida la comunicación de audio de PC a PC, haga clic en **telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="70679-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="70679-125">En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="70679-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="70679-126">En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="70679-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="70679-127">Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="70679-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="70679-128">Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea telefónica de escritorio desde Lync Server 2013 para realizar llamadas de equipo a equipo y llamadas de equipo a teléfono, haga clic en **control remoto de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="70679-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="70679-129">En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="70679-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="70679-130">El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="70679-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70679-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="70679-131">See Also</span></span>


[<span data-ttu-id="70679-132">Modificación de las propiedades de la cuenta de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70679-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

