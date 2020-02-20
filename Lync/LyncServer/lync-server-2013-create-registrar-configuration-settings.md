---
title: 'Lync Server 2013: crear opciones de configuración de registrador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6167e82679aa0124b2ae8833be9d4a9a56df2009
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="672ee-102">Crear opciones de configuración de registrador en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="672ee-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="672ee-103">_**Última modificación del tema:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="672ee-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="672ee-p101">Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:</span><span class="sxs-lookup"><span data-stu-id="672ee-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="672ee-107">**Kerberos**   es el esquema de autenticación basado en contraseña más seguro disponible para los clientes, pero normalmente solo está disponible para los clientes de la empresa, ya que requiere la conexión del cliente a un centro de distribución de claves (controlador de dominio de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="672ee-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="672ee-108">Esta configuración es adecuada si el servidor autentica solo a los clientes de empresa.</span><span class="sxs-lookup"><span data-stu-id="672ee-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="672ee-109">**NTLM**   esta es la autenticación basada en contraseña disponible para los clientes que usan un esquema de hash de desafío-respuesta en la contraseña.</span><span class="sxs-lookup"><span data-stu-id="672ee-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="672ee-110">Esta es la única forma de autenticación disponible para los clientes sin conectividad a un centro de distribución de claves (controlador de dominio de Kerberos), como usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="672ee-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="672ee-111">Si un servidor autentica solo a usuarios remotos, debe elegir NTLM.</span><span class="sxs-lookup"><span data-stu-id="672ee-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="672ee-112">**Autenticación de certificados**   este es el nuevo método de autenticación cuando el servidor necesita obtener certificados de los clientes de Lync Phone Edition, los teléfonos de área común, Lync 2013 y la aplicación de la tienda Windows de Lync.</span><span class="sxs-lookup"><span data-stu-id="672ee-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="672ee-113">En los clientes de Lync Phone Edition, después de que un usuario inicie sesión y se autentique correctamente proporcionando un número de identificación personal (PIN), Lync Server 2013, a continuación, aprovisiona el URI del SIP en el teléfono y aprovisiona un certificado firmado de Lync Server o un certificado de usuario que identifica a Joe (por ejemplo: SN=joe@contoso.com) al teléfono.</span><span class="sxs-lookup"><span data-stu-id="672ee-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="672ee-114">Este certificado se usa para la autenticación con el registrador y los Servicios web.</span><span class="sxs-lookup"><span data-stu-id="672ee-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="672ee-p105">Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.</span><span class="sxs-lookup"><span data-stu-id="672ee-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="672ee-119">Si va a usar los clientes de aplicaciones de la tienda Windows Lync, debe habilitar la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="672ee-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="672ee-120">Siga estos pasos para crear un registrador nuevo.</span><span class="sxs-lookup"><span data-stu-id="672ee-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="672ee-121">Para crear nuevas opciones de configuración del registrador</span><span class="sxs-lookup"><span data-stu-id="672ee-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="672ee-122">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="672ee-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="672ee-123">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="672ee-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="672ee-124">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="672ee-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="672ee-125">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="672ee-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="672ee-126">En la página **Registrador**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="672ee-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="672ee-127">En \*\*Seleccionar un servicio \*\*, haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en \*\*Aceptar \*\*.</span><span class="sxs-lookup"><span data-stu-id="672ee-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="672ee-128">En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:</span><span class="sxs-lookup"><span data-stu-id="672ee-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="672ee-129">**Habilitar autenticación Kerberos**: para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="672ee-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="672ee-130">**Habilitar autenticación NTLM**: para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.</span><span class="sxs-lookup"><span data-stu-id="672ee-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="672ee-131">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="672ee-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="672ee-132">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="672ee-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

