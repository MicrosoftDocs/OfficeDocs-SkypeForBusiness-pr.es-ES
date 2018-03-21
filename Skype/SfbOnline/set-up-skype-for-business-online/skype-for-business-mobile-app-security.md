---
title: "Skype para la seguridad de aplicaciones móviles de negocio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Aprenda a configurar la seguridad de aplicaciones móviles para los usuarios. "
ms.openlocfilehash: 98a748ca626d9b27a3e75ce5d75641155af7853d
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="skype-for-business-mobile-app-security"></a>Skype para la seguridad de aplicaciones móviles de negocio

## <a name="skype-for-business-client-security"></a>Seguridad del cliente de Skype Empresarial

En este artículo se cubre la información relacionada con el cifrado de datos en las aplicaciones Skype Empresarial para móviles.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nombre de usuario/Contraseña** <br/> |**Datos de la aplicación (conversaciones,<br/> póngase en contacto con la lista de reuniones)** <br/> |**Registros de diagnóstico** <br/> |
|**Android** <br/> |La información de credenciales se almacena en Cuentas de Android. Antes de ello, también se cifra mediante el algoritmo " **AES/CBC/PKCS5Padding** ".<br/> |El almacenamiento se realiza en una base de datos SQL cifrada mediante una biblioteca llamada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Para ello se utiliza su algoritmo predeterminado de AES de 256 bits en modo CBC. Los datos en reposo están siempre cifrados en el archivo de la base de datos y solo se descifran en el tránsito interno de la memoria volátil de la aplicación y la pila de llamadas. También ciframos los archivos del buzón de voz con el mismo método que se utiliza para cifrar la contraseña y el nombre del usuario (no se almacenan en la base de datos). Los correos de voz se descifran temporalmente en el disco para poder reproducirlos.<br/> |Esta información no está cifrada.  <br/> |
|**iOS** <br/> |El nombre de usuario y la contraseña NO se cifran en la cadena de claves. Sin embargo, la cadena de claves está cifrada por sí misma.  <br/> |Ahora usamos la etiqueta de protección de datos [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) en todos los archivos del almacenamiento de aplicaciones. Esto significa que los archivos del almacenamiento de la aplicación estarían cifrados hasta que el usuario desbloquee el dispositivo por primera vez tras haberlo reiniciado.<br/> |Esta información no está cifrada.  <br/> |
|**Windows Phone** <br/> |Windows Phone utiliza DPAPI (la API de protección de datos) de Windows para proteger las contraseñas. Creo que el esquema de cifrado que se utiliza es AES. Windows no nos da la opción de configurar el tamaño de la clave (o el esquema), por lo que es el que ofrece DPAPI, sea cual sea. Usará el TPM del dispositivo para proteger las claves que sean específicas del usuario y el dispositivo. Tenga en cuenta que las claves de DPAPI no son específicas de la aplicación.  <br/> |Los datos de las aplicaciones de Windows Phone se protegen con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, como las credenciales. Dependiendo del nivel de detalle que queramos, parte de la información del índice de los datos de la aplicación se protege mediante el cifrado AES (que no es DPAPI) para evitar la sal, de manera que podamos buscar sin descifrar y que la clave, a su vez, esté protegida con DPAPI. Cualquier proceso del mismo teléfono puede leer los datos de la memoria caché, siempre que este pueda tener acceso a nuestra carpeta de datos. El cifrado de Windows no protege ante brechas del espacio aislado, sino que solo protege ante intentos de acceso externos.<br/> |Esta información no está cifrada.  <br/> |
   
**Nota:** Consulte [esta documentación pública](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) para la aplicación de pin de dispositivo disponible en cada una de las anteriores plataformas móviles
  
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a>¿Comentarios?
Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).