---
title: 'Lync Server 2013: configuración de los servicios de Federación de Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26f7ec2be8390ee913c810928cc99c4e20d53c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517657"
---
# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="b0e39-102">Configuración de los servicios de Federación de Active Directory (AD FS 2,0) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0e39-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0e39-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="b0e39-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="b0e39-104">En la siguiente sección se describe cómo configurar los servicios de Federación de Active Directory (AD FS 2,0) para que admitan la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="b0e39-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="b0e39-105">Para obtener información sobre cómo instalar AD FS 2,0, consulte las guías paso a paso y de procedimientos de AD FS 2,0 en [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374) .</span><span class="sxs-lookup"><span data-stu-id="b0e39-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b0e39-106">Al instalar AD FS 2,0, no use el administrador de servidores de Windows para agregar el rol de los servicios de Federación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0e39-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="b0e39-107">En su lugar, descargue e instale el paquete 2,0 RTW de los servicios de Federación de Active Directory en <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A> .</span><span class="sxs-lookup"><span data-stu-id="b0e39-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="b0e39-108">**Para configurar AD FS para la autenticación en dos fases**</span><span class="sxs-lookup"><span data-stu-id="b0e39-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="b0e39-109">Inicie sesión en el equipo con AD FS 2,0 con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="b0e39-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="b0e39-110">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0e39-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="b0e39-111">Desde la línea de comandos de Windows PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0e39-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="b0e39-112">Establezca una asociación con cada Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Director de julio de 2013, grupo de servidores Enterprise y servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución del siguiente comando, que reemplaza el nombre del servidor específico de la implementación:</span><span class="sxs-lookup"><span data-stu-id="b0e39-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="b0e39-113">En el menú Herramientas administrativas, inicie la consola de administración de AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="b0e39-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="b0e39-114">Expanda **relaciones de confianza relaciones** de \> **confianza para usuario autenticado**.</span><span class="sxs-lookup"><span data-stu-id="b0e39-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="b0e39-115">Compruebe que se haya creado una nueva confianza para Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: Grupo de servidores Enterprise o servidor Standard Edition de julio de 2013.</span><span class="sxs-lookup"><span data-stu-id="b0e39-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="b0e39-116">Cree y asigne una regla de autorización de emisión para la relación de confianza para usuario autenticado con Windows PowerShell; para ello, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b0e39-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="b0e39-117">Cree y asigne una regla de transformación de emisión para la relación de confianza para usuario autenticado con Windows PowerShell; para ello, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b0e39-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="b0e39-118">Desde la consola de Administración AD FS 2,0, haga clic con el botón secundario en su relación de confianza para usuario autenticado y seleccione **editar reglas de notificación**.</span><span class="sxs-lookup"><span data-stu-id="b0e39-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="b0e39-119">Seleccione la pestaña **reglas de autorización de emisión** y compruebe que la nueva regla de autorización se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0e39-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="b0e39-120">Seleccione la ficha **reglas de transformación de emisión** y compruebe que la nueva regla de transformación se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0e39-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

