---
title: Asignar un certificado de autenticación de servidor a servidor a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d82974f45ab06024f2834609403ed6604067bb2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a><span data-ttu-id="6f143-102">Asignar un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f143-102">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f143-103">_**Última modificación del tema:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="6f143-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="6f143-104">Para determinar si ya se ha asignado un certificado de autenticación de servidor a servidor a Microsoft Lync Server 2013, ejecute el siguiente comando desde el shell de administración de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6f143-104">To determine whether or not a server-to-server authentication certificate has already been assigned to Microsoft Lync Server 2013, run the following command from the Lync Server 2013 Management Shell:</span></span>

    Get-CsCertificate -Type OAuthTokenIssuer

<span data-ttu-id="6f143-105">Si no recibe información del certificado, debe asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="6f143-105">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="6f143-106">Como regla general, se puede usar cualquier certificado 2013 de Lync Server como certificado OAuthTokenIssuer; por ejemplo, el certificado predeterminado de Lync Server 2013 también puede usarse como certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="6f143-106">As a general rule, any Lync Server 2013 certificate can be used as your OAuthTokenIssuer certificate; for example, your Lync Server 2013 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="6f143-107">(El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor Web que incluya el nombre de su dominio SIP en el campo Subject). Los dos requisitos principales para el certificado que se usan para la autenticación de servidor a servidor son los siguientes: 1) el mismo certificado debe configurarse como el certificado OAuthTokenIssuer en todos los servidores front-end; y 2) el certificado debe tener al menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="6f143-107">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>

<span data-ttu-id="6f143-p102">Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Una vez haya solicitado y obtenido el nuevo certificado, podrá iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar a este para importar y asignar el certificado:</span><span class="sxs-lookup"><span data-stu-id="6f143-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

<span data-ttu-id="6f143-p103">En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado. Este procedimiento debe ejecutarse una sola vez: el servicio de replicación de Lync Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6f143-p103">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate. This procedure should be run just one time: Lync Server's replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>

<span data-ttu-id="6f143-p104">También puede usar un certificado actual como certificado de autenticación de servidor a servidor. Como se ha mencionado, el certificado predeterminado se puede usar como certificado de autenticación de servidor a servidor. Los dos comandos siguientes de Windows PowerShell recuperan el valor de la propiedad Thumbprint del certificado predeterminado. Use este valor para que el certificado predeterminado sea el certificado de autenticación de servidor a servidor:</span><span class="sxs-lookup"><span data-stu-id="6f143-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

<span data-ttu-id="6f143-p105">En el comando anterior, el certificado recuperado está configurado para funcionar con certificado de autenticación de servidor a servidor global. Esto significa que el certificado se replicará en todos los servidores front-end y que se usará en ellos. Recuerde que este comando solo debe ejecutarse una vez en los servidores front-end. Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end. Configure el certificado una vez y deje que el servidor de replicación de Lync Server se ocupe de copiarlo en cada uno de los servidores.</span><span class="sxs-lookup"><span data-stu-id="6f143-p105">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers. Again, this command should only be run one time, and only on one of your Front End Servers. Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server. Instead, configure the certificate once, then let Lync Server's replication server take care of copying that certificate to each server.</span></span>

<span data-ttu-id="6f143-118">El cmdlet Set-CsCertificate toma el certificado en cuestión y configura inmediatamente dicho certificado para que actúe como el certificado OAuthTokenIssuer actual.</span><span class="sxs-lookup"><span data-stu-id="6f143-118">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="6f143-119">(Lync Server 2013 conserva dos copias de un tipo de certificado: el certificado actual y el certificado anterior). Si necesita que el nuevo certificado empiece a funcionar inmediatamente como el certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="6f143-119">(Lync Server 2013 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="6f143-p107">También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado. "Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado. Por ejemplo, este comando recupera el certificado predeterminado y lo configura para que sea el certificado OAuthTokenIssuer actual a partir del 1 de julio de 2012:</span><span class="sxs-lookup"><span data-stu-id="6f143-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2012:</span></span>

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

<span data-ttu-id="6f143-123">El 1 de julio de 2012, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual, y el "antiguo" certificado OAuthTokenIssuer se configurará como el certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="6f143-123">On July 1, 2012 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>

<span data-ttu-id="6f143-p108">Si no quiere usar Windows PowerShell, puede usar la consola MMC de certificados para exportar un certificado del servidor front-end e importarlo a todos los servidores front-end. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.</span><span class="sxs-lookup"><span data-stu-id="6f143-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="6f143-126">En tal caso, el procedimiento debe hacerse en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6f143-126">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="6f143-127">Al exportar e importar certificados de esta manera, Lync Server 2013 no replicará ese certificado en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6f143-127">When exporting and importing certificates in this manner Lync Server 2013 will not replicate that certificate to each Front End Server.</span></span>



</div>

<span data-ttu-id="6f143-128">Una vez que el certificado se ha importado a todos los servidores front-end, dicho certificado se puede asignar mediante el Asistente para la implementación de Lync Server en lugar de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f143-128">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Lync Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="6f143-129">Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:</span><span class="sxs-lookup"><span data-stu-id="6f143-129">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>

1.  <span data-ttu-id="6f143-130">Haga clic en Inicio, en todos los programas, en **Microsoft Lync server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6f143-130">Click Start, click All Programs, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="6f143-131">En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6f143-131">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="6f143-132">En la página Microsoft Lync Server 2013, haga clic en el botón **Ejecutar** en el encabezado **paso 3: solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="6f143-132">On the Microsoft Lync Server 2013 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="6f143-133">Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6f143-133">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>

4.  <span data-ttu-id="6f143-134">En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6f143-134">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>

5.  <span data-ttu-id="6f143-135">En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f143-135">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>

6.  <span data-ttu-id="6f143-136">En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f143-136">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>

7.  <span data-ttu-id="6f143-137">En la página Resumen de asignación de certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f143-137">On the Certificate Assignment Summary page, click **Next**.</span></span>

8.  <span data-ttu-id="6f143-138">En la página Ejecución de comandos, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6f143-138">On the Executing Commands page, click **Finish**.</span></span>

9.  <span data-ttu-id="6f143-139">Cierre el Asistente para certificados y el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="6f143-139">Close the Certificate Wizard and the Deployment Wizard.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

