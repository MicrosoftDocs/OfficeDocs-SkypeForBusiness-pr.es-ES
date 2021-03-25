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
description: 'Aprenda a configurar la seguridad de las aplicaciones móviles para los usuarios. '
ms.openlocfilehash: d599542970cec5aa4206f29d3ff7fa27ce36e9a0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109956"
---
# <a name="skype-for-business-mobile-app-security"></a>Seguridad de la aplicación para móviles de Skype Empresarial

## <a name="skype-for-business-client-security"></a>Seguridad del cliente de Skype Empresarial

En este artículo se cubre la información relacionada con el cifrado de datos en las aplicaciones Skype Empresarial para móviles.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nombre de usuario/Contraseña** <br/> |**Datos de la aplicación (conversaciones, <br/> lista de contactos, reuniones)** <br/> |**Registros de diagnóstico** <br/> |
|**Android** <br/> |La información de credenciales se almacena en Cuentas de Android. Antes de ello, también se cifra mediante el algoritmo " **AES/CBC/PKCS5Padding** ".<br/> |El almacenamiento se realiza en una base de datos SQL cifrada mediante una biblioteca llamada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Para ello se utiliza su algoritmo predeterminado de AES de 256 bits en modo CBC. Los datos en reposo están siempre cifrados en el archivo de la base de datos y solo se descifran en el tránsito interno de la memoria volátil de la aplicación y la pila de llamadas. También ciframos los archivos del buzón de voz con el mismo método que se utiliza para cifrar la contraseña y el nombre del usuario (no se almacenan en la base de datos). Los correos de voz se descifran temporalmente en el disco para poder reproducirlos.<br/> |Esta información no está cifrada.  <br/> |
|**iOS** <br/> |El nombre de usuario y la contraseña NO se cifran en la cadena de claves. Sin embargo, la cadena de claves está cifrada por sí misma.  <br/> |Ahora usamos la etiqueta de protección de datos [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) en todos los archivos del almacenamiento de aplicaciones. Esto significa que los archivos del almacenamiento de la aplicación estarían cifrados hasta que el usuario desbloquee el dispositivo por primera vez tras haberlo reiniciado.<br/> |Esta información no está cifrada.  <br/> |
|**Windows Phone** <br/> |Windows Phone utiliza DPAPI (la API de protección de datos) de Windows para proteger las contraseñas. Creo que el esquema de cifrado que se utiliza es AES. Windows no nos da la opción de configurar el tamaño de la clave (o el esquema), por lo que es el que ofrece DPAPI, sea cual sea. Usará el TPM del dispositivo para proteger las claves que sean específicas del usuario y el dispositivo. Tenga en cuenta que las claves de DPAPI no son específicas de la aplicación.  <br/> |Los datos de las aplicaciones de Windows Phone se protegen con [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, como las credenciales. Dependiendo del nivel de detalle que queramos, parte de la información del índice de los datos de la aplicación se protege mediante el cifrado AES (que no es DPAPI) para evitar la sal, de manera que podamos buscar sin descifrar y que la clave, a su vez, esté protegida con DPAPI. Cualquier proceso del mismo teléfono puede leer los datos de la memoria caché, siempre que este pueda tener acceso a nuestra carpeta de datos. El cifrado de Windows no protege ante brechas del espacio aislado, sino que solo protege ante intentos de acceso externos.<br/> |Esta información no está cifrada.  <br/> |
   
**Nota:** Consulte esta documentación [pública para](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) la aplicación de pin de dispositivo disponible en cada una de las plataformas móviles anteriores
  
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
