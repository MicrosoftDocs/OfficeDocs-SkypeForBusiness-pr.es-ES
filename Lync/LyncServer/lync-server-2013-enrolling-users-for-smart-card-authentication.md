---
title: 'Lync Server 2013: inscripción de usuarios para la autenticación de tarjeta inteligente'
description: 'Lync Server 2013: inscripción de usuarios para la autenticación de tarjeta inteligente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d67994d2152ac344934d093a1b6f7d482a7933a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558476"
---
# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="6883b-103">Inscripción de usuarios para la autenticación de tarjeta inteligente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6883b-103">Enrolling users for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6883b-104">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="6883b-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="6883b-105">Generalmente hay dos métodos para inscribir a los usuarios para la autenticación de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="6883b-105">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="6883b-106">El método más sencillo implica que los usuarios se inscriban directamente en la autenticación de tarjetas inteligentes mediante la inscripción Web, mientras que el método más complejo implica el uso de un agente de inscripción.</span><span class="sxs-lookup"><span data-stu-id="6883b-106">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="6883b-107">Este tema se centra en la inscripción automática de certificados de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="6883b-107">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="6883b-108">Para obtener más información sobre la inscripción en nombre de usuarios como agente de inscripción, consulte inscribirse para certificados en nombre de otros usuarios en [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367) .</span><span class="sxs-lookup"><span data-stu-id="6883b-108">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="6883b-109">Para inscribir usuarios para la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="6883b-109">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="6883b-110">Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="6883b-110">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="6883b-111">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6883b-111">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="6883b-112">Vaya a la página de **inscripción Web** de la entidad de certificación (por ejemplo, https://MyCA.contoso.com/certsrv) .</span><span class="sxs-lookup"><span data-stu-id="6883b-112">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6883b-113">Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="6883b-113">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="6883b-114">En la página **principal** , seleccione **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="6883b-114">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="6883b-115">A continuación, seleccione **solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="6883b-115">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="6883b-116">Seleccione **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="6883b-116">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="6883b-117">Seleccione **usuario de tarjeta inteligente** en la sección **plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6883b-117">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="6883b-118">**Las opciones de clave** confirman la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6883b-118">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="6883b-119">Seleccione el botón de opción **crear conjunto de claves nuevo**</span><span class="sxs-lookup"><span data-stu-id="6883b-119">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="6883b-120">Para **CSP**, seleccione **proveedor base de cifrado de tarjetas inteligentes de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6883b-120">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="6883b-121">En **uso**de la clave, seleccione **Exchange** (esta es la única opción disponible).</span><span class="sxs-lookup"><span data-stu-id="6883b-121">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="6883b-122">En **tamaño de clave**, escriba **2048**</span><span class="sxs-lookup"><span data-stu-id="6883b-122">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="6883b-123">Confirmar que **el nombre del contenedor de claves automático** está seleccionado</span><span class="sxs-lookup"><span data-stu-id="6883b-123">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="6883b-124">Deje las demás casillas desactivadas.</span><span class="sxs-lookup"><span data-stu-id="6883b-124">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="6883b-125">En **opciones adicionales** , confirme los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6883b-125">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="6883b-126">En **formato de solicitud** , seleccione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="6883b-126">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="6883b-127">Para el **algoritmo hash** , seleccione **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="6883b-127">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="6883b-128">Para **nombre descriptivo** , escriba **Smardcard certificado**.</span><span class="sxs-lookup"><span data-stu-id="6883b-128">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="6883b-129">Si usa un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6883b-129">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="6883b-130">Haga clic en **Enviar** para enviar la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="6883b-130">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="6883b-131">Cuando se le solicite, escriba el PIN que se usó para crear la tarjeta inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="6883b-131">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6883b-132">El valor PIN predeterminado de la tarjeta inteligente virtual es "12345678".</span><span class="sxs-lookup"><span data-stu-id="6883b-132">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="6883b-133">Una vez emitido el certificado, haga clic en **instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="6883b-133">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6883b-134">Si la solicitud de certificado produce el error "este explorador Web no admite la generación de solicitudes de certificado", hay tres formas posibles de resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="6883b-134">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="6883b-135">Habilitar la vista de compatibilidad en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6883b-135">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="6883b-136">Habilitar la opción Activar configuración de intranet en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6883b-136">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="6883b-137">Seleccione la opción restablecer todas las zonas a nivel predeterminado en la ficha Seguridad en el menú opciones de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6883b-137">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

