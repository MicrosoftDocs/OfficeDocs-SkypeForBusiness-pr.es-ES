---
title: 'Lync Server 2013: crear o editar proveedores federados de SIP públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 795950427023a193eff3ab0012687e381e3d3eff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="e1f0e-102">Crear o editar proveedores federados de SIP públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f0e-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1f0e-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e1f0e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e1f0e-104">La conectividad de mensajería instantánea pública permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por los proveedores de servicios de\!mensajería instantánea públicos, como Windows Live Messenger, Yahoo y AOL.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="e1f0e-105">Lync Server 2013 tiene configuraciones de proveedor público para America Online, Windows Live y Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="e1f0e-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="e1f0e-106">mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-106">instant messaging.</span></span> <span data-ttu-id="e1f0e-107">Cada proveedor público se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **permite a los usuarios comunicarse sólo con las personas de su lista de contactos que usan este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="e1f0e-108">Como configuración predeterminada, no está habilitado ninguno de los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="e1f0e-109">Debe rellenar el contrato de licencia y proporcionar el trabajo antes de habilitar los proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="e1f0e-110">Puede habilitar al proveedor antes de completar la licencia y proporcionar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="e1f0e-111">Los usuarios no podrán comunicarse con los contactos de estos proveedores hasta que haya finalizado el trabajo como requisito previo.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="e1f0e-112">Para obtener más información sobre la concesión de licencias y el aprovisionamiento de proveedores públicos, vea [Configure Policies to control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e1f0e-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="e1f0e-113">Use el siguiente procedimiento para crear o cambiar proveedores públicos.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="e1f0e-114">Para crear o cambiar proveedores públicos</span><span class="sxs-lookup"><span data-stu-id="e1f0e-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="e1f0e-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e1f0e-116">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e1f0e-117">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e1f0e-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e1f0e-118">En el barra de navegación izquierda, haga clic en **Acceso externo y federación** y luego en **Proveedores SIP federados**.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="e1f0e-119">Si necesita crear un nuevo proveedor público, haga clic en **Nuevo** y luego en **Proveedor público**.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="e1f0e-120">Si desea cambiar una entrada de la lista de los proveedores públicos, seleccione un proveedor público, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="e1f0e-121">En la página **Editar proveedor SIP federado**, puede escribir o cambiar los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e1f0e-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="e1f0e-122">**Habilitar comunicaciones con este proveedor**   : al seleccionar esta opción, se permite la mensajería instantánea con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="e1f0e-123">**Nombre del proveedor:**   una propiedad necesaria, escriba el nombre del proveedor tal y como se reflejará en la lista de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="e1f0e-124">**Servicio perimetral de acceso (FQDN):**   una propiedad necesaria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor que está configurando.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="e1f0e-125">Esta información se proporciona como un elemento predeterminado y debe cambiarse solo si el proveedor cambia el FQDN del servicio perimetral de acceso en el proveedor de público.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="e1f0e-126">**Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir a los usuarios comunicarse con personas de su lista de contactos que utilizan este proveedor** , limitará la comunicación a los contactos que haya aceptado y que se encuentren en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="e1f0e-p105">La activación de **Permitir a los usuarios comunicarse con todos los que usan este proveedor** elimina la restricción que debe haber recibido y aceptado como una invitación de contacto. Este parámetro no limita quién puede comunicarse con usted desde la red del proveedor público.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-p105">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="e1f0e-129">Cuando haya finalizado la configuración de este parámetro, haga clic en **Confirmar** para guardar o en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e1f0e-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1f0e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f0e-130">See Also</span></span>


[<span data-ttu-id="e1f0e-131">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f0e-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="e1f0e-132">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f0e-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

