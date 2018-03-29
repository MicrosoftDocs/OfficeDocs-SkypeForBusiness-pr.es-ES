---
title: Configurar las directivas de arranque de cliente en Skype Empresarial Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumen: Cómo administrar la directiva de grupo para Skype para el negocio.'
ms.openlocfilehash: b2e2f9787dd54b783b0f24ce9a6bb152ea4a69d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-client-bootstrapping-policies-in-skype-for-business-server-2015"></a>Configurar las directivas de arranque de cliente en Skype Empresarial Server 2015
 
**Resumen:** Cómo administrar la directiva de grupo para Skype para el negocio.
  
La Consola de administración de directivas de grupo (GPMC) y el Editor de objetos de directiva de grupo son herramientas que puede usar para administrar directivas de grupo. Incluido en la plantilla administrativa de la directiva de grupo de Office son lync16.admx (ADMX) y plantillas administrativas .adml (ADML), que contienen la configuración de directiva basada en el registro de Skype para el negocio que configurar para objetos de directiva de grupo en el dominio. Los archivos ADML son complementos específicos del idioma de los archivos ADMX. Todos los archivos ADMX y ADML contienen la configuración de directiva de una única aplicación de Office. Puede [descargar los archivos de plantilla administrativa de Office 2016 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitamente desde Microsoft Download Center.
  
Para Skype para el negocio, hay varios clientes bootstrapping las políticas que se debe considerar la configuración antes de que los usuarios iniciar sesión el servidor por primera vez. Por ejemplo, el modo de seguridad y los servidores predeterminados que el cliente tiene que usar hasta que se complete el inicio de sesión. Puede utilizar Directiva de grupo para establecer estos valores en los registros del equipo de usuario antes de que inicie sesión y empezar a recibir configuración de aprovisionamiento en banda desde el servidor. La tabla siguiente muestra la configuración de directiva de grupo que están disponible para Skype para empresas.
  
**Configuración de directiva de grupo para el negocio de Skype**

|**Configuración de directiva de grupo**|**Descripción**|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica cómo Skype para empresas identifica el transporte y el servidor que se utilizará durante el inicio de sesión. En esta opción puede especificar lo siguiente: <br/>  ServerAddressExternal: especifica el nombre del servidor o la dirección IP que utilizan los clientes y los contactos federados al conectarse desde fuera del firewall externo. <br/>  ServerAddressInternal: Especifica el nombre del servidor o la dirección IP utilizada cuando los clientes se conecten desde dentro del servidor de seguridad de la organización. <br/>  Transporte: especifica el Protocolo de control de transmisión (TCP) o Seguridad de la capa de transporte (TLS). <br/> |
|Versiones adicionales de servidor compatible (ConfiguredServerCheckValues)  <br/> |Especifica una lista de nombres de versión de servidor separados por punto y coma que Skype para Business Server 2015 se iniciar sesión en, además de las versiones de servidor admitidas de manera predeterminada.  <br/> |
|Deshabilitar la carga automática de los registros de errores de inicio de sesión (DisableAutomaticSendTracing)  <br/> |Carga automáticamente los registros de errores de inicio de sesión en Skype para Business Server 2015 para el análisis. No se cargan automáticamente registros si el inicio de sesión es correcto. Si esta directiva no está configurada, ocurre lo siguiente:  <br/> Para Skype para usuarios de negocios en línea: registros de errores de inicio de sesión se cargan automáticamente. De Skype para empresas usuarios locales: se muestra un cuadro de diálogo de confirmación al usuario antes de cargar. Cuando esta opción está deshabilitada, los registros de inicio de sesión se envían automáticamente a la Skype para Business Server para Skype para negocios locales y Skype para usuarios de negocios en línea. Cuando este parámetro está habilitado, los registros de inicio de sesión nunca se cargan automáticamente.  <br/> |
|Deshabilitar reserva HTTP para la conexión SIP (DisableHttpConnect)  <br/> |Impide que Skype para Business Server intenta conectarse al servidor mediante HTTP, si TLS o TCP no está disponible. De forma predeterminada, Skype para el negocio primero intenta conectarse al servidor utilizando TLS o TCP y Skype para el negocio si ninguno de estos métodos de transporte es correcta, intenta conectar utilizando HTTP. Use esta directiva para deshabilitar el intento de conexión HTTP de reserva.  <br/> |
|Requerir credenciales de inicio de sesión (DisableNTCredentials)  <br/> |Solicita al usuario que proporcione credenciales de inicio de sesión de Skype para el negocio, en lugar de utilizar automáticamente las credenciales de Windows al iniciar la sesión en un servidor SIP.  <br/> |
|Deshabilitar la comprobación de versión del servidor (DisableServerCheck)  <br/> |Si esta directiva se establece en 1, impide Skype para empresas el nombre del servidor y la versión antes de iniciar sesión. De forma predeterminada, Skype para empresas realiza estas comprobaciones antes de iniciar sesión.  <br/> |
|Habilitar el uso de BITS para descargar los archivos del servicio de libreta de direcciones (EnableBitsForGalDownload)  <br/> |Permite Skype para empresas utilizar el servicio de transferencia inteligente en segundo plano (BITS) para descargar los archivos de los servicios de libreta de direcciones.  <br/> |
|Configurar el modo de seguridad SIP (EnableSIPHighSecurityMode)  <br/> |Permite Skype para empresas enviar y recibir mensajes instantáneos de forma más segura. Esta directiva no afecta a los servicios de Microsoft Exchange Server ni Windows .NET.  <br/> Si no establece esta configuración de directiva, Skype para empresas puede utilizar cualquier tipo de transporte. Pero si no utiliza TLS y si el servidor autentica a los usuarios, Skype para el negocio debe utilizar autenticación NTLM o Kerberos.  <br/> |
|Libreta de direcciones global descargar retardo inicial (GalDownloadInitialDelay)  <br/> |Especifica el período de tiempo que transcurrirá antes de que se produzca una descarga de la lista global de direcciones (GAL). El valor predeterminado es 60 minutos, lo que significa que el servidor retrasa la descarga del archivo GAL durante un período de tiempo aleatorio comprendido entre 0 y 60 minutos.  <br/> |
|Impedir que los usuarios ejecuten Skype para empresas (PreventRun)  <br/> |Impide que los usuarios ejecuten Skype para empresas. Puede establecer esta configuración de directiva en Configuración del equipo o en Configuración de usuario, pero la configuración de directiva de Configuración del equipo tiene prioridad.  <br/> |
|Permitir el almacenamiento de contraseñas de usuario (SavePassword)  <br/> |Permite Skype para empresas almacenar contraseñas.  <br/> |
|Configurar el modo de compresión de SIP (SipCompression)  <br/> |Especifica cuándo debe activarse la compresión SIP. De forma predeterminada, la compresión SIP se habilita en función de la velocidad del adaptador. Tenga en cuenta que la configuración de esta directiva puede provocar un aumento en el tiempo de inicio de sesión.  <br/> |
|Lista de dominios de confianza (TrustModelData)  <br/> |Muestra los dominios de confianza que no coinciden con el prefijo del dominio SIP del cliente.  <br/> |
   
Las directivas configuradas en el servidor tienen prioridad frente a la configuración de las directivas de grupo y las opciones de cliente que configure el usuario. En la tabla siguiente se indica el orden de prioridad de la configuración cuando se produce un conflicto.
  
**Prioridad de directiva de grupo**

|**Prioridad**|**Ubicación o método de configuración**|
|:-----|:-----|
|1  <br/> |Skype para el aprovisionamiento en banda de Business Server 2015  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |El cuadro de diálogo Opciones de Skype para empresas  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir la configuración de directiva de grupo utilizando el Skype para los archivos de plantilla administrativa de negocios

1. Cree una carpeta de nivel de raíz que contenga todos los archivos ADMX independientes del idioma. Por ejemplo, cree la carpeta raíz del almacén central en el controlador del dominio en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimiento presupone que desea administrar varios equipos en su dominio. En este caso, almacena las plantillas de un almacén central en la carpeta Sysvol del controlador del dominio principal. Así obtendrá una ubicación de almacenamiento central replicada para las plantillas administrativas del dominio. 
  
2. Cree una subcarpeta para cada idioma que se utilizará. Estas subcarpetas contendrán los archivos de recursos ADML específicos del idioma. Por ejemplo, cree una subcarpeta para inglés de Estados Unidos (EN-US) en esta ubicación:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

