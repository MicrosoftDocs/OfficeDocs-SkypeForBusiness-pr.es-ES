---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La página nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud en bits del par de claves público y privado y una casilla de verificación que le permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: abc022cd9126b90fb83244657dfb32ac214a62c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216399"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="3c247-103">Solicitud de certificado (básica)</span><span class="sxs-lookup"><span data-stu-id="3c247-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="3c247-104">La página **nombre y configuración de seguridad** proporciona un cuadro de texto para definir un **Nombre descriptivo**, una lista desplegable para la **longitud en bits** del par de claves público y privado y una casilla de verificación que permite a la clave privada **marca el certificado como exportable**.</span><span class="sxs-lookup"><span data-stu-id="3c247-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="3c247-105">El nombre descriptivo, o sencillo, de un certificado es un nombre fácilmente reconocible que permite que la persona que lo ve lo identifique más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="3c247-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="3c247-106">La longitud de bits del par de claves pública y privada se puede seleccionar entre 1024, 2048 o 4096.</span><span class="sxs-lookup"><span data-stu-id="3c247-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="3c247-107">Seleccionar la casilla de verificación para **marcar la clave privada del certificado como exportable** permite que el certificado y la clave privada se exportan y se muevan a otro servidor o equipo.</span><span class="sxs-lookup"><span data-stu-id="3c247-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="3c247-108">La única vez que se necesita activar es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación relé multimedia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="3c247-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3c247-109">Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la marca de la clave privada del certificado como exportable opción sólo si es absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="3c247-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

