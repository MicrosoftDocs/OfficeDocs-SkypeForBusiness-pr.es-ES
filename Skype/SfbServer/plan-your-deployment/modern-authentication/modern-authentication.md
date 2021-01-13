---
title: Planear la autenticación moderna en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Temas de planeación de autenticación y autorización para Skype Empresarial Server, incluida la integración con otros productos
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816250"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="e207d-103">Discusión de autenticación y autorización en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e207d-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="e207d-104">La autenticación y la autorización son conceptos relacionados, pero hacen diferentes tareas (aunque ambas son necesarias).</span><span class="sxs-lookup"><span data-stu-id="e207d-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="e207d-105">En términos sencillos, la autenticación (AuthN) depende de secretos que solo un usuario válido conoce o tiene, y que pueden ser una contraseña, código, huella digital, certificado, una combinación de notificaciones sobre el usuario que son verdaderas o una combinación de estas cosas que se usan juntas.</span><span class="sxs-lookup"><span data-stu-id="e207d-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="e207d-106">AuthN es un proceso para demostrar que eres quien dice ser.</span><span class="sxs-lookup"><span data-stu-id="e207d-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="e207d-107">La autorización (AuthZ) se preocupa por lo que tiene acceso después de haber probado quién es.</span><span class="sxs-lookup"><span data-stu-id="e207d-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="e207d-108">Determina lo que se le ha permitido ver, editar y obtener acceso de otro modo.</span><span class="sxs-lookup"><span data-stu-id="e207d-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="e207d-109">Por ejemplo, puede que tenga acceso de administrador de colección de sitios eficaz a SharePoint Online, pero si cambia a otra carga de trabajo en línea, como Skype Empresarial Online, puede que tenga privilegios para solucionar problemas de usuario, no para cambiar la configuración del servidor o los servidores.</span><span class="sxs-lookup"><span data-stu-id="e207d-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="e207d-110">En una tercera carga de trabajo, como Exchange Online, es posible que solo tenga el acceso promedio del usuario.</span><span class="sxs-lookup"><span data-stu-id="e207d-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="e207d-111">AuthZ comprueba qué y cuánto acceso tiene a servicios/cargas de carga, aplicaciones, archivos y otros datos.</span><span class="sxs-lookup"><span data-stu-id="e207d-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="e207d-112">Nuestros ejemplos implican propiedades en línea como SharePoint y Exchange Online, pero los procesos de AuthN y AuthZ funcionan localmente y en un entorno híbrido de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="e207d-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="e207d-113">En última instancia, las herramientas como AAD Connect y ADFS se involucran en la historia de AuthN y AuthZ mediante la sincronización de cuentas y contraseñas locales en ad de la nube (que es Azure AD) o la intrusión en el flujo de AuthZ para que a un usuario no se le pidan con frecuencia sus credenciales, por ejemplo, al cambiar entre cargas de trabajo en la nube, crear escenarios de Sign-On único.</span><span class="sxs-lookup"><span data-stu-id="e207d-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="e207d-114">Pero no son, por sí mismos, AuthN o AuthZ responsables, solo forman parte de la mecánica.</span><span class="sxs-lookup"><span data-stu-id="e207d-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="e207d-115">Hoy en día, muchas tecnologías consideran que estos procesos (AuthN y AuthZ) son un mecanismo y oirá muchas referencias al proceso de autenticación que también incluyen autorización en ellos.</span><span class="sxs-lookup"><span data-stu-id="e207d-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="e207d-116">Es importante recordar que el primer paso en el acceso de usuario es AuthN, lo que demuestra que es quien dice ser y que AuthZ usa el conocimiento de quién es el usuario para determinar a qué tiene acceso (como verá con Open Authorization u OAuth).</span><span class="sxs-lookup"><span data-stu-id="e207d-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="e207d-117">Temas de planeación de autenticación y autorización</span><span class="sxs-lookup"><span data-stu-id="e207d-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="e207d-118">Cómo usar la autenticación moderna (ADAL) con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e207d-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="e207d-119">Topologías de Skype Empresarial compatibles con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="e207d-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="e207d-120">Planee desactivar los métodos de autenticación heredados interna y externamente en la red.</span><span class="sxs-lookup"><span data-stu-id="e207d-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

