---
title: Configuración de directivas de arranque de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumen: Cómo administrar directivas de grupo.'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029061"
---
# <a name="configure-client-bootstrapping-policies"></a>Configuración de directivas de arranque de cliente
 
**Resumen:** Cómo administrar directivas de grupo.
  
La consola de administración de directivas de grupo (GPMC) y el editor de objetos de directiva de grupo son herramientas que se usan para administrar la Directiva de grupo. En la plantilla administrativa de la Directiva de grupo de Office se incluyen plantillas administrativas de lync16. ADMX (ADMX) y. ADML (ADML), que contienen la configuración de directiva basada en el registro de Skype empresarial que se configura para los objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos de idioma para archivos ADMX. Cada archivo ADMX y ADML contiene la configuración de directiva para una sola aplicación de Office. Puede [descargar los archivos de plantilla administrativa (ADMX/ADML) de Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) de forma gratuita desde el centro de descarga de Microsoft.
  
Para los clientes de Skype empresarial, hay varias directivas de arranque de cliente que debe considerar configurar antes de que los usuarios inicien sesión en el servidor por primera vez. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente debe usar hasta que se complete el inicio de sesión. Puede usar la Directiva de grupo para establecer estas opciones en los registros del equipo de los usuarios antes de iniciar sesión y comenzar a recibir la configuración de aprovisionamiento en banda del servidor. En la siguiente tabla se enumeran las opciones de configuración de directiva de grupo que están disponibles en Skype empresarial.
  
**Configuración de directiva de grupo para Skype empresarial**

|Configuración de directiva de grupo|Descripción|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica cómo identifica Skype empresarial el transporte y el servidor que se deben usar durante el inicio de sesión. En esta configuración, debe especificar lo siguiente: <br/>  ServerAddressExternal: especifica el nombre del servidor o la dirección IP que usan los clientes y los contactos federados cuando se conectan desde fuera del firewall externo. <br/>  ServerAddressInternal: especifica el nombre del servidor o la dirección IP que se usa cuando los clientes se conectan desde dentro del firewall de la organización. <br/>  Transport: especifica el protocolo de control de transmisión (TCP) o la seguridad de la capa de transporte (TLS). <br/> |
|Versiones de servidor adicionales admitidas (ConfiguredServerCheckValues)  <br/> |Especifica una lista de nombres de versiones de servidor separados por punto y coma en los que Skype empresarial Server iniciará sesión, además de las versiones de servidor admitidas de forma predeterminada.  <br/> |
|Deshabilitar la carga automática de registros de error de inicio de sesión (DisableAutomaticSendTracing)  <br/> |Carga automáticamente los registros de errores de inicio de sesión en Skype empresarial Server para su análisis. Si el inicio de sesión se realiza correctamente, no se cargará automáticamente ningún registro. Si esta Directiva no está configurada, ocurrirá lo siguiente:  <br/> Para los usuarios de Skype empresarial online: los registros de error de inicio de sesión se cargan automáticamente. Para usuarios locales de Skype empresarial: se muestra un cuadro de diálogo de confirmación al usuario antes de cargarlo. Cuando esta configuración está deshabilitada, los registros de inicio de sesión se cargan automáticamente en Skype empresarial Server para los usuarios de Skype empresarial local y Skype empresarial online. Cuando esta configuración está habilitada, los registros de inicio de sesión nunca se cargan automáticamente.  <br/> |
|Deshabilitar la reserva HTTP para la conexión SIP (DisableHttpConnect)  <br/> |Impide que Skype empresarial Server intente conectarse al servidor mediante HTTP, si TLS o TCP no están disponibles. De forma predeterminada, Skype empresarial primero intenta conectarse al servidor mediante TLS o TCP y, si ninguno de estos métodos de transporte se ha realizado correctamente, Skype empresarial intenta conectarse mediante HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.  <br/> |
|Requerir credenciales de inicio de sesión (DisableNTCredentials)  <br/> |Requiere que el usuario proporcione las credenciales de inicio de sesión de Skype empresarial en lugar de usar automáticamente las credenciales de Windows durante el inicio de sesión en un servidor SIP.  <br/> |
|Deshabilitar comprobación de la versión del servidor (DisableServerCheck)  <br/> |Si establece esta directiva en 1, evita que Skype empresarial Compruebe el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Skype empresarial realiza estas comprobaciones antes de iniciar sesión.  <br/> |
|Habilitar el uso de BITS para descargar archivos del servicio de libreta de direcciones (EnableBitsForGalDownload)  <br/> |Permite que Skype empresarial use el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de servicios de la libreta de direcciones.  <br/> |
|Configurar el modo de seguridad SIP (EnableSIPHighSecurityMode)  <br/> |Permite que Skype empresarial envíe y reciba mensajes instantáneos de forma más segura. Esta directiva no se aplica a los servicios de Windows .NET o Microsoft Exchange Server.  <br/> Si no establece esta configuración de Directiva, Skype empresarial puede usar cualquier transporte. Pero si no usa TLS y el servidor autentica a los usuarios, Skype empresarial debe usar la autenticación NTLM o Kerberos.  <br/> |
|Retraso inicial de descarga de la libreta de direcciones global (GalDownloadInitialDelay)  <br/> |Especifica el período de tiempo que debe transcurrir antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es de 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período aleatorio comprendido entre 0 y 60 minutos.  <br/> |
|Impedir que los usuarios ejecuten Skype empresarial (PreventRun)  <br/> |Impide que los usuarios ejecuten Skype empresarial. Puede configurar esta opción de directiva en Configuración del equipo y Configuración de usuario, si bien la configuración de directiva establecida en Configuración del equipo tiene prioridad.  <br/> |
|Permitir el almacenamiento de contraseñas de usuario (SavePassword)  <br/> |Permite que Skype empresarial almacene contraseñas.  <br/> |
|Configurar el modo de compresión SIP (SipCompression)  <br/> |Especifica cuándo se debe activar la compresión SIP. De forma predeterminada, la compresión SIP está habilitada en función de la velocidad del adaptador. Tenga en cuenta que al configurar esta directiva podría aumentar el tiempo de inicio de sesión.  <br/> |
|Lista de dominios de confianza (TrustModelData)  <br/> |Enumera los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.  <br/> |
   
Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.
  
**Prioridad de las directivas de grupo**

|**Precedence**|**Ubicación o método de configuración**|
|:-----|:-----|
|1   <br/> |Aprovisionamiento en banda de Skype empresarial Server  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Cuadro de diálogo Opciones de Skype empresarial  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir la configuración de la Directiva de grupo con los archivos de plantilla administrativa de Skype empresarial

1. Cree una carpeta de nivel raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree una carpeta de nivel raíz del almacén central en su controlador de dominio en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > En este procedimiento se presupone que desea administrar varios equipos en su dominio. En este caso, se almacenan las plantillas en un almacén central en la carpeta Sysvol del controlador de dominio principal. Esto proporciona una ubicación del almacén central replicada para las plantillas administrativas del dominio. 
  
2. Cree una subcarpeta para cada idioma que vaya a usar. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para Inglés de Estados Unidos (EN-US) en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

