---
title: 'Lync Server 2013: Configurar los certificados para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="ed581-102">Configurar los certificados para el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed581-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed581-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ed581-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed581-104">Cuando ejecute el Asistente para certificados, asegúrese de haber iniciado sesión con una cuenta que sea miembro de un grupo al que se le hayan asignado los permisos adecuados para el tipo de plantilla de certificado que va a usar.</span><span class="sxs-lookup"><span data-stu-id="ed581-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="ed581-105">De forma predeterminada, una solicitud de certificado de Lync Server 2013 usará la plantilla de certificado de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="ed581-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="ed581-106">Si usa una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado con esta plantilla, compruebe que el grupo tiene asignados los permisos de inscripción necesarios para usar esa plantilla.</span><span class="sxs-lookup"><span data-stu-id="ed581-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="ed581-107">Cada director requiere un certificado predeterminado, un certificado interno de la web y un certificado externo Web.</span><span class="sxs-lookup"><span data-stu-id="ed581-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="ed581-108">Para obtener más información sobre los requisitos de certificados para directores, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="ed581-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="ed581-109">Use el siguiente procedimiento para configurar certificados de director.</span><span class="sxs-lookup"><span data-stu-id="ed581-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="ed581-110">Repita el procedimiento para cada director.</span><span class="sxs-lookup"><span data-stu-id="ed581-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="ed581-111">Los pasos de este procedimiento describen cómo configurar un certificado de una entidad de certificación (CA) raíz interna de empresa implementada por su organización y con procesamiento de solicitudes sin conexión.</span><span class="sxs-lookup"><span data-stu-id="ed581-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="ed581-112">Para obtener más información sobre cómo obtener certificados de una entidad emisora externa, póngase en contacto con el equipo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ed581-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="ed581-113">Para configurar certificados para el grupo de directores o directores</span><span class="sxs-lookup"><span data-stu-id="ed581-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="ed581-114">En el Asistente para la implementación de Lync Server, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ed581-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="ed581-115">En la página **Asistente para certificados**, haga clic en **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="ed581-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="ed581-116">En la página **solicitud de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="ed581-117">En la página **peticiones demoradas o inmediatas** , acepte la opción predeterminada **enviar la solicitud inmediatamente a una entidad emisora de certificados en línea** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="ed581-118">En la página **elegir una entidad emisora de certificados (CA)** , haga clic en la entidad emisora de certificados interna de Windows que desea usar y, después, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="ed581-119">En la página de la cuenta de la entidad emisora de **certificados** , especifique las credenciales alternativas que se usarán si la cuenta con la que inició sesión no tiene suficiente autoridad para solicitar el certificado y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="ed581-120">En la página **especificar plantilla de certificado alternativa** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="ed581-121">En la página **nombre y configuración de seguridad** , puede especificar un **nombre descriptivo**, aceptar la 2048 y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="ed581-122">En la página información de la **organización** , especifique la información de la organización y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="ed581-123">En la página **información geográfica** , especifique la información geográfica opcional y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="ed581-124">En la página **nombre del asunto/nombres alternativos del asunto** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed581-125">La lista nombre alternativo del sujeto debe contener el nombre del equipo en el que está instalando el director (si es un único Director) o el nombre del grupo de directores, y los nombres simples de la dirección URL configurados para la organización.</span><span class="sxs-lookup"><span data-stu-id="ed581-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="ed581-126">En la página **configuración del dominio SIP de los nombres alternativos de asunto (San)** , seleccione los **dominios SIP configurados** para todos los dominios que quiera que controle el director y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="ed581-127">En la página **configurar nombres alternativos de asunto adicionales** , agregue los nombres alternativos de asunto adicionales necesarios y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="ed581-128">En la página **Resumen de solicitud de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="ed581-129">En la página **comandos en ejecución** , haga clic en **siguiente** una vez que los comandos hayan terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ed581-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="ed581-130">En la página estado de la **solicitud de certificado en línea** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ed581-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="ed581-131">En la página **asignación de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed581-132">Si desea ver el certificado, haga doble clic en el certificado de la lista.</span><span class="sxs-lookup"><span data-stu-id="ed581-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="ed581-133">En la página **Resumen de asignación de certificado** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ed581-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="ed581-134">En la página **comandos en ejecución** , haga clic en **Finalizar** después de que los comandos hayan terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ed581-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="ed581-135">En la página **Asistente para certificados** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ed581-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

