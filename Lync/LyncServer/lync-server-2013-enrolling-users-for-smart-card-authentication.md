---
title: 'Lync Server 2013: inscripción de usuarios para la autenticación de tarjeta inteligente'
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
ms.openlocfilehash: a1d60a29eff876ef362d15c90e2615fd70bc8774
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41993815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="755b1-102">Inscripción de usuarios para la autenticación de tarjeta inteligente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="755b1-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="755b1-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="755b1-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="755b1-104">Generalmente hay dos métodos para inscribir a los usuarios para la autenticación de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="755b1-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="755b1-105">El método más sencillo implica que los usuarios se inscriban directamente en la autenticación de tarjetas inteligentes mediante la inscripción Web, mientras que el método más complejo implica el uso de un agente de inscripción.</span><span class="sxs-lookup"><span data-stu-id="755b1-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="755b1-106">Este tema se centra en la inscripción automática de certificados de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="755b1-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="755b1-107">Para obtener más información sobre la inscripción en nombre de usuarios como agente de inscripción, consulte inscribirse para certificados en nombre de otros usuarios en [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span><span class="sxs-lookup"><span data-stu-id="755b1-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="755b1-108">Para inscribir usuarios para la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="755b1-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="755b1-109">Inicie sesión en la estación de trabajo Windows 8 con las credenciales de un usuario habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="755b1-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="755b1-110">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="755b1-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="755b1-111">Vaya a la página de **inscripción Web** de la entidad de https://MyCA.contoso.com/certsrv)certificación (por ejemplo,.</span><span class="sxs-lookup"><span data-stu-id="755b1-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="755b1-112">Si usa Internet Explorer 10, es posible que deba ver este sitio web en modo de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="755b1-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="755b1-113">En la página **principal** , seleccione **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="755b1-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="755b1-114">A continuación, seleccione **solicitud avanzada**.</span><span class="sxs-lookup"><span data-stu-id="755b1-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="755b1-115">Seleccione **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="755b1-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="755b1-116">Seleccione **usuario de tarjeta inteligente** en la sección **plantilla de certificado** y complete la solicitud de certificado avanzada con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="755b1-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="755b1-117">**Las opciones de clave** confirman la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="755b1-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="755b1-118">Seleccione el botón de opción **crear conjunto de claves nuevo**</span><span class="sxs-lookup"><span data-stu-id="755b1-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="755b1-119">Para **CSP**, seleccione **proveedor base de cifrado de tarjetas inteligentes de Microsoft**</span><span class="sxs-lookup"><span data-stu-id="755b1-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="755b1-120">En **uso**de la clave, seleccione **Exchange** (esta es la única opción disponible).</span><span class="sxs-lookup"><span data-stu-id="755b1-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="755b1-121">En **tamaño de clave**, escriba **2048**</span><span class="sxs-lookup"><span data-stu-id="755b1-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="755b1-122">Confirmar que **el nombre del contenedor de claves automático** está seleccionado</span><span class="sxs-lookup"><span data-stu-id="755b1-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="755b1-123">Deje las demás casillas desactivadas.</span><span class="sxs-lookup"><span data-stu-id="755b1-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="755b1-124">En **opciones adicionales** , confirme los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="755b1-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="755b1-125">En **formato de solicitud** , seleccione **CMC**.</span><span class="sxs-lookup"><span data-stu-id="755b1-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="755b1-126">Para el **algoritmo hash** , seleccione **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="755b1-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="755b1-127">Para **nombre descriptivo** , escriba **Smardcard certificado**.</span><span class="sxs-lookup"><span data-stu-id="755b1-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="755b1-128">Si usa un lector de tarjetas inteligentes físico, inserte la tarjeta inteligente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="755b1-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="755b1-129">Haga clic en **Enviar** para enviar la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="755b1-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="755b1-130">Cuando se le solicite, escriba el PIN que se usó para crear la tarjeta inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="755b1-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="755b1-131">El valor PIN predeterminado de la tarjeta inteligente virtual es "12345678".</span><span class="sxs-lookup"><span data-stu-id="755b1-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="755b1-132">Una vez emitido el certificado, haga clic en **instalar este certificado** para completar el proceso de inscripción.</span><span class="sxs-lookup"><span data-stu-id="755b1-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="755b1-133">Si la solicitud de certificado produce el error "este explorador Web no admite la generación de solicitudes de certificado", hay tres formas posibles de resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="755b1-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="755b1-134">Habilitar la vista de compatibilidad en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="755b1-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="755b1-135">Habilitar la opción Activar configuración de intranet en Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="755b1-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="755b1-136">Seleccione la opción restablecer todas las zonas a nivel predeterminado en la ficha Seguridad en el menú opciones de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="755b1-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

