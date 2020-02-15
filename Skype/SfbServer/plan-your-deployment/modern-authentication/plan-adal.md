---
title: Planeación de la autenticación moderna (ADAL) con Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: En este artículo se explica qué es la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046293"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="0d301-103">Cómo usar la autenticación moderna (ADAL) con Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="0d301-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="0d301-104">En este artículo se presenta la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0) que puede encontrarse en la actualización acumulativa de marzo de 2016 para Skype empresarial para Skype empresarial Server 2015 o desde el inicial Release for Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0d301-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="0d301-105">¿Qué es ADAL?</span><span class="sxs-lookup"><span data-stu-id="0d301-105">What is ADAL?</span></span>

<span data-ttu-id="0d301-106">ADAL es el acrónimo de "biblioteca de autenticación de Active Directory" y, junto con OAuth 2,0, es un respaldo de la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="0d301-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="0d301-107">Esta biblioteca de código está diseñada para que los recursos protegidos en su directorio estén disponibles para las aplicaciones cliente (como Skype empresarial) mediante tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0d301-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="0d301-108">ADAL funciona con OAuth 2,0 para habilitar más escenarios de autenticación y autorización, como multi-factor Authentication (MFA) y más formas de autenticación SAML.</span><span class="sxs-lookup"><span data-stu-id="0d301-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="0d301-109">Una variedad de aplicaciones que actúan como clientes pueden aprovechar la autenticación moderna para ayudarle a obtener recursos protegidos.</span><span class="sxs-lookup"><span data-stu-id="0d301-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="0d301-110">En Skype empresarial Server, esta tecnología se usa entre los clientes locales y los servidores locales para proporcionar a los usuarios un nivel adecuado de autorización para los recursos.</span><span class="sxs-lookup"><span data-stu-id="0d301-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="0d301-111">Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2,0) tienen algunos elementos en común.</span><span class="sxs-lookup"><span data-stu-id="0d301-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="0d301-112">Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente es Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d301-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="0d301-113">Hay un recurso para el que el cliente necesita un nivel específico de acceso y este recurso está protegido por un servicio de directorio, en este caso el recurso es Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0d301-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="0d301-114">Hay una conexión de OAuth, es decir, una conexión dedicada a *autorizar* a un usuario para que tenga acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="0d301-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="0d301-115">(OAuth también se conoce por el nombre descriptivo, la autenticación de servidor a servidor y, a menudo, se suele abreviar como S2S).</span><span class="sxs-lookup"><span data-stu-id="0d301-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="0d301-116">En conversaciones de autenticación moderna (ADAL) de Skype empresarial Server, Skype empresarial Server se comunica a través de ADFS (ADFS 3,0 en Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="0d301-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="0d301-117">La autenticación puede producirse mediante otro proveedor de identidades (IdP), pero es necesario configurar Skype empresarial Server para comunicarse con ADFS directamente.</span><span class="sxs-lookup"><span data-stu-id="0d301-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="0d301-118">Si no ha configurado ADFS para que funcione con Skype empresarial Server, complete la [instalación de ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0d301-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="0d301-119">ADAL se incluye en la actualización acumulativa de marzo de 2016 para Skype empresarial Server 2015 y la actualización acumulativa de marzo de 2016 para Skype empresarial **debe** estar instalada y es necesaria para una configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="0d301-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="0d301-120">Para Skype empresarial Server 2019, está disponible en la versión inicial del producto.</span><span class="sxs-lookup"><span data-stu-id="0d301-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d301-121">Durante la versión inicial, la autenticación moderna en un entorno local solo se admite si no interviene una topología mixta de Skype.</span><span class="sxs-lookup"><span data-stu-id="0d301-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="0d301-122">Por ejemplo, si el entorno es puramente de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0d301-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="0d301-123">Esta instrucción puede estar sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="0d301-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="0d301-124">Debe descargarse un paquete de PowerShell que incluya archivos. PS1 con los comandos que usa ADAL para una configuración correcta.</span><span class="sxs-lookup"><span data-stu-id="0d301-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="0d301-125">Para obtener información sobre cómo implementar la autenticación moderna en Skype empresarial, consulte: [Cómo usar la autenticación moderna (Adal) con Skype empresarial](../../manage/authentication/use-adal.md) .</span><span class="sxs-lookup"><span data-stu-id="0d301-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
