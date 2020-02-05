---
title: Dominios de confianza del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768673"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="37c19-103">Dominios de confianza del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="37c19-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="37c19-104">Lea este tema para obtener información sobre cómo configurar los dominios de confianza de Sistema de salas de Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="37c19-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="37c19-105">Dominios de confianza</span><span class="sxs-lookup"><span data-stu-id="37c19-105">Trusted domains</span></span>

<span data-ttu-id="37c19-106">El cliente de Skype empresarial muestra un cuadro de diálogo que permite a los usuarios aceptar el certificado de Skype empresarial Server si el dominio SIP de la cuenta de usuario que inicia sesión es diferente del nombre presentado en el asunto o nombre alternativo del asunto en el certificado.</span><span class="sxs-lookup"><span data-stu-id="37c19-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="37c19-107">Si el certificado configurado para Skype empresarial Server en su organización no tiene el nombre de dominio SIP de la cuenta del sistema de salas de Skype en el nombre alternativo asunto o asunto, debe configurar los dominios presentados en el certificado en los dominios de confianza. clave del registro en la máquina de consola del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="37c19-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="37c19-108">La guía del administrador de sistemas de salas de Skype proporcionada por el fabricante de su sistema de salas de Skype explica cómo y dónde agregar dominios de confianza en el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="37c19-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="37c19-109">Por ejemplo, supongamos que los certificados configurados en Skype empresarial Server tienen un nombre alternativo de asunto y asunto de "CONTOSO. LOCAL "y uno de los dominios SIP asignados a un usuario para la dirección de inicio de sesión del sistema de salas de Skype es" confrm1@contoso.net ".</span><span class="sxs-lookup"><span data-stu-id="37c19-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="37c19-110">Debido a que contoso.net no está en el certificado, en el equipo del sistema de la sala de Skype, necesitará configurar "contoso. local" como dominio de confianza en el registro, como se explica en la guía del administrador de sistemas de Skype Room.</span><span class="sxs-lookup"><span data-stu-id="37c19-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

