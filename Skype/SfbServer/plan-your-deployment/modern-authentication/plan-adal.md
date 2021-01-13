---
title: Planificación de la autenticación moderna (ADAL) con Skype Empresarial
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
description: En este artículo se explica qué es la autenticación moderna (que se basa en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0).
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816230"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="48adb-103">Cómo usar la autenticación moderna (ADAL) con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="48adb-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="48adb-104">En este artículo se presenta la autenticación moderna (que se basa en la Biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que se puede encontrar en la actualización acumulativa de marzo de 2016 para Skype Empresarial para Skype Empresarial Server 2015, o desde la versión inicial de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48adb-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="48adb-105">¿Qué es ADAL?</span><span class="sxs-lookup"><span data-stu-id="48adb-105">What is ADAL?</span></span>

<span data-ttu-id="48adb-106">ADAL es el acrónimo de la "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es una base de la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="48adb-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="48adb-107">Esta biblioteca de código está diseñada para que los recursos protegidos del directorio estén disponibles para las aplicaciones cliente (como Skype Empresarial) a través de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="48adb-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="48adb-108">ADAL funciona con OAuth 2.0 para habilitar más escenarios de autenticación y autorización, como la autenticación multifactor (MFA) y más formas de autenticación SAML.</span><span class="sxs-lookup"><span data-stu-id="48adb-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="48adb-109">Una variedad de aplicaciones que actúan como clientes pueden aprovechar la autenticación moderna para obtener ayuda para obtener recursos protegidos.</span><span class="sxs-lookup"><span data-stu-id="48adb-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="48adb-110">En Skype Empresarial Server, esta tecnología se usa entre los clientes locales y los servidores locales para proporcionar a los usuarios un nivel adecuado de autorización para los recursos.</span><span class="sxs-lookup"><span data-stu-id="48adb-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="48adb-111">Las conversaciones de autenticación moderna (basadas en ADAL y OAuth 2.0) tienen algunos elementos en común.</span><span class="sxs-lookup"><span data-stu-id="48adb-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="48adb-112">Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente es Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="48adb-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="48adb-113">Hay un recurso al que el cliente necesita un nivel específico de acceso y este recurso está protegido por un servicio de directorio, en este caso el recurso es Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="48adb-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="48adb-114">Hay una conexión OAuth, es decir, una conexión dedicada a autorizar  *a*  un usuario a tener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="48adb-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="48adb-115">(OAuth también se conoce por el nombre más descriptivo, autenticación de servidor a servidor, y a menudo se abrevia como S2S).</span><span class="sxs-lookup"><span data-stu-id="48adb-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="48adb-116">En las conversaciones de autenticación moderna (ADAL) de Skype Empresarial Server, Skype Empresarial Server se comunica a través de ADFS (ADFS 3.0 en Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="48adb-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="48adb-117">La autenticación puede producirse con otro proveedor de identidades (IdP), pero Skype Empresarial Server debe configurarse para comunicarse directamente con ADFS.</span><span class="sxs-lookup"><span data-stu-id="48adb-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="48adb-118">Si no ha configurado ADFS para trabajar con Skype Empresarial Server, complete la instalación [de ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48adb-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="48adb-119">ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype Empresarial Server 2015, y la actualización acumulativa de marzo de 2016 para Skype Empresarial debe estar instalada y es necesaria para una configuración correcta. </span><span class="sxs-lookup"><span data-stu-id="48adb-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="48adb-120">Para Skype Empresarial Server 2019, está disponible desde la versión inicial del producto.</span><span class="sxs-lookup"><span data-stu-id="48adb-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48adb-121">Durante la versión inicial, la autenticación moderna en un entorno local solo se admite si no hay ninguna topología mixta de Skype implicada.</span><span class="sxs-lookup"><span data-stu-id="48adb-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="48adb-122">Por ejemplo, si el entorno es simplemente Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="48adb-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="48adb-123">Esta instrucción puede estar sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="48adb-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="48adb-124">Se debe descargar un paquete de PowerShell que incluya archivos .ps1 con los comandos usados por ADAL para una configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="48adb-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="48adb-125">Para obtener información sobre cómo implementar la autenticación moderna en Skype Empresarial, consulte: Cómo usar la autenticación moderna [(ADAL) con Skype Empresarial](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="48adb-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
