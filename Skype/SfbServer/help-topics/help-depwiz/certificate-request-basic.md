---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: La página Nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud de bits del par de claves pública y privada, y una casilla que permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: f0d0339a483056276d400654f897b898b002cf03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805350"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="8be10-103">Solicitud de certificado (básica)</span><span class="sxs-lookup"><span data-stu-id="8be10-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="8be10-104">La  página Nombre y configuración de seguridad proporciona un cuadro de texto  para definir un nombre **descriptivo,** una lista desplegable para la longitud de bits del par de claves pública y privada, y una casilla que permite marcar la clave privada del certificado como **exportable.**</span><span class="sxs-lookup"><span data-stu-id="8be10-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="8be10-105">El nombre descriptivo o simple de un certificado es un nombre fácilmente reconocible que facilita a la persona que ve el certificado identificarlo.</span><span class="sxs-lookup"><span data-stu-id="8be10-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="8be10-106">La longitud de bits del par de claves pública y privada se puede seleccionar como 1024, 2048 o 4096.</span><span class="sxs-lookup"><span data-stu-id="8be10-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="8be10-107">Si se selecciona la casilla para marcar la clave privada del certificado como **exportable,** el certificado y la clave privada se pueden exportar y mover a otro equipo o servidor.</span><span class="sxs-lookup"><span data-stu-id="8be10-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="8be10-108">La única vez que esto es necesario es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación de retransmisión multimedia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="8be10-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8be10-109">Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la opción Marcar la clave privada del certificado como exportable solo si es absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="8be10-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

