---
title: Dominios de confianza del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834120"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="e22d8-103">Dominios de confianza del Sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="e22d8-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="e22d8-104">Lea este tema para obtener información sobre cómo configurar dominios de confianza para Skype Room System y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="e22d8-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="e22d8-105">Dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="e22d8-105">Trusted domains</span></span>

<span data-ttu-id="e22d8-106">El cliente de Skype Empresarial muestra un cuadro de diálogo que permite a los usuarios aceptar el certificado de Skype Empresarial Server si el dominio SIP de la cuenta de usuario que inicia sesión es diferente del nombre que aparece en el asunto o el nombre alternativo del sujeto en el certificado.</span><span class="sxs-lookup"><span data-stu-id="e22d8-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="e22d8-107">Si el certificado configurado para Skype Empresarial Server en su organización no tiene el nombre de dominio SIP de la cuenta del Sistema de sala de Skype en el asunto o el nombre alternativo del sujeto, debe configurar los dominios que se presentan en el certificado en la clave del Registro de dominios de confianza en el equipo de consola del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="e22d8-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="e22d8-108">La Guía del administrador del sistema de sala de Skype proporcionada por el fabricante del Sistema de sala de Skype explica cómo y dónde agregar dominios de confianza en el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="e22d8-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="e22d8-109">Por ejemplo, supongamos que los certificados configurados en Skype Empresarial Server tienen el nombre alternativo asunto/asunto "CONTOSO. LOCAL" y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión del Sistema de sala de Skype es "confrm1@contoso.net".</span><span class="sxs-lookup"><span data-stu-id="e22d8-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="e22d8-110">Como contoso.net no está en el certificado, en el equipo del Sistema de sala de Skype, tendrá que configurar "contoso.local" como un dominio de confianza en el Registro, como se explica en la Guía del administrador del sistema de sala de Skype proporcionada por el fabricante del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="e22d8-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

