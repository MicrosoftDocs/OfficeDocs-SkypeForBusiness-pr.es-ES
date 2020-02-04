---
title: 'Lync Server 2013: configuración de AD FS 2,0 para admitir la autenticación de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="f2f93-102">Configuración de AD FS 2,0 para admitir la autenticación de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2f93-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2f93-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="f2f93-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="f2f93-104">Hay dos tipos de autenticación posibles que se pueden configurar para permitir que AD FS 2.0 admita autenticación con tarjetas inteligentes:</span><span class="sxs-lookup"><span data-stu-id="f2f93-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="f2f93-105">Autenticación basada en formularios (FBA)</span><span class="sxs-lookup"><span data-stu-id="f2f93-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="f2f93-106">Autenticación de cliente de seguridad de capa de transporte</span><span class="sxs-lookup"><span data-stu-id="f2f93-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="f2f93-107">Al usar la autenticación basada en formularios, puede desarrollar una página web que permita a los usuarios autenticarse ya sea por medio de su nombre de usuario/contraseña o por medio de su tarjeta inteligente y PIN.</span><span class="sxs-lookup"><span data-stu-id="f2f93-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="f2f93-108">Este tema se enfoca en cómo implementar la autenticación de cliente de seguridad de capa de transporte con AD FS 2.0.</span><span class="sxs-lookup"><span data-stu-id="f2f93-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="f2f93-109">Para obtener más información sobre los tipos de autenticación 2,0 de AD FS, consulte AD FS 2,0: Cómo cambiar el tipo [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)de autenticación local en.</span><span class="sxs-lookup"><span data-stu-id="f2f93-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="f2f93-110">**Para configurar AD FS 2.0 para admitir la autenticación de cliente**</span><span class="sxs-lookup"><span data-stu-id="f2f93-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="f2f93-111">Inicie sesión en el equipo con AD FS 2.0 por medio de una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="f2f93-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="f2f93-112">Inicie Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="f2f93-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="f2f93-113">Ir a C:\\Inetpub\\ADFS\\LS</span><span class="sxs-lookup"><span data-stu-id="f2f93-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="f2f93-114">Haga una copia de seguridad del archivo web.config existente.</span><span class="sxs-lookup"><span data-stu-id="f2f93-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="f2f93-115">Abra el archivo web.config existente con el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="f2f93-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="f2f93-116">Desde la barra de menús, seleccione **Editar** y, luego, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f2f93-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="f2f93-117">Busque \*\* \<localAuthenticationTypes\>\*\*.</span><span class="sxs-lookup"><span data-stu-id="f2f93-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="f2f93-118">Tenga en cuenta que hay cuatro tipos de autenticación enumerados, uno por línea.</span><span class="sxs-lookup"><span data-stu-id="f2f93-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="f2f93-119">Mueva la línea que contiene el tipo de autenticación TLSClient hacia la parte superior de la lista en la sección.</span><span class="sxs-lookup"><span data-stu-id="f2f93-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="f2f93-120">Guarde y cierre el archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="f2f93-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="f2f93-121">Inicie un símbolo del sistema con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="f2f93-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="f2f93-122">Reinicie IIS ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f2f93-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

