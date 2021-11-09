---
title: Configurar las directivas de arranque de cliente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumen: Cómo administrar directivas de grupo.'
ms.openlocfilehash: 073bd23219b3fa0a39ed06a94a5ef0586a740e6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831654"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar las directivas de arranque de cliente
 
**Resumen:** Cómo administrar directivas de grupo.
  
La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que se usan para administrar la directiva de grupo. La plantilla administrativa de directiva de grupo de Office se incluye en las plantillas administrativas lync16.admx (ADMX) y .adml (ADML), que contienen las opciones de directiva basadas en el Registro para Skype Empresarial que se configuran para los objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos del idioma para los archivos ADMX. Cada archivo ADMX y ADML contiene la configuración de directiva de una sola Office aplicación. Puede descargar los archivos Office plantillas administrativas [de 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) de forma gratuita desde el Centro de descarga de Microsoft.
  
Para Skype Empresarial cliente, hay varias directivas de arranque de cliente que debe considerar la configuración antes de que los usuarios inicien sesión en el servidor por primera vez. Por ejemplo, los servidores predeterminados y el modo de seguridad que el cliente debe usar hasta que se complete el inicio de sesión. Puede usar la directiva de grupo para establecer esta configuración en los registros del equipo de los usuarios antes de iniciar sesión y empezar a recibir la configuración de aprovisionamiento en banda desde el servidor. En la tabla siguiente se enumeran las opciones de configuración de directiva de grupo que están disponibles para Skype Empresarial.
  
**Directiva de Configuración para Skype Empresarial**

|Configuración de directiva de grupo|Descripción|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica cómo Skype Empresarial identifica el transporte y el servidor que se va a usar durante el inicio de sesión. Dentro de esta configuración, se especifica lo siguiente: <br/>  ServerAddressExternal: especifica el nombre del servidor o la dirección IP que usan los clientes y los contactos federados al conectarse desde fuera del firewall externo. <br/>  ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde dentro del firewall de la organización. <br/>  Transporte: especifica el protocolo de control de transmisión (TCP) o la seguridad de la capa de transporte (TLS). <br/> |
|Versiones de servidor adicionales admitidas (ConfiguredServerCheckValues)  <br/> |Especifica una lista de nombres de versión de servidor separados por punto y comas en la que Skype Empresarial Server iniciar sesión, además de las versiones de servidor admitidas de forma predeterminada.  <br/> |
|Deshabilitar la carga automática de registros de errores de inicio de sesión (DisableAutomaticSendTracing)  <br/> |Carga automáticamente los registros de errores de inicio de sesión en Skype Empresarial Server para su análisis. No se cargan registros automáticamente si el inicio de sesión se realiza correctamente. Si esta directiva no está configurada, se produce lo siguiente:  <br/> Para Skype Empresarial en línea: los registros de errores de inicio de sesión se cargan automáticamente. Para Skype Empresarial usuarios locales: se muestra un cuadro de diálogo de confirmación al usuario antes de cargarlo. Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el Skype Empresarial Server para usuarios Skype Empresarial locales y Skype Empresarial online. Cuando esta configuración está habilitada, los registros de inicio de sesión nunca se cargan automáticamente.  <br/> |
|Deshabilitar la reserva HTTP para la conexión SIP (DisableHttpConnect)  <br/> |Impide Skype Empresarial Server intentar conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Skype Empresarial primero intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se realiza correctamente, Skype Empresarial intenta conectarse mediante HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.  <br/> |
|Requerir credenciales de inicio de sesión (DisableNTCredentials)  <br/> |Requiere que el usuario proporcione credenciales de inicio de sesión para Skype Empresarial en lugar de usar automáticamente Windows credenciales durante el inicio de sesión en un servidor SIP.  <br/> |
|Deshabilitar la comprobación de versión del servidor (DisableServerCheck)  <br/> |Si establece esta directiva en 1, Skype Empresarial comprobar el nombre y la versión del servidor antes de iniciar sesión. De forma predeterminada, Skype Empresarial realiza estas comprobaciones antes de iniciar sesión.  <br/> |
|Habilitar el uso de BITS para descargar archivos de servicio de libreta de direcciones (EnableBitsForGalDownload)  <br/> |Permite Skype Empresarial usar el Servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.  <br/> |
|Configurar el modo de seguridad SIP (EnableSIPHighSecurityMode)  <br/> |Permite Skype Empresarial enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no se aplica a los servicios de Windows .NET o Microsoft Exchange Server.  <br/> Si no configura esta configuración de directiva, Skype Empresarial puede usar cualquier transporte. Pero si no usa TLS y si el servidor autentica a los usuarios, Skype Empresarial debe usar la autenticación NTLM o Kerberos.  <br/> |
|Retraso inicial de descarga global de libreta de direcciones (GalDownloadInitialDelay)  <br/> |Especifica el período de tiempo antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período aleatorio de entre 0 y 60 minutos.  <br/> |
|Impedir que los usuarios ejecuten Skype Empresarial (PreventRun)  <br/> |Impide que los usuarios ejecuten Skype Empresarial. Puede configurar esta opción de directiva en Configuración del equipo y Configuración de usuario, si bien la configuración de directiva establecida en Configuración del equipo tiene prioridad.  <br/> |
|Permitir el almacenamiento de contraseñas de usuario (SavePassword)  <br/> |Permite Skype Empresarial para almacenar contraseñas.  <br/> |
|Configurar el modo de compresión SIP (SipCompression)  <br/> |Especifica cuándo se debe activar la compresión SIP. De forma predeterminada, la compresión SIP está habilitada en función de la velocidad del adaptador. Tenga en cuenta que al configurar esta directiva podría aumentar el tiempo de inicio de sesión.  <br/> |
|Lista de dominios de confianza (TrustModelData)  <br/> |Enumera los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.  <br/> |
   
Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.
  
**Prioridad de las directivas de grupo**

|**Precedence**|**Ubicación o método de configuración**|
|:-----|:-----|
|1  <br/> |Skype Empresarial Server aprovisionamiento en banda  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Cuadro de diálogo Opciones de Skype Empresarial  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir la configuración de directiva de grupo mediante el Skype Empresarial archivos de plantilla administrativa

1. Cree una carpeta de nivel raíz para que contenga todos los archivos ADMX sin idioma. Por ejemplo, cree una carpeta de nivel raíz del almacén central en su controlador de dominio en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > En este procedimiento se supone que desea administrar varios equipos del dominio. En este caso, las plantillas se almacenan en un almacén central en la carpeta Sysvol del controlador de dominio principal. Esto proporciona una ubicación del almacén central replicada para las plantillas administrativas del dominio. 
  
2. Crea una subcarpeta para cada idioma que usarás. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

