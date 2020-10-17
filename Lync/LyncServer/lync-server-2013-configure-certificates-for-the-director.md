---
title: 'Lync Server 2013: configurar certificados para el director'
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
ms.openlocfilehash: e257d62e761b33dad737f9d37da5f561703183ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521057"
---
# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="e8b03-102">Configurar certificados para el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8b03-102">Configure certificates for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8b03-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e8b03-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8b03-104">Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use.</span><span class="sxs-lookup"><span data-stu-id="e8b03-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="e8b03-105">De forma predeterminada, una solicitud de certificado 2013 de Lync Server usará la plantilla de certificado del servidor Web.</span><span class="sxs-lookup"><span data-stu-id="e8b03-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="e8b03-106">Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e8b03-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="e8b03-107">Cada director necesita un certificado predeterminado, así como certificado web interno y otro externo.</span><span class="sxs-lookup"><span data-stu-id="e8b03-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="e8b03-108">Para obtener más información sobre los requisitos de certificados para directores, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="e8b03-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="e8b03-p103">Use el siguiente procedimiento para configurar certificados de director (repítalo con cada uno de los directores). Los pasos de este procedimiento detallan cómo se configura un certificado procedente de una entidad de certificación raíz de empresa interna implementada por la organización y con procesamiento de una solicitud sin conexión. Para obtener información detallada sobre cómo obtener certificados de una CA externa, póngase en contacto con el equipo de atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="e8b03-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="e8b03-113">Para configurar certificados para el director o grupo de directores</span><span class="sxs-lookup"><span data-stu-id="e8b03-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="e8b03-114">En el Asistente para la implementación de Lync Server, junto a **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="e8b03-115">En la página **Asistente para certificados**, haga clic en **Solicitud**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="e8b03-116">En la página **Solicitud de certificado**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="e8b03-117">En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="e8b03-118">En la página **Elegir una entidad de certificación**, haga clic en la entidad de certificación de Windows interna que desee usar y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="e8b03-119">En la página **Cuenta de entidad de certificación**, especifique las credenciales que se van a usar de forma alternativa en caso de que la cuenta con la que se ha iniciado sesión no tenga suficiente autoridad para solicitar el certificado. A continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="e8b03-120">En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="e8b03-121">En la página **Nombre y configuración de seguridad**, puede indicar un **Nombre descriptivo**, aceptar la longitud de clave de 2048 bits y hacer clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="e8b03-122">En la página **Información de la organización**, aporte información sobre la organización si lo desea y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="e8b03-123">En la página **Información geográfica**, aporte información geográfica si lo desea y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="e8b03-124">En la página **Nombre del sujeto o nombres alternativos del sujeto**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8b03-125">En la lista de nombres alternativos del sujeto debe figurar el nombre del equipo en el que se va a instalar el director (si se trata de uno solo) o el nombre del grupo de directores, así como los nombres de las direcciones URL sencillas configuradas para la organización.</span><span class="sxs-lookup"><span data-stu-id="e8b03-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="e8b03-126">En la página **Configuración de dominio SIP**, seleccione **Dominios SIP configurados** para todos los dominios que quiera que el director controle y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="e8b03-127">En la página **Configurar nombres de sujeto alternativos adicionales**, agregue los nombres de sujeto alternativos adicionales que desee y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="e8b03-128">En la página **Resumen de la solicitud de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="e8b03-129">En la página **Ejecución de comandos**, haga clic en **Siguiente** cuando los comandos hayan terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e8b03-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="e8b03-130">En la página **Estado de solicitud del certificado en línea**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="e8b03-131">En la página **Asignación de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8b03-132">Si desea ver el certificado, haga doble clic en él en la lista.</span><span class="sxs-lookup"><span data-stu-id="e8b03-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="e8b03-133">En la página **Resumen de asignación de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="e8b03-134">En la página **Ejecución de comandos**, haga clic en **Finalizar** cuando los comandos hayan terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e8b03-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="e8b03-135">En la página **Asistente para certificados**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e8b03-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

