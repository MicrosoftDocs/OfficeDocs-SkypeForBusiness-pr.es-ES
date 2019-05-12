---
title: Configurar las directivas de arranque de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumen: Cómo administrar las directivas de grupo.'
ms.openlocfilehash: 050040ae6de828e20aadf75bc4d8accfa782fc7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895373"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar las directivas de arranque de cliente
 
**Resumen:** Cómo administrar las directivas de grupo.
  
La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que puede usar para administrar directivas de grupo. Incluido con la plantilla administrativa de la directiva de grupo de Office son lync16.admx (ADMX) y las plantillas administrativas de .adml (ADML), que contienen la configuración de directiva basadas en el registro de Skype para la empresa que se configure para objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos del idioma de los archivos ADMX. Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office. Puede [descargar los archivos de plantilla administrativa de Office 2016 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) de manera gratuita desde Microsoft Download Center.
  
Para Skype para clientes empresariales, hay varias cliente las directivas que se debe considerar la configuración antes de que los usuarios inician sesión el servidor por primera vez de arranque. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente tiene que usar hasta que se complete el inicio de sesión. Puede usar la directiva de grupo para establecer esta configuración en los registros del equipo de los usuarios antes de iniciar sesión y empezar a recibir la configuración de aprovisionamiento en banda desde el servidor. En la siguiente tabla muestra la configuración de directiva de grupo que está disponible para Skype para la empresa.
  
**Configuración de directiva de grupo para Skype para la empresa**

|Configuración de directiva de grupo|Descripción|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica cómo Skype para la empresa identifica el transporte y el servidor que desea usar durante el inicio de sesión. En esta opción puede especificar lo siguiente: <br/>  ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo. <br/>  ServerAddressInternal: Especifica el nombre del servidor o la dirección IP se utiliza cuando los clientes se conectan desde dentro del firewall de la organización. <br/>  Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS). <br/> |
|Otras versiones del servidor compatibles (ConfiguredServerCheckValues)  <br/> |Especifica una lista de nombres de versión de servidor separados por punto y coma que Skype para Business Server iniciará sesión, además a las versiones de servidor que se admiten de forma predeterminada.  <br/> |
|Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)  <br/> |Automáticamente carga los registros de errores de inicio de sesión en Skype para Business Server para su análisis. No se cargan automáticamente registros si el inicio de sesión es correcto. Si esta directiva no está configurada, ocurre lo siguiente:  <br/> Para Skype para usuarios profesionales en línea: los registros de errores de inicio de sesión se cargan automáticamente. Para Skype para la empresa local a los usuarios: se muestra un cuadro de diálogo de confirmación al usuario antes de cargar. Cuando esta opción está deshabilitada, los registros de inicio de sesión se cargan automáticamente a la Skype para Business Server para Skype para empresarial local y Skype para usuarios profesionales en línea. Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.  <br/> |
|Deshabilitar reserva HTTP para la conexión SIP (DisableHttpConnect)  <br/> |Impide que Skype para Business Server intenta conectarse al servidor mediante el uso de HTTP, si TLS o TCP no está disponible. De forma predeterminada, Skype para la empresa en primer lugar intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se realiza correctamente, Skype para la empresa intenta conectar utilizando HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.  <br/> |
|Requerir credenciales de inicio de sesión (DisableNTCredentials)  <br/> |Requiere que el usuario proporcione las credenciales de inicio de sesión para Skype para el negocio, en lugar de utilizar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.  <br/> |
|Deshabilitar la comprobación de versión del servidor (DisableServerCheck)  <br/> |Si esta directiva se establece en 1, impide que Skype para la empresa de comprobación antes de iniciar sesión el nombre del servidor y la versión. De forma predeterminada, Skype para la empresa realiza estas comprobaciones antes de iniciar sesión.  <br/> |
|Permitir el uso de BITS para descargar archivos del servicio de libreta de direcciones (EnableBitsForGalDownload)  <br/> |Permite Skype para la empresa usar el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de servicios de la libreta de direcciones.  <br/> |
|Configurar modo de seguridad SIP (EnableSIPHighSecurityMode)  <br/> |Permite Skype para la empresa enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.  <br/> Si no configura esta opción de directiva, Skype para la empresa puede usar cualquier transporte. Pero si no utiliza TLS y si el servidor autentica a los usuarios, Skype para la empresa se debe usar la autenticación NTLM o Kerberos.  <br/> |
|Retraso inicial (GalDownloadInitialDelay) de descarga de la libreta de direcciones global  <br/> |Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.  <br/> |
|Impedir que los usuarios ejecuten Skype para la empresa (PreventRun)  <br/> |Impide que los usuarios ejecuten Skype para la empresa. Puede establecer esta configuración de directiva en Configuración del equipo o en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.  <br/> |
|Permitir el almacenamiento de las contraseñas de usuario (SavePassword)  <br/> |Permite Skype para la empresa almacenar contraseñas.  <br/> |
|Configurar el modo de compresión SIP (SipCompression)  <br/> |Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.  <br/> |
|Lista de dominios de confianza (TrustModelData)  <br/> |Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.  <br/> |
   
Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.
  
**Prioridad de las directivas de grupo**

|**Prioridad**|**Ubicación o método de configuración**|
|:-----|:-----|
|1  <br/> |Skype para Business Server del aprovisionamiento en banda  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |El cuadro de diálogo Opciones de Skype para la empresa  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir la configuración de directiva de grupo mediante el uso de la Skype para los archivos de plantilla administrativa de negocio

1. Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio. 
  
2. Cree una subcarpeta para cada idioma que usará. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

