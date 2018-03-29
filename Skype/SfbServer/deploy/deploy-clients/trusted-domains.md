---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="58c20-103">Dominios de confianza del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="58c20-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="58c20-104">Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="58c20-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="58c20-105">Dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="58c20-105">Trusted domains</span></span>

<span data-ttu-id="58c20-106">El Skype para empresa cliente muestra un cuadro de diálogo que permite a los usuarios que acepte el certificado desde el Skype para Business Server si el dominio SIP de iniciar sesión en la cuenta de usuario es diferente del nombre que se presenta en el asunto o el nombre de Alt de asunto en el certificado.</span><span class="sxs-lookup"><span data-stu-id="58c20-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="58c20-107">Si el certificado configurado para Skype para Business Server de su organización no tiene nombre de dominio SIP de la cuenta de sistema del sitio de Skype en el asunto o el nombre de asunto Alt, debe configurar esos dominios presentados en el certificado en los dominios de confianza clave del registro en el equipo de la consola de sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="58c20-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="58c20-108">Guía de sistema de sala de Skype suministrados por el fabricante Skype sala del administrador del sistema se explica dónde y cómo agregar dominios de confianza en el Skype para cliente de empresa.</span><span class="sxs-lookup"><span data-stu-id="58c20-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="58c20-109">Por ejemplo, supongamos que los certificados configurados en Skype para Business Server tienen un nombre de sujeto o Alt de "CONTOSO. "LOCAL" y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión de sistema de sala de Skype es "confrm1@contoso.net".</span><span class="sxs-lookup"><span data-stu-id="58c20-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="58c20-110">Porque contoso.net no aparece en el certificado en el equipo de sistema del sitio de Skype, debe configurar "contoso.local" como un dominio de confianza en el registro, como se explica en la Guía de sistema de sala de Skype suministrados por el fabricante Skype sala del administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="58c20-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

