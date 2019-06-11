---
title: 'Lync Server 2013: configuración de la CA de empresa para la autenticación de tarjetas inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="17001-102">Configuración de CA de empresa para la autenticación de tarjetas inteligentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17001-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17001-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="17001-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="17001-104">En la sección siguiente se describe cómo configurar una entidad de certificación (CA) raíz de empresa para admitir la autenticación de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="17001-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="17001-105">Para obtener información sobre cómo instalar una entidad emisora de certificados raíz de empresa, vea instalar una [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)entidad de certificación raíz de empresa en.</span><span class="sxs-lookup"><span data-stu-id="17001-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="17001-106">Configurar una entidad emisora de certificados raíz de empresa para admitir la autenticación de tarjetas inteligentes</span><span class="sxs-lookup"><span data-stu-id="17001-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="17001-107">En los siguientes pasos, se describe cómo configurar una CA raíz empresarial para admitir la autenticación de tarjeta inteligente:</span><span class="sxs-lookup"><span data-stu-id="17001-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="17001-108">Inicie sesión en el equipo de la CA empresarial usando una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="17001-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="17001-109">Inicie el Administrador del sistema y compruebe que está instalado el rol Inscripción web de entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="17001-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="17001-110">En el menú **Herramientas administrativas**, abra la consola de administración de **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="17001-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="17001-111">En el panel de navegación, expanda **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="17001-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="17001-112">Haga clic con el botón derecho en **Plantillas de certificado**, elija **Nueva** y, luego, elija **Plantilla de certificado que se va a emitir**.</span><span class="sxs-lookup"><span data-stu-id="17001-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="17001-113">Elija **Enrollment Agent**, **Usuario de tarjeta inteligente** e **Inicio de sesión de Tarjeta inteligente**.</span><span class="sxs-lookup"><span data-stu-id="17001-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="17001-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17001-114">Click **OK**.</span></span>

8.  <span data-ttu-id="17001-115">Haga clic con el botón derecho en **Plantillas de certificado**.</span><span class="sxs-lookup"><span data-stu-id="17001-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="17001-116">Elija **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="17001-116">Select **Manage**.</span></span>

10. <span data-ttu-id="17001-117">Abra las propiedades de la plantilla Usuario de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="17001-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="17001-118">Haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="17001-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="17001-119">Cambie los permisos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="17001-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="17001-120">Agregue cuentas de usuario individuales de AD con los permisos Leer/Inscribir (permitir), o</span><span class="sxs-lookup"><span data-stu-id="17001-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="17001-121">Agregue un grupo de seguridad que contenga los usuarios de tarjeta inteligente con permisos Leer/Inscribir (permitir), o</span><span class="sxs-lookup"><span data-stu-id="17001-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="17001-122">Agregue el grupo Usuarios del dominio con los permisos Leer/Inscribir (permitir)</span><span class="sxs-lookup"><span data-stu-id="17001-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

