---
title: 'Lync Server 2013: Crear o editar proveedores federados de SIP hospedados'
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
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="a446e-102">Crear o editar proveedores federados de SIP hospedados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a446e-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a446e-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a446e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a446e-104">La conectividad de mensajería instantánea (mi) de proveedor hospedado permite a los usuarios de su organización usar la mensajería instantánea para comunicarse con los usuarios de los servicios de mensajería instantánea proporcionados por proveedores hospedados, como Microsoft Office 365 y Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a446e-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="a446e-105">Cada proveedor alojado se configura con el nombre de dominio completo del servidor perimetral del proveedor, y el nivel de verificación predeterminado **permite a los usuarios comunicarse solo con las personas de su lista de contactos que usen este proveedor**.</span><span class="sxs-lookup"><span data-stu-id="a446e-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="a446e-106">Use el procedimiento siguiente para crear o editar proveedores hospedados:</span><span class="sxs-lookup"><span data-stu-id="a446e-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="a446e-107">Para crear o editar proveedores hospedados</span><span class="sxs-lookup"><span data-stu-id="a446e-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="a446e-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a446e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a446e-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a446e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a446e-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a446e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a446e-111">En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, a continuación, haga clic en **proveedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="a446e-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="a446e-112">Si necesita crear un nuevo proveedor alojado, haga clic en **nuevo** y, a continuación, haga clic en **proveedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="a446e-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="a446e-113">Si necesita modificar una entrada de la lista de proveedores hospedados, seleccione un proveedor hospedado, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="a446e-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="a446e-114">En la página **Editar proveedor federado de SIP** , puede escribir o modificar las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="a446e-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="a446e-115">**Habilitar las comunicaciones con este proveedor**   al seleccionar esta opción se habilitan las comunicaciones con los usuarios de este proveedor.</span><span class="sxs-lookup"><span data-stu-id="a446e-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="a446e-116">**Nombre del proveedor:**   una propiedad obligatoria, escriba el nombre del proveedor, ya que se reflejará en la lista de proveedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="a446e-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="a446e-117">**Servicio perimetral de acceso (FQDN):**   una propiedad obligatoria, escriba el nombre de dominio completo del servicio perimetral de acceso del proveedor hospedado que está configurando.</span><span class="sxs-lookup"><span data-stu-id="a446e-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="a446e-118">Esta información debe proporcionarla el proveedor hospedado y solo se debe cambiar si el proveedor hospedado realiza un cambio en el FQDN del servicio perimetral de acceso en el proveedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="a446e-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="a446e-119">**Nivel de verificación predeterminado:**   la configuración predeterminada, **permitir que los usuarios se comuniquen con personas de su lista de contactos que usan este proveedor** , limitará la comunicación a los contactos que haya aceptado y estarán en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="a446e-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="a446e-120">Si selecciona **permitir que los usuarios se comuniquen con todos los usuarios con este proveedor** , se eliminará la restricción que debe haber recibido y aceptado una invitación de contacto.</span><span class="sxs-lookup"><span data-stu-id="a446e-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="a446e-121">Esta configuración no limita quién puede ponerse en contacto contigo desde la red del proveedor alojado.</span><span class="sxs-lookup"><span data-stu-id="a446e-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="a446e-122">Cuando haya terminado de configurar la configuración, haga clic en **confirmar** para guardar o en **Cancelar** para descartar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a446e-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a446e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a446e-123">See Also</span></span>


[<span data-ttu-id="a446e-124">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a446e-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="a446e-125">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a446e-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

