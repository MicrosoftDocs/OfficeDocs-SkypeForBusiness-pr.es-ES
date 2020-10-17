---
title: 'Lync Server 2013: creación o edición de proveedores federados de SIP hospedados'
description: 'Lync Server 2013: creación o edición de proveedores federados de SIP hospedados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaaa1b29b9a85332b85dfb7a1f258503fa4e9c77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553886"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="11d10-103">Creación o edición de proveedores federados de SIP hospedados Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d10-103">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d10-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="11d10-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="11d10-105">La conectividad de mensajería instantánea (mi) de proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados, incluidos Microsoft 365 y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="11d10-105">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="11d10-106">Cada proveedor hospedado se configura con el nombre de dominio completo del servidor perimetral del proveedor y el nivel de verificación predeterminado **Permitir a los usuarios comunicarse solamente con personas de su Lista de contactos que utilizan este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="11d10-106">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="11d10-107">Utilice los siguientes procedimientos para crear o editar proveedores hospedados:</span><span class="sxs-lookup"><span data-stu-id="11d10-107">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="11d10-108">Para crear o editar proveedores hospedados</span><span class="sxs-lookup"><span data-stu-id="11d10-108">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="11d10-109">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11d10-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11d10-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11d10-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11d10-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="11d10-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11d10-112">En el barra de navegación izquierda, haga clic en **Acceso externo y de federación** y, a continuación, en **Proveedores federados de SIP**.</span><span class="sxs-lookup"><span data-stu-id="11d10-112">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="11d10-113">Si necesita crear un nuevo proveedor hospedado, haga clic en **Nuevo** y, a continuación, haga clic en **Proveedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="11d10-113">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="11d10-114">Si necesita editar una entrada de la lista de Proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="11d10-114">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="11d10-115">En la página **Editar proveedor federado de SIP**, puede escribir o editar la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="11d10-115">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="11d10-116">**Habilitar comunicaciones con este proveedor**     La selección de esta opción habilita las comunicaciones con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="11d10-116">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="11d10-117">**Nombre del proveedor:**     Una propiedad necesaria, escriba el nombre del proveedor tal y como se reflejará en la lista de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="11d10-117">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="11d10-118">**Servicio perimetral de acceso (FQDN):**     Una propiedad necesaria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que va a configurar.</span><span class="sxs-lookup"><span data-stu-id="11d10-118">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="11d10-119">Esta información debe ser proporcionada por el proveedor hospedado y solo debe modificarse si el proveedor hospedado realiza un cambio al FQDN del servicio perimetral de acceso del proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="11d10-119">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="11d10-120">**Nivel de verificación predeterminado:**     La configuración predeterminada, **permitir que los usuarios se comuniquen con las personas de su lista de contactos que utilizan este proveedor** , limitará la comunicación a los contactos que haya aceptado y que se encuentren en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="11d10-120">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="11d10-p103">Seleccionar **Permitir a los usuarios comunicarse con todos los que utilizan este proveedor** elimina la restricción de tener que haber recibido y aceptado una invitación de contacto. Esta configuración no limita quién puede contactarlo desde la red del proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="11d10-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="11d10-123">Cuando haya terminado de configurar los parámetros, haga clic en **Confirmar** para guardar o haga clic en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="11d10-123">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11d10-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11d10-124">See Also</span></span>


[<span data-ttu-id="11d10-125">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d10-125">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="11d10-126">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d10-126">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

