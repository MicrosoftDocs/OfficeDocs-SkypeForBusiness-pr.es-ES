---
title: 'Lync Server 2013: configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes'
description: 'Lync Server 2013: configurar la CA de empresa para la autenticación de tarjetas inteligentes.'
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
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548446"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="5ba05-103">Configuración de la entidad de certificación empresarial para la autenticación de tarjetas inteligentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba05-103">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba05-104">_**Última modificación del tema:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="5ba05-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="5ba05-105">En la siguiente sección se describe cómo configurar una entidad de certificación (CA) raíz de empresa para que admita la autenticación de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="5ba05-105">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="5ba05-106">Para obtener información sobre cómo instalar una entidad de certificación raíz de empresa, consulte install a Enterprise root Certification Authority en [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="5ba05-106">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="5ba05-107">Configuración de una entidad de certificación raíz empresarial para admitir la autenticación de tarjeta inteligente</span><span class="sxs-lookup"><span data-stu-id="5ba05-107">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="5ba05-108">Los pasos siguientes describen cómo configurar una CA raíz de empresa para admitir la autenticación de tarjeta inteligente:</span><span class="sxs-lookup"><span data-stu-id="5ba05-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="5ba05-109">Inicie sesión en el equipo de la entidad de certificación empresarial con una cuenta de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="5ba05-109">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="5ba05-110">Inicie el administrador del sistema y compruebe que está instalado el rol de inscripción Web de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="5ba05-110">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="5ba05-111">En el menú **herramientas administrativas** , abra la consola de administración de la **entidad de certificación** .</span><span class="sxs-lookup"><span data-stu-id="5ba05-111">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="5ba05-112">En el panel de navegación, expanda **entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-112">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="5ba05-113">Haga clic con el botón secundario en **plantillas de certificado**, seleccione **nuevo**y, a continuación, seleccione **plantilla de certificado para emitir**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-113">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="5ba05-114">Seleccione **agente de inscripción**, **usuario de tarjeta inteligente**e **Inicio de sesión de tarjeta inteligente**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-114">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="5ba05-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-115">Click **OK**.</span></span>

8.  <span data-ttu-id="5ba05-116">Haga clic con el botón secundario en **plantillas de certificado**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-116">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="5ba05-117">Seleccione **administrar**.</span><span class="sxs-lookup"><span data-stu-id="5ba05-117">Select **Manage**.</span></span>

10. <span data-ttu-id="5ba05-118">Abra las propiedades de la plantilla usuario de tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="5ba05-118">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="5ba05-119">Haga clic en la pestaña **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="5ba05-119">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="5ba05-120">Cambie los permisos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5ba05-120">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="5ba05-121">Agregar cuentas de AD de usuario individuales con permisos de lectura/inscripción (permitir), o</span><span class="sxs-lookup"><span data-stu-id="5ba05-121">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="5ba05-122">Agregue un grupo de seguridad que contenga usuarios de tarjetas inteligentes con permisos de lectura/inscripción (permitir), o</span><span class="sxs-lookup"><span data-stu-id="5ba05-122">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="5ba05-123">Adición del grupo de usuarios de dominio con permisos de lectura e inscripción (permitir)</span><span class="sxs-lookup"><span data-stu-id="5ba05-123">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

