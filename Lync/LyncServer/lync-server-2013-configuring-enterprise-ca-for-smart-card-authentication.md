---
title: 'Lync Server 2013: configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 315d98e26b471e2d9dd84dcb70cd7302e924e9b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="aa084-102">Configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa084-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa084-103">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="aa084-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="aa084-104">En la siguiente sección se describe cómo configurar una entidad de certificación (CA) raíz de empresa para que admita la autenticación de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="aa084-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="aa084-105">Para obtener información sobre cómo instalar una entidad de certificación raíz de empresa, consulte install a Enterprise root [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364)Certification Authority en.</span><span class="sxs-lookup"><span data-stu-id="aa084-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="aa084-106">Configuración de una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="aa084-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="aa084-107">Los pasos siguientes describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:</span><span class="sxs-lookup"><span data-stu-id="aa084-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="aa084-108">Inicie sesión en el equipo de la entidad de certificación empresarial con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="aa084-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="aa084-109">Inicie el administrador del sistema y compruebe que está instalado el rol de inscripción Web de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="aa084-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="aa084-110">En el menú **herramientas administrativas** , abra la consola de administración de la **entidad de certificación** .</span><span class="sxs-lookup"><span data-stu-id="aa084-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="aa084-111">En el panel de navegación, expanda **entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="aa084-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="aa084-112">Haga clic con el botón secundario en **plantillas de certificado**, seleccione **nuevo**y, a continuación, seleccione **plantilla de certificado para emitir**.</span><span class="sxs-lookup"><span data-stu-id="aa084-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="aa084-113">Seleccione **agente de inscripción**, **usuario de tarjeta inteligente**e **Inicio de sesión de tarjeta inteligente**.</span><span class="sxs-lookup"><span data-stu-id="aa084-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="aa084-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa084-114">Click **OK**.</span></span>

8.  <span data-ttu-id="aa084-115">Haga clic con el botón secundario en **plantillas de certificado**.</span><span class="sxs-lookup"><span data-stu-id="aa084-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="aa084-116">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="aa084-116">Select **Manage**.</span></span>

10. <span data-ttu-id="aa084-117">Abra las propiedades de la plantilla usuario de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="aa084-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="aa084-118">Haga clic en la pestaña **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="aa084-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="aa084-119">Cambie los permisos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="aa084-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="aa084-120">Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir), o</span><span class="sxs-lookup"><span data-stu-id="aa084-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="aa084-121">Agregue un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir), o</span><span class="sxs-lookup"><span data-stu-id="aa084-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="aa084-122">Adición del grupo de usuarios de dominio con permisos de lectura e inscripción (permitir)</span><span class="sxs-lookup"><span data-stu-id="aa084-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

