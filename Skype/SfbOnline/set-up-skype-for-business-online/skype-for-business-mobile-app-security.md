---
title: Seguridad de la aplicación para móviles de Skype Empresarial
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Aprenda a configurar la seguridad de las aplicaciones móviles para sus usuarios. '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010783"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="9694e-103">Seguridad de la aplicación para móviles de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9694e-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="9694e-104">Seguridad del cliente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9694e-104">Skype for Business Client Security</span></span>

<span data-ttu-id="9694e-105">En este artículo se cubre la información relacionada con el cifrado de datos en las aplicaciones Skype Empresarial para móviles.</span><span class="sxs-lookup"><span data-stu-id="9694e-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="9694e-106">**Nombre de usuario/Contraseña**</span><span class="sxs-lookup"><span data-stu-id="9694e-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="9694e-107">**Datos de la aplicación (conversaciones, <br/> lista de contactos, reuniones)**</span><span class="sxs-lookup"><span data-stu-id="9694e-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="9694e-108">**Registros de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="9694e-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="9694e-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="9694e-109">**Android**</span></span> <br/> |<span data-ttu-id="9694e-p101">La información de credenciales se almacena en Cuentas de Android. Antes de ello, también se cifra mediante el algoritmo " **AES/CBC/PKCS5Padding** ".</span><span class="sxs-lookup"><span data-stu-id="9694e-p101">We store credentials information in Android Accounts. We also encrypt credentials before saving them into Accounts. We use " **AES/CBC/PKCS5Padding** " algorithm for encryption. </span></span><br/> |<span data-ttu-id="9694e-p102">El almacenamiento se realiza en una base de datos SQL cifrada mediante una biblioteca llamada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Para ello se utiliza su algoritmo predeterminado de AES de 256 bits en modo CBC. Los datos en reposo están siempre cifrados en el archivo de la base de datos y solo se descifran en el tránsito interno de la memoria volátil de la aplicación y la pila de llamadas. También ciframos los archivos del buzón de voz con el mismo método que se utiliza para cifrar la contraseña y el nombre del usuario (no se almacenan en la base de datos). Los correos de voz se descifran temporalmente en el disco para poder reproducirlos.</span><span class="sxs-lookup"><span data-stu-id="9694e-p102">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/). We use their default algorithm of 256-bit AES in CBC mode. The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks. We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB). Voicemails are temporarily unencrypted on disk to allow playback.  </span></span><br/> |<span data-ttu-id="9694e-118">Esta información no está cifrada.</span><span class="sxs-lookup"><span data-stu-id="9694e-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="9694e-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="9694e-119">**iOS**</span></span> <br/> |<span data-ttu-id="9694e-p103">El nombre de usuario y la contraseña NO se cifran en la cadena de claves. Sin embargo, la cadena de claves está cifrada por sí misma.</span><span class="sxs-lookup"><span data-stu-id="9694e-p103">We DO NOT encrypt the username/password in the keychain. The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="9694e-p104">Ahora usamos la etiqueta de protección de datos [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) en todos los archivos del almacenamiento de aplicaciones. Esto significa que los archivos del almacenamiento de la aplicación estarían cifrados hasta que el usuario desbloquee el dispositivo por primera vez tras haberlo reiniciado.</span><span class="sxs-lookup"><span data-stu-id="9694e-p104">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage. This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot. </span></span><br/> |<span data-ttu-id="9694e-124">Esta información no está cifrada.</span><span class="sxs-lookup"><span data-stu-id="9694e-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="9694e-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="9694e-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="9694e-p105">Windows Phone utiliza DPAPI (la API de protección de datos) de Windows para proteger las contraseñas. Creo que el esquema de cifrado que se utiliza es AES. Windows no nos da la opción de configurar el tamaño de la clave (o el esquema), por lo que es el que ofrece DPAPI, sea cual sea. Usará el TPM del dispositivo para proteger las claves que sean específicas del usuario y el dispositivo. Tenga en cuenta que las claves de DPAPI no son específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9694e-p105">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords. I believe the encryption scheme used is AES. Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives. It will use the device TPM to secure keys which are specific to the user and device. Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="9694e-p106">Los datos de las aplicaciones de Windows Phone se protegen con [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, como las credenciales. Dependiendo del nivel de detalle que queramos, parte de la información del índice de los datos de la aplicación se protege mediante el cifrado AES (que no es DPAPI) para evitar la sal, de manera que podamos buscar sin descifrar y que la clave, a su vez, esté protegida con DPAPI. Cualquier proceso del mismo teléfono puede leer los datos de la memoria caché, siempre que este pueda tener acceso a nuestra carpeta de datos. El cifrado de Windows no protege ante brechas del espacio aislado, sino que solo protege ante intentos de acceso externos.</span><span class="sxs-lookup"><span data-stu-id="9694e-p106">WP App Data is protected with [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds. Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI. Cached data can be read by any process from the same phone, assuming it can reach our data folder. Windows encryption does not protect from sandbox breach, only external access attempts.  </span></span><br/> |<span data-ttu-id="9694e-135">Esta información no está cifrada.</span><span class="sxs-lookup"><span data-stu-id="9694e-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="9694e-136">**Nota:** Consulta esta documentación [pública para la](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) aplicación de pin de dispositivo disponible en cada una de las plataformas móviles anteriores</span><span class="sxs-lookup"><span data-stu-id="9694e-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9694e-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="9694e-137">Related topics</span></span>
[<span data-ttu-id="9694e-138">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="9694e-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9694e-139">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="9694e-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
