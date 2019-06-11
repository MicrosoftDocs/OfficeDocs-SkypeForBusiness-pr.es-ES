---
title: 'Lync Server 2013: inscribir usuarios para la autenticación de tarjetas inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="c0942-102">Inscribir usuarios para la autenticación de tarjetas inteligentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0942-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0942-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="c0942-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="c0942-p101">En general, existen dos métodos para inscribir a los usuarios en la autenticación de tarjeta inteligente. El método más sencillo consiste en que los usuarios se inscriban directamente en la autenticación de tarjeta inteligente a través de la inscripción web; el más complejo consiste en usar un Enrollment Agent. Este tema se centra en la autoinscripción para usar certificados de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="c0942-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="c0942-107">Para obtener más información sobre la inscripción en nombre de los usuarios como agente de inscripción, consulte inscribirse para certificados en nombre de otros usuarios [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)en.</span><span class="sxs-lookup"><span data-stu-id="c0942-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="c0942-108">Para inscribir a usuarios en la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="c0942-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="c0942-109">Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="c0942-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="c0942-110">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c0942-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="c0942-111">Vaya a la página de **inscripción Web** de la entidad emisora de certificados (por ejemplo,. https://MyCA.contoso.com/certsrv)</span><span class="sxs-lookup"><span data-stu-id="c0942-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0942-112">Si usa Internet Explorer 10, puede que tenga que ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c0942-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="c0942-113">En la página **principal**, elija **Solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="c0942-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="c0942-114">Luego elija **Solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="c0942-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="c0942-115">Elija **Crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="c0942-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="c0942-116">Seleccione **Usuario de tarjeta inteligente** en la sección **Plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c0942-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="c0942-117">En **Opciones de clave**, confirme la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="c0942-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="c0942-118">Active el botón de radio **Crear conjunto de claves nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c0942-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="c0942-119">En **CSP**, seleccione **Proveedor base de cifrado para tarjetas inteligentes de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c0942-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="c0942-120">En **Uso de la clave**, seleccione **Exchange** (es la única opción disponible).</span><span class="sxs-lookup"><span data-stu-id="c0942-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="c0942-121">En **Tamaño de la clave**, escriba **2048**.</span><span class="sxs-lookup"><span data-stu-id="c0942-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="c0942-122">Confirme que está activado **Nombre automático de contenedor de claves**.</span><span class="sxs-lookup"><span data-stu-id="c0942-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="c0942-123">Deje las demás casillas desactivadas.</span><span class="sxs-lookup"><span data-stu-id="c0942-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="c0942-124">En **Opciones adicionales**, confirme los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c0942-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="c0942-125">En **Formato de la solicitud**, seleccione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="c0942-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="c0942-126">En **Algoritmo hash**, seleccione **sha1**.</span><span class="sxs-lookup"><span data-stu-id="c0942-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="c0942-127">En **Nombre descriptivo**, escriba **Smardcard Certificate**.</span><span class="sxs-lookup"><span data-stu-id="c0942-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="c0942-128">Si utiliza un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0942-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="c0942-129">Haga clic en **Enviar** para enviar la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="c0942-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="c0942-130">Cuando se le pida, escriba el PIN que se usó para crear la tarjeta inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="c0942-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0942-131">El valor del PIN de tarjeta inteligente virtual predeterminado es “12345678”.</span><span class="sxs-lookup"><span data-stu-id="c0942-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="c0942-132">Una vez emitido el certificado, haga clic en **Instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="c0942-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0942-133">Si la solicitud de certificado presenta el error “Este explorador web no es compatible con la creación de solicitudes de certificados”, hay tres formas de resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="c0942-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="c0942-134">Habilitar la Vista de compatibilidad en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c0942-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c0942-135">Habilitar la opción Activar configuración de Intranet en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c0942-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c0942-136">Activar la opción Restablecer todas las zonas al nivel predeterminado en la pestaña Seguridad del menú de opciones de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c0942-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

