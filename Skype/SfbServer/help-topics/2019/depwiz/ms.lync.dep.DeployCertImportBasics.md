---
title: Importar certificado (introducción)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto Seleccionar archivo del certificado, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón Examinar y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.
ms.openlocfilehash: ec0eb1593c628e44fcbe5cfb8d47a381b9281406
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837110"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="16e3f-104">Importar certificado (introducción)</span><span class="sxs-lookup"><span data-stu-id="16e3f-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="16e3f-p102">Para importar un certificado, debe proporcionar la ruta del archivo del certificado. En el cuadro de texto **Seleccionar archivo del certificado**, puede escribir el nombre de archivo y la ruta completa, o bien hacer clic en el botón **Examinar** y buscar la ubicación y el nombre de archivo, que suele ser un archivo con la extensión .p7b, .pfx, o .cer.</span><span class="sxs-lookup"><span data-stu-id="16e3f-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="16e3f-107">Si el certificado contiene una clave privada, active la casilla **Archivo de certificado que contiene la clave privada del certificado.**</span><span class="sxs-lookup"><span data-stu-id="16e3f-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="16e3f-108">Si se selecciona esta casilla de verificación, se habilita la entrada de texto de **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="16e3f-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="16e3f-109">Si tiene un certificado asociado con una clave privada, al crearse el certificado se suele colocar una contraseña en la clave privada.</span><span class="sxs-lookup"><span data-stu-id="16e3f-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="16e3f-110">La contraseña de la clave privada se asigna para que el certificado y la clave privada puedan importarse al almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="16e3f-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="16e3f-111">Tras haber facilitado la información de la ruta de archivo del certificado, y la contraseña de clave privada, si era el caso, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="16e3f-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="16e3f-112">La importación no se realizará si no se proporciona la contraseña de clave privada.</span><span class="sxs-lookup"><span data-stu-id="16e3f-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

