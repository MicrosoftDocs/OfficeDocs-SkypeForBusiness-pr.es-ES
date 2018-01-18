---
title: "Skype para la seguridad de aplicaciones móviles de negocio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Aprenda a configurar la seguridad de aplicaciones móviles para los usuarios. "
ms.openlocfilehash: bc80434cb29f6d2133ce99e9a583cb388fc7b1b3
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="skype-for-business-mobile-app-security"></a>Skype para la seguridad de aplicaciones móviles de negocio

## <a name="skype-for-business-client-security"></a>Skype para Business Client Security

Este artículo cubre información de cifrado de datos para aplicaciones de negocios móviles de Skype.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nombre de usuario y contraseña** <br/> |**Datos de la aplicación (conversaciones,<br/> póngase en contacto con la lista de reuniones)** <br/> |**Registros de diagnóstico** <br/> |
|**Android** <br/> |Almacenamos información de credenciales de cuentas Android. Ciframos credenciales antes de guardarlos en las cuentas. Utilizamos " **CBC/AES/PKCS5Padding** " algoritmo de cifrado. <br/> |Almacenamos en una base de datos cifrada de SQL utilizando una biblioteca denominada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Utilizamos su algoritmo predeterminado de AES de 256 bits en modo CBC. Los datos en reposo siempre se cifran en el archivo de base de datos y sólo están sin cifrar en tránsito dentro de las pilas volátiles de memoria y llamada de la aplicación. Ciframos también archivos de correo de voz utilizando el mismo método, como el nombre del usuario y el cifrado de contraseña (no se almacenan en la base de datos). Mensajes de voz son temporalmente sin cifrar en el disco para permitir la reproducción.  <br/> |Esta información no está cifrada.  <br/> |
|**iOS** <br/> |No cifrar el nombre de usuario y la contraseña en las llaves. Sin embargo, las llaves se cifran por sí mismo.  <br/> |Ya estamos utilizando el indicador de protección de datos de [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) en todos los archivos en el almacenamiento de la aplicación. Esto significa que se podrían cifrar archivos en el almacenamiento de la aplicación hasta que el usuario desbloquea el dispositivo por primera vez después del reinicio del dispositivo. <br/> |Esta información no está cifrada.  <br/> |
|**Windows Phone** <br/> |Windows Phone utiliza DPAPI (API de protección de datos) en Windows para proteger las contraseñas. Creo que el esquema de codificación utilizado es AES. Windows no nos da una opción para configurar el tamaño de clave (o combinación), por lo que es lo que ofrece DPAPI. Utilizará el dispositivo TPM para proteger claves que son específicas para el usuario y el dispositivo. Tenga en cuenta que las claves DPAPI no son específicas de la aplicación.  <br/> |Data de App WP están protegidos con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, como las credenciales. Dependiendo del detalle que queremos, parte de la información de índice para los datos de la aplicación está protegido por cifrado de AES (no-DPAPI) para evitar la salazón, por lo que podemos buscar un sin descifrar y que a su vez esté protegido con DPAPI. Pueden leer datos almacenados en caché por cualquier proceso, desde el mismo teléfono, suponiendo que puede llegar a nuestra carpeta de datos. Cifrado de Windows no protege de la violación de recinto de seguridad, intenta únicamente tener acceso externo.  <br/> |Esta información no está cifrada.  <br/> |
   
**Nota:** Consulte [esta documentación pública](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) para la aplicación de pin de dispositivo disponible en cada una de las anteriores plataformas móviles
  
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)
