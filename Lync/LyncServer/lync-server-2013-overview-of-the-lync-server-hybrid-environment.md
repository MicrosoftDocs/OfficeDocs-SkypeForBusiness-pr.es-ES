---
title: 'Lync Server 2013: información general sobre el entorno híbrido de Lync Server'
description: 'Lync Server 2013: información general sobre el entorno híbrido de Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95b0ae433dafad349d7ef9b6328e43dbc308579c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552396"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="ec2b6-103">Información general sobre el entorno híbrido de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec2b6-103">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec2b6-104">_**Última modificación del tema:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="ec2b6-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="ec2b6-105">El entorno híbrido de Lync Server 2013 hace referencia a una implementación en la que hay algunos usuarios hospedados en Lync Server 2013 local y otros usuarios hospedados en Lync Online, pero los usuarios comparten el mismo dominio, como user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-105">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="ec2b6-106">Acerca de esta guía</span><span class="sxs-lookup"><span data-stu-id="ec2b6-106">About this Guide</span></span>

<span data-ttu-id="ec2b6-107">En esta guía se describen las tareas necesarias para configurar el entorno de Lync Server 2013 para la interoperabilidad con Lync Online y, a continuación, mover a los usuarios de la implementación local para usar Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-107">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="ec2b6-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec2b6-108">Prerequisites</span></span>

<span data-ttu-id="ec2b6-109">Tendrá que tener instaladas las siguientes aplicaciones y utilidades para completar las tareas de configuración de una implementación de híbrido.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-109">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="ec2b6-110">Los programas de instalación para estos archivos se incluyen en los medios de instalación proporcionados para su implementación, así como en los vínculos incluidos en la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-110">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="ec2b6-111">Servicios de federación de Active Directory (ADFS) 2.0</span><span class="sxs-lookup"><span data-stu-id="ec2b6-111">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="ec2b6-112">Herramienta de sincronización de directorios de Microsoft 9,1</span><span class="sxs-lookup"><span data-stu-id="ec2b6-112">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="ec2b6-113">Instalar Windows PowerShell para el inicio de sesión único con AD FS</span><span class="sxs-lookup"><span data-stu-id="ec2b6-113">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="ec2b6-114">El Asistente para el inicio de sesión de Microsoft Online Services (msoidcli-7.0.msi) se incluye con la configuración de escritorio de Microsoft 365, que se puede obtener en la página de descargas a la que se vincula desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-114">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="ec2b6-115">Credenciales de administrador</span><span class="sxs-lookup"><span data-stu-id="ec2b6-115">Administrator Credentials</span></span>

<span data-ttu-id="ec2b6-116">Cuando se le pida que proporcione sus credenciales de administrador, use el nombre de usuario y la contraseña de la cuenta de administrador de la organización de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-116">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ec2b6-117">También usará estas credenciales para configurar los servicios de Federación de Active Directory (AD FS) 2,0, la sincronización de directorios, el inicio de sesión único, la Federación y el traslado de usuarios a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-117">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="ec2b6-118">Conectarse a Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec2b6-118">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="ec2b6-119">Los administradores ahora pueden usar Windows PowerShell para administrar Lync Online y sus cuentas de usuario de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ec2b6-119">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="ec2b6-120">Para ello, primero debe descargar e instalar el módulo Lync Online Connector desde el centro de descarga de Microsoft ( https://go.microsoft.com/fwlink/?LinkId=294688) .</span><span class="sxs-lookup"><span data-stu-id="ec2b6-120">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="ec2b6-121">Para obtener más información sobre cómo descargar, instalar y usar el módulo Lync Online Connector y para obtener información detallada sobre cómo usar Windows PowerShell para administrar Lync Online, consulte [using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec2b6-121">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

