---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: ff8f75178fef21900292760fb71f53ea3746380c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895050"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="64814-103">Dominios de confianza del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="64814-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="64814-104">Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="64814-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="64814-105">Dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="64814-105">Trusted domains</span></span>

<span data-ttu-id="64814-106">El Skype para cliente empresarial muestra un cuadro de diálogo que permite a los usuarios que acepte el certificado desde el Skype para Business Server si el dominio SIP de la cuenta de usuario de inicio de sesión es diferente del nombre que se presentan en el asunto o el nombre alternativo de sujeto en el certificado.</span><span class="sxs-lookup"><span data-stu-id="64814-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="64814-107">Si el certificado configurado para Skype para Business Server en la organización no tiene el nombre de dominio SIP de la cuenta del sistema de salas de Skype en el asunto o el nombre alternativo de sujeto, debe configurar los dominios que aparecen en el certificado en los dominios de confianza clave del registro en el equipo de la consola del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="64814-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="64814-108">Sistema de sala de Skype suministrados por el fabricante Skype salón del administrador del sistema esta guía se explica cómo y dónde para agregar dominios de confianza en el Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="64814-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="64814-109">Por ejemplo, supongamos que los certificados configurados en Skype para Business Server tienen un nombre de sujeto o sujeto alternativo de "CONTOSO. "LOCAL" y uno de los dominios SIP que se asigna a un usuario de la dirección de inicio de sesión del sistema de salas de Skype es "confrm1@contoso.net".</span><span class="sxs-lookup"><span data-stu-id="64814-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="64814-110">Debido a que contoso.net es no en el certificado, en el equipo del sistema de salas de Skype, debe configurar "contoso.local" como un dominio de confianza en el registro, como se explica en la Guía de Skype salón suministrados por el fabricante Skype salón del sistema del administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="64814-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

