---
title: "Skype para la seguridad de la aplicación móvil de empresa"
ms.author: kenwith
author: kenwith
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
description: ""
---

# Skype para la seguridad de la aplicación móvil de empresa

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
## Seguridad del cliente de Skype Empresarial

En este artículo se cubre la información relacionada con el cifrado de datos en las aplicaciones Skype Empresarial para móviles.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nombre de usuario/Contraseña** <br/> |**Datos de aplicaciones (conversaciones, lista de contactos, reuniones)** <br/> |**Registros de diagnóstico** <br/> |
|**Android** <br/> |La información de credenciales se almacena en Cuentas de Android. Antes de ello, también se cifra mediante el algoritmo " **AES/CBC/PKCS5Padding** ". <br/> |El almacenamiento se realiza en una base de datos SQL cifrada mediante una biblioteca llamada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Para ello se utiliza su algoritmo predeterminado de AES de 256 bits en modo CBC. Los datos en reposo están siempre cifrados en el archivo de la base de datos y solo se descifran en el tránsito interno de la memoria volátil de la aplicación y la pila de llamadas. También ciframos los archivos del buzón de voz con el mismo método que se utiliza para cifrar la contraseña y el nombre del usuario (no se almacenan en la base de datos). Los correos de voz se descifran temporalmente en el disco para poder reproducirlos.  <br/> |Esta información no está cifrada.  <br/> |
|**iOS** <br/> |El nombre de usuario y la contraseña NO se cifran en la cadena de claves. Sin embargo, la cadena de claves está cifrada por sí misma.  <br/> |Ahora usamos la etiqueta de protección de datos [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) en todos los archivos del almacenamiento de aplicaciones. Esto significa que los archivos del almacenamiento de la aplicación estarían cifrados hasta que el usuario desbloquee el dispositivo por primera vez tras haberlo reiniciado. <br/> |Esta información no está cifrada.  <br/> |
|**Windows Phone** <br/> |Windows Phone utiliza DPAPI (la API de protección de datos) de Windows para proteger las contraseñas. Creo que el esquema de cifrado que se utiliza es AES. Windows no nos da la opción de configurar el tamaño de la clave (o el esquema), por lo que es el que ofrece DPAPI, sea cual sea. Usará el TPM del dispositivo para proteger las claves que sean específicas del usuario y el dispositivo. Tenga en cuenta que las claves de DPAPI no son específicas de la aplicación.  <br/> |Los datos de las aplicaciones de Windows Phone se protegen con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, como las credenciales. Dependiendo del nivel de detalle que queramos, parte de la información del índice de los datos de la aplicación se protege mediante el cifrado AES (que no es DPAPI) para evitar la sal, de manera que podamos buscar sin descifrar y que la clave, a su vez, esté protegida con DPAPI. Cualquier proceso del mismo teléfono puede leer los datos de la memoria caché, siempre que este pueda tener acceso a nuestra carpeta de datos. El cifrado de Windows no protege ante brechas del espacio aislado, sino que solo protege ante intentos de acceso externos.  <br/> |Esta información no está cifrada.  <br/> |
   
Nota: consulte [esta documentación pública](https://docs.microsoft.com/es-es/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) relacionada con el cumplimiento del PIN del dispositivo en cada una de las plataformas móviles anteriores.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

