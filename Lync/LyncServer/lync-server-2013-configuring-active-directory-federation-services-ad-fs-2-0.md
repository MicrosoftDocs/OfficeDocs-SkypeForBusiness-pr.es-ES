---
title: 'Lync Server 2013: configuración de servicios de Federación de Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="9b106-102">Configuración de servicios de Federación de Active Directory (AD FS 2,0) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b106-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b106-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="9b106-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="9b106-104">En la siguiente sección se describe cómo configurar los servicios de federación de Active Directory (AD FS 2.0) para admitir autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="9b106-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="9b106-105">Para obtener más información sobre cómo instalar 2,0 de AD FS, consulte instrucciones paso a paso de AD FS 2,0 y guías de [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)procedimientos en.</span><span class="sxs-lookup"><span data-stu-id="9b106-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9b106-106">Al instalar AD FS 2.0, no use Windows Server Manager para agregar el rol de los servicios de federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9b106-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="9b106-107">En su lugar, descargue e instale el paquete de servicios de Federación de Active <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Directory 2,0 RTW en.</span><span class="sxs-lookup"><span data-stu-id="9b106-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="9b106-108">**Para configurar AD FS para la autenticación en dos fases**</span><span class="sxs-lookup"><span data-stu-id="9b106-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="9b106-109">Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="9b106-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="9b106-110">Inicie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b106-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="9b106-111">Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9b106-111">From the Windows PowerShell command-line, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  <span data-ttu-id="9b106-112">Establezca una asociación con cada servidor de Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Director de 2013 julio de 2017, grupo empresarial y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando, sustituyendo el nombre del servidor específico de su implementación:</span><span class="sxs-lookup"><span data-stu-id="9b106-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="9b106-113">Desde el menú Herramientas administrativas, inicie la consola de administración de AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b106-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="9b106-114">Expanda **relaciones** \> \*\*\*\* de confianza confianzas de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="9b106-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="9b106-115">Compruebe que se ha creado una nueva confianza para su Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013: Grupo de servidores Enterprise o servidor Standard Edition de julio de 2013.</span><span class="sxs-lookup"><span data-stu-id="9b106-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="9b106-116">Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="9b106-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="9b106-117">Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado por medio de Windows PowerShell ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="9b106-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="9b106-118">Desde la consola de administración de AD FS 2.0, haga clic con el botón secundario en la relación de confianza para el usuario autenticado y seleccione **Editar reglas de notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="9b106-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="9b106-119">Seleccione la pestaña **Reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b106-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="9b106-120">Seleccione la pestaña **Reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b106-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

