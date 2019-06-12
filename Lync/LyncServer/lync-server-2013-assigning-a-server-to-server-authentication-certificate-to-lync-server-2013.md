---
title: Asignación de un certificado de autenticación de servidor a servidor a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d4e5e3ac8c544e83ab9cfb8f82a5c70f86131b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="02e14-102">Asignación de un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e14-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02e14-103">_**Última modificación del tema:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="02e14-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="02e14-104">Para determinar si un certificado de autenticación de servidor a servidor ya se ha asignado a Microsoft Lync Server 2013, ejecute el siguiente comando desde el shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="02e14-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="02e14-105">Si no recibe información del certificado, necesita asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="02e14-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="02e14-106">Como regla general, cualquier certificado de Lync Server 2013 se puede usar como certificado de OAuthTokenIssuer; por ejemplo, su certificado predeterminado de Lync Server 2013 también se puede usar como el certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="02e14-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="02e14-107">(El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor Web que incluya el nombre de su dominio SIP en el campo asunto). Los dos requisitos principales para el certificado que se usa para la autenticación de servidor a servidor son los siguientes: 1) el mismo certificado se debe configurar como el certificado de OAuthTokenIssuer en todos los servidores front-end; y 2) el certificado debe tener al menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="02e14-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="02e14-108">Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="02e14-108">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="02e14-109">Una vez que haya solicitado y obtenido el nuevo certificado, puede iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar al siguiente para importar y asignar ese certificado:</span><span class="sxs-lookup"><span data-stu-id="02e14-109">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="02e14-110">En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado.</span><span class="sxs-lookup"><span data-stu-id="02e14-110">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="02e14-111">Este procedimiento debe ejecutarse una sola vez: el servicio de replicación de Lync Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-111">This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="02e14-112">Como alternativa, puede usar un certificado existente como certificado de autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="02e14-112">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="02e14-113">(Como se indica, el certificado predeterminado puede usarse como certificado de autenticación de servidor a servidor). El siguiente par de comandos de Windows PowerShell recupera el valor de la propiedad Thumbprint del certificado predeterminado y luego usa ese valor para convertir el certificado predeterminado en el certificado de autenticación de servidor a servidor:</span><span class="sxs-lookup"><span data-stu-id="02e14-113">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="02e14-114">En el comando anterior, el certificado recuperado está configurado para funcionar como certificado de autenticación de servidor a servidor global; eso significa que el certificado será replicado y usado por todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-114">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="02e14-115">De nuevo, este comando solo se debe ejecutar una vez y solo en uno de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-115">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="02e14-116">Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-116">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="02e14-117">En su lugar, configure el certificado una vez y deje que el servidor de replicación de Lync Server tenga cuidado al copiar ese certificado en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="02e14-117">Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="02e14-118">El cmdlet Set-CsCertificate toma el certificado en cuestión y lo configura inmediatamente para que actúe como el certificado de OAuthTokenIssuer actual.</span><span class="sxs-lookup"><span data-stu-id="02e14-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="02e14-119">(Lync Server 2013 conserva dos copias de un tipo de certificado: el certificado actual y el certificado anterior). Si necesita que el nuevo certificado empiece a funcionar inmediatamente como el certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="02e14-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="02e14-120">También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="02e14-120">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="02e14-121">"Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="02e14-121">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="02e14-122">Por ejemplo, este comando recupera el certificado predeterminado y, después, configura ese certificado para que tome el control como el certificado de OAuthTokenIssuer actual a partir del 1 de julio de 2012:</span><span class="sxs-lookup"><span data-stu-id="02e14-122">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="02e14-123">El 1 de julio de 2012 el nuevo certificado se configurará como el certificado de OAuthTokenIssuer actual y el certificado de OAuthTokenIssuer "antiguo" se configurará como el certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="02e14-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="02e14-124">Si no desea usar Windows PowerShell, también puede usar la consola MMC certificados para exportar un certificado de un servidor front-end y, a continuación, importar ese mismo certificado en todos los demás servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-124">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="02e14-125">Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.</span><span class="sxs-lookup"><span data-stu-id="02e14-125">If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="02e14-126">En este caso, el procedimiento debe realizarse en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="02e14-127">Al exportar e importar certificados de esta forma, Lync Server 2013 no replicará ese certificado en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="02e14-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="02e14-128">Una vez que el certificado se ha importado a todos los servidores front-end, ese certificado se puede asignar mediante el Asistente para la implementación de Lync Server en lugar de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02e14-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="02e14-129">Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:</span><span class="sxs-lookup"><span data-stu-id="02e14-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="02e14-130">Haga clic en Inicio, seleccione todos los programas, **Microsoft Lync server 2013**y, a continuación, haga clic en **Asistente de implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="02e14-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="02e14-131">En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="02e14-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="02e14-132">En la página Microsoft Lync Server 2013, haga clic en el botón **Ejecutar** bajo el título **paso 3: solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="02e14-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="02e14-133">Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="02e14-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="02e14-134">En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="02e14-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="02e14-135">En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02e14-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="02e14-136">En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02e14-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="02e14-137">En la página Resumen de asignación de certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="02e14-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="02e14-138">En la página Ejecutar comandos, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="02e14-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="02e14-139">Cierre el Asistente para certificados y el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="02e14-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

