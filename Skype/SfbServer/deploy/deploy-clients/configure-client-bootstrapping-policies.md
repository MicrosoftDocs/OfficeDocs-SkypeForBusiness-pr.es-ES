---
title: Configurar las directivas de arranque de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumen: Cómo administrar directivas de grupo.'
ms.openlocfilehash: 29e60ea772348ed5f483669cc1d17f8c13e96a02
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286540"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar las directivas de arranque de cliente
 
**Resumen:** Cómo administrar las directivas de grupo.
  
La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que puede usar para administrar directivas de grupo. En la plantilla administrativa de la Directiva de grupo de Office se incluyen las plantillas administrativas de lync16. ADMX (ADMX) y. ADML (ADML), que contienen la configuración de directiva basada en el registro para Skype empresarial que se configura para los objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos del idioma de los archivos ADMX. Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office. Puede [descargar los archivos de plantilla administrativa (ADMX/ADML) de Office 2016](https://www.microsoft.com/en-us/download/details.aspx?id=49030) de forma gratuita desde el centro de descarga de Microsoft.
  
Para los clientes de Skype empresarial, hay varias directivas de inicio del cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente tiene que usar hasta que se complete el inicio de sesión. Puede usar la Directiva de grupo para establecer esta configuración en los registros del equipo de los usuarios antes de que inicien sesión y empiecen a recibir la configuración de aprovisionamiento en banda del servidor. En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo que están disponibles en Skype empresarial.
  
**Configuración de directiva de grupo para Skype empresarial**

|Configuración de directiva de grupo|Descripción|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica cómo identifica Skype empresarial el transporte y el servidor que se van a usar durante el inicio de sesión. En esta opción puede especificar lo siguiente: <br/>  ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo. <br/>  ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde el Firewall de la organización. <br/>  Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS). <br/> |
|Versiones de servidor adicionales compatibles (ConfiguredServerCheckValues)  <br/> |Especifica una lista de nombres de versión de servidor separados por puntos y comas en los que iniciará sesión Skype empresarial Server, además de las versiones de servidor que son compatibles de forma predeterminada.  <br/> |
|Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)  <br/> |Carga automáticamente los registros de errores de inicio de sesión en Skype empresarial Server para su análisis. No se cargan automáticamente registros si el inicio de sesión es correcto. Si esta directiva no está configurada, ocurre lo siguiente:  <br/> Para los usuarios de Skype empresarial online: los registros de errores de inicio de sesión se cargan automáticamente. Para usuarios locales de Skype empresarial: se muestra un cuadro de diálogo de confirmación para el usuario antes de cargarlo. Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en el servidor de Skype empresarial para los usuarios locales de Skype empresarial y de Skype empresarial online. Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.  <br/> |
|Deshabilitar la reserva HTTP para conexión SIP (DisableHttpConnect)  <br/> |Impide que Skype empresarial Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Skype empresarial primero intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se realiza correctamente, Skype empresarial intenta conectarse mediante HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.  <br/> |
|Requerir credenciales de inicio de sesión (DisableNTCredentials)  <br/> |Requiere que el usuario proporcione credenciales de inicio de sesión para Skype empresarial en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.  <br/> |
|Deshabilitar comprobación de la versión del servidor (DisableServerCheck)  <br/> |Si establece esta directiva en 1, evita que Skype empresarial Compruebe el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Skype empresarial realiza estas comprobaciones antes de iniciar sesión.  <br/> |
|Habilitar el uso de BITS para descargar archivos del servicio de libreta de direcciones (EnableBitsForGalDownload)  <br/> |Permite que Skype empresarial use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.  <br/> |
|Configurar el modo de seguridad SIP (EnableSIPHighSecurityMode)  <br/> |Permite a Skype empresarial enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.  <br/> Si no establece esta configuración de Directiva, Skype empresarial puede usar cualquier transporte. Pero si no usa TLS y el servidor autentica a los usuarios, Skype empresarial debe usar la autenticación NTLM o Kerberos.  <br/> |
|Retardo inicial de descarga de libreta de direcciones global (GalDownloadInitialDelay)  <br/> |Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.  <br/> |
|Impedir que los usuarios ejecuten Skype empresarial (PreventRun)  <br/> |Impide que los usuarios ejecuten Skype empresarial. Puede establecer esta configuración de directiva en Configuración del equipo o en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.  <br/> |
|Permitir el almacenamiento de contraseñas de usuario (SavePassword)  <br/> |Permite que Skype empresarial almacene contraseñas.  <br/> |
|Configurar el modo de compresión SIP (SipCompression)  <br/> |Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.  <br/> |
|Lista de dominios de confianza (TrustModelData)  <br/> |Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.  <br/> |
   
Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.
  
**Prioridad de las directivas de grupo**

|**Prioridad**|**Ubicación o método de configuración**|
|:-----|:-----|
|1  <br/> |Aprovisionamiento en banda de Skype empresarial Server  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Cuadro de diálogo Opciones de Skype empresarial  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir la configuración de directiva de grupo mediante los archivos de la plantilla administrativa de Skype empresarial

1. Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio. 
  
2. Cree una subcarpeta para cada uno de los idiomas que va a usar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

