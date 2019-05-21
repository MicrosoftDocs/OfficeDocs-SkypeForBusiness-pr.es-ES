---
title: Solicitud de certificado (básica)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La página nombre y configuración de seguridad proporciona un cuadro de texto para definir un nombre descriptivo, una lista desplegable para la longitud en bits del par de claves privada y pública, y una casilla que le permite marcar la clave privada del certificado como exportable.
ms.openlocfilehash: 4759b550c8e6aaa0c09b0ef44a6547ae3722a082
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273776"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="f7273-103">Solicitud de certificado (básica)</span><span class="sxs-lookup"><span data-stu-id="f7273-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="f7273-104">La página **nombre y configuración de seguridad** proporciona un cuadro de texto para definir un **nombre descriptivo**, una lista desplegable para la **longitud en bits** del par de clave privada y pública, y una casilla que le permite \*\*marcar la clave privada del certificado como \*\*exportable.</span><span class="sxs-lookup"><span data-stu-id="f7273-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="f7273-105">El nombre descriptivo, o sencillo, de un certificado es un nombre fácilmente reconocible que permite que la persona que lo ve lo identifique más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="f7273-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="f7273-106">La longitud de bits del par de claves pública y privada se puede seleccionar entre 1024, 2048 o 4096.</span><span class="sxs-lookup"><span data-stu-id="f7273-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="f7273-107">Activar la casilla para **marcar la clave privada del certificado como** exportable permite que el certificado y la clave privada se exporten y muevan a otro equipo o servidor.</span><span class="sxs-lookup"><span data-stu-id="f7273-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="f7273-108">La única vez que se necesita activar es cuando se crea un grupo de servidores perimetrales para el servicio de autenticación relé multimedia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="f7273-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f7273-109">Para ayudar a mantener la seguridad del certificado y el par de claves, debe seleccionar la opción marcar la clave privada del certificado como exportable solo si es absolutamente necesario.</span><span class="sxs-lookup"><span data-stu-id="f7273-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

