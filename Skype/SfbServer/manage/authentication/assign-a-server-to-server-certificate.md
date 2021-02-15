---
title: Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumen: asigne un certificado de autenticación de servidor a servidor para Skype Empresarial Server.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828510"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="19f6a-103">Asignar un certificado de autenticación de servidor a servidor a Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="19f6a-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="19f6a-104">**Resumen:** Asignar un certificado de autenticación de servidor a servidor para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="19f6a-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="19f6a-105">Para determinar si ya se ha asignado un certificado de autenticación de servidor a servidor a Skype Empresarial Server, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="19f6a-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="19f6a-106">Si no recibe información del certificado, debe asignar un certificado del emisor de token para poder usar la autenticación de servidor a servidor.</span><span class="sxs-lookup"><span data-stu-id="19f6a-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="19f6a-107">Como regla general, cualquier certificado de Skype Empresarial Server puede usarse como certificado OAuthTokenIssuer; Por ejemplo, el certificado predeterminado de Skype Empresarial Server también puede usarse como certificado OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="19f6a-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="19f6a-108">(El certificado OAUthTokenIssuer también puede ser cualquier certificado de servidor web que incluya el nombre de su dominio SIP en el campo Asunto). Los dos requisitos principales para el certificado usado para la autenticación de servidor a servidor son los siguientes: 1) el mismo certificado debe configurarse como certificado OAuthTokenIssuer en todos los servidores front-end; y, 2) el certificado debe tener al menos 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="19f6a-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="19f6a-p102">Si no dispone de un certificado que pueda usarse para la autenticación de servidor a servidor, puede obtener uno nuevo, importarlo y usarlo para este tipo de autenticación. Una vez haya solicitado y obtenido el nuevo certificado, podrá iniciar sesión en cualquiera de los servidores front-end y usar un comando de Windows PowerShell similar a este para importar y asignar el certificado:</span><span class="sxs-lookup"><span data-stu-id="19f6a-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="19f6a-111">En el comando anterior, el parámetro Path representa la ruta de acceso completa al archivo de certificado, y el parámetro Password representa la contraseña que se asignó al certificado.</span><span class="sxs-lookup"><span data-stu-id="19f6a-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="19f6a-112">Este procedimiento debe ejecutarse solo una vez: el servicio de replicación de Skype Empresarial Server creará automáticamente un conjunto de tareas programadas que descifrarán e implementarán el certificado en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="19f6a-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="19f6a-p104">También puede usar un certificado actual como certificado de autenticación de servidor a servidor. Como se ha mencionado, el certificado predeterminado se puede usar como certificado de autenticación de servidor a servidor. Los dos comandos siguientes de Windows PowerShell recuperan el valor de la propiedad Thumbprint del certificado predeterminado. Use este valor para que el certificado predeterminado sea el certificado de autenticación de servidor a servidor:</span><span class="sxs-lookup"><span data-stu-id="19f6a-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="19f6a-115">En el comando anterior, el certificado recuperado está configurado para funcionar como el certificado de autenticación de servidor a servidor global; esto significa que el certificado se replicará en todos los servidores front-end y los usará.</span><span class="sxs-lookup"><span data-stu-id="19f6a-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="19f6a-116">De nuevo, este comando solo debe ejecutarse una vez y solo en uno de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="19f6a-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="19f6a-117">Aunque todos los servidores front-end deben usar el mismo certificado, no debe configurar el certificado OAuthTokenIssuer en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="19f6a-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="19f6a-118">En su lugar, configure el certificado una vez y, a continuación, deje que el servidor de replicación de Skype Empresarial Server se haga cargo de copiar ese certificado en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="19f6a-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="19f6a-119">El Set-CsCertificate toma el certificado en cuestión e inmediatamente configura dicho certificado para que actúe como el certificado OAuthTokenIssuer actual.</span><span class="sxs-lookup"><span data-stu-id="19f6a-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="19f6a-120">(Skype Empresarial Server mantiene dos copias de un tipo de certificado: el certificado actual y el certificado anterior). Si necesita que el nuevo certificado empiece a actuar inmediatamente como certificado OAuthTokenIssuer, debe usar el cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="19f6a-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="19f6a-121">También puede usar el cmdlet Set-CsCertificate para la "sucesión" de un nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="19f6a-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="19f6a-122">"Sucesión" significa simplemente que se configura un nuevo certificado para que pase a ser el certificado OAuthTokenIssuer actual en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="19f6a-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="19f6a-123">Por ejemplo, este comando recupera el certificado predeterminado y, a continuación, configura dicho certificado para que se haga cargo del certificado OAuthTokenIssuer actual a partir del 1 de julio de 2015:</span><span class="sxs-lookup"><span data-stu-id="19f6a-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="19f6a-124">El 1 de julio de 2015, el nuevo certificado se configurará como el certificado OAuthTokenIssuer actual y el certificado OAuthTokenIssuer "antiguo" se configurará como el certificado anterior.</span><span class="sxs-lookup"><span data-stu-id="19f6a-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="19f6a-p108">Si no quiere usar Windows PowerShell, puede usar la consola MMC de certificados para exportar un certificado del servidor front-end e importarlo a todos los servidores front-end. Si lo hace así, no olvide exportar la clave privada junto con el propio certificado.</span><span class="sxs-lookup"><span data-stu-id="19f6a-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="19f6a-127">En tal caso, el procedimiento debe hacerse en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="19f6a-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="19f6a-128">Al exportar e importar certificados de esta manera, Skype Empresarial Server no replicará ese certificado en cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="19f6a-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="19f6a-129">Después de importar el certificado a todos los servidores front-end, dicho certificado se puede asignar mediante el Asistente para la implementación de Skype Empresarial Server en lugar de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19f6a-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="19f6a-130">Para asignar un certificado con el Asistente para la implementación, siga estos pasos en un equipo donde este asistente esté instalado:</span><span class="sxs-lookup"><span data-stu-id="19f6a-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="19f6a-131">Haga clic en Inicio, en Todos los programas, **en Skype** Empresarial Server y, a continuación, en Asistente para la implementación de Skype **Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="19f6a-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="19f6a-132">En el Asistente para la implementación, haga **clic en Instalar o actualizar el sistema de Skype Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="19f6a-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="19f6a-133">En la página de Skype  Empresarial Server, haga clic en el botón Ejecutar bajo el encabezado **Paso 3: Solicitar,** instalar o asignar certificados.</span><span class="sxs-lookup"><span data-stu-id="19f6a-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="19f6a-134">Nota: si ya ha instalado certificados en este equipo, en lugar del botón **Ejecutar**, aparecerá **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="19f6a-135">En el Asistente para certificados, seleccione el certificado **OAuthTokenIssuer** y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="19f6a-136">En la página **Asignación de certificado** del Asistente para certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="19f6a-137">En la página **Almacén de certificados**, seleccione el certificado que desea usar para la autenticación de servidor a servidor y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="19f6a-138">En la página Resumen de asignación de certificados, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="19f6a-139">En la página Ejecución de comandos, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="19f6a-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="19f6a-140">Cierre el Asistente para certificados y el Asistente para la implementación.</span><span class="sxs-lookup"><span data-stu-id="19f6a-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

