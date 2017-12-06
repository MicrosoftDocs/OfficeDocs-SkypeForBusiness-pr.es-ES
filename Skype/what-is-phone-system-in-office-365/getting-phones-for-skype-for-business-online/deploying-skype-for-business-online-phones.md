---
title: "Implementación de teléfonos de Skype Empresarial Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
description: "Learn the deployment steps to get the correct firmware, update it if needed, assign licences, and configure settings for Skype for Business online phones"
---

# Implementación de teléfonos de Skype Empresarial Online

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](faa17eb3-7483-4984-87f2-815d981b68ae.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/faa17eb3-7483-4984-87f2-815d981b68ae). 
  
Esta guía de implementación le ayudará a implementar teléfonos IP para Skype Empresarial Online.
  
En todos los tipos de empresas, tener un número de teléfono permite a los usuarios realizar y recibir llamadas de voz y es un requisito importante para realizar negocios. Los usuarios que tienen números telefónicos podrán realizar llamadas de voz en todos los dispositivos de Skype Empresarial incluidos teléfonos IP, equipos y dispositivos móviles. Puede obtener más información sobre Skype para teléfonos IP de empresa lea [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
  
## Pasos para la implementación de teléfonos IP

### Paso 1: descargar las guías para administradores y los manuales de los teléfonos del fabricante

Antes de comenzar, es recomendable descargar las guías para administradores y los manuales de usuario de los teléfonos que proporciona el fabricante.
  
- Para los teléfonos Polycom, consulte la [Guía de implementación de Polycom](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl).
    
- Para teléfonos Yealink, consulte [Yealink Skype para la solución de teléfonos SIP de empresa HD](http://www.yealink.com/solution_7.mdl).
    
- Para teléfonos AudioCodes, consulte la [Guía de administración del aprovisionamiento de AudioCodes](https://www.audiocodes.com/products/ems).
    
### Paso 2: asegurarse de que los teléfonos que va a comprar o a los que va a realizar la migración son teléfonos IP compatibles con Skype Empresarial y tienen el firmware adecuado

Un Skype empresarial Online admite teléfono y firmware también es compatible con Skype empresarial Server, pero lo opuesto no siempre es true. Para asegurarse de que va a comprar o el aprovisionamiento de un teléfono compatible y el firmware, vea [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
  
### Paso 3: comprobar que está instalado el firmware correcto y actualizarlo si es necesario

Comprobar la versión de firmware en teléfonos. Para:
  
- **Teléfonos Polycom VVX:** vaya a **Ajustes** > **Estado** > **Plataforma** > **Aplicación** > **Principal**.
    
- **Teléfonos Yealink:** vaya a **Estado** en la pantalla principal del teléfono.
    
- **Teléfonos AudioCodes:** desde la pantalla de inicio, vaya a **Menú** > **Estado del dispositivo** > **Versión de firmware**.
    
    > [!NOTE]
    > Para obtener acceso remoto a teléfono detalles, consulte guías de administración del fabricante. Consulte los vínculos encima de las guías de usuario y manuales de teléfono. 
  
- **Teléfonos Lync Phone Edition (LPE):** desde la pantalla de inicio, vaya a **Menú** > **Información del sistema**.
    
### Paso 4: consideraciones con respecto a la actualización de los dispositivos

> [!NOTE]
> Firmware Polycom antes 5.5.1.X tenía un mecanismo de bloqueo de dispositivo de fabricante específico que se reemplaza con un Skype para la implementación de negocios "Bloqueo de teléfono." Actualizar un teléfono de 5.4.X.X que estaba protegida con "Bloqueo del dispositivo" a 5.5.1.X con "Bloqueo de teléfono" no hereda el código PIN de "Dispositivo bloqueo," que puede dejar el teléfono no seguro. Los usuarios que han activado "Bloqueo del dispositivo" necesitan habilitar el parámetro de perfil de dispositivo de Polycom siguiente dar a los usuarios de control de tiempo de actualización (lync.deviceUpdate.popUpSK.enabled=1). 
  
La Skype administra las actualizaciones de firmware de servicio de la empresa. Cada Skype empresarial certificadas se carga firmware del teléfono para la Skype para Business actualizar servidor y actualización de dispositivo está habilitada en todos los teléfonos de forma predeterminada. Dependiendo del tiempo de inactividad de los intervalos de sondeo y del teléfono, teléfonos automáticamente descargar e instalar la últimas versiones certificadas. Puede deshabilitar a la configuración de actualización de dispositivo mediante el cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) y el valor del parámetro _EnableDeviceUpdate_ `false`.
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Cuando un nuevo firmware está disponible y listo para descargar e instalar, el teléfono notificará al usuario. Teléfonos Polycom se notificar al usuario y proporcione una opción para **Actualizar** o **Posponer**.
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
En un teléfono Polycom, puede actualizar el firmware desde el teléfono seleccionando **ActualizaciónSw**.
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
También puede optar por administrar las actualizaciones de firmware usando un sistema de aprovisionamiento de nuestros socios. Para obtener información sobre la administración de los sistemas de aprovisionamiento de nuestros socios y la personalización avanzada de teléfonos, consulte las guías de administración del fabricante.
  
> [!CAUTION]
> Asegúrese de que solo tiene una autoridad de actualización de dispositivos (actualización de dispositivos en banda o un servidor de aprovisionamiento de terceros) para evitar los bucles de actualizaciones. 
  
### Paso 5: configuración y las opciones de teléfono de infraestructura

Puede configurar las opciones y políticas más utilizadas de los teléfonos usando los cmdlets de Windows PowerShell para la administración en banda de Skype Empresarial. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obtener más información sobre estos parámetros y ajustes.
  
Para la planificación de la infraestructura de red, vea [Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### Paso 6: preparar a los usuarios para iniciar sesión

Para permitir a los usuarios correctamente, inicie sesión en un Skype para teléfono empresarial Online y realizar llamadas, debe asegurarse de que los usuarios se asignan las licencias correctas. Como mínimo, debe asignar una licencia de sistema telefónico y un Plan de llamada. Para obtener información adicional, puede ver [Skype para Business y Microsoft Teams licencias de complemento](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) y[Asignar Skype para Business y Microsoft Teams licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Puede encontrar más información sobre los planes de llamada lea [¿Qué planes de llamada en Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
  
- Las ** opciones de inicio de sesión** disponibles para los usuarios en línea son:
    
  - Los usuarios con **Polycom VVX 5XX y 6XX** teléfonos verán:
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obtener más información sobre las opciones de inicio de sesión admitidas por el fabricante, vea [Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
    
- **Id. de usuario**: usando el teclado del teléfono o el teclado en pantalla (si está disponible), los usuarios pueden usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como *amosm@contoso.com*  , en el nombre de usuario.
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > La autenticación con PIN no se admite en Skype Empresarial Online con teléfonos LPE y teléfonos IP de socios. 
  
- **Usar un PC** Cuando mejor juntos sobre software Ethernet (BToE) está instalado en el equipo del usuario y habilitada, los usuarios pueden iniciar sesión en sus teléfonos mediante la ventana de autenticación en su Windows de Skype empresarial. Para obtener más información, vea[Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)](faa17eb3-7483-4984-87f2-815d981b68ae.md#BK_BTOE) .
    
    > [!NOTE]
    > Los usuarios deben usar el nombre de usuario y la contraseña de su organización para iniciar sesión en el teléfono. Por ejemplo, deben usar el formato UPN, como  *amosm@contoso.com*  , en el nombre de usuario.
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Utilizar una inicio de sesión de Web**: se trata de una nueva forma de los usuarios autenticar mediante un explorador web estándar. Se proporcionará a los usuarios con un conjunto de instrucciones para seguir al usar un explorador para iniciar sesión.
    
  - Los usuarios con **Polycom VVX 5XX y 6XX** teléfonos verán:
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    El código que se genera caducará en 15 minutos. Cuando haya expirado, el usuario tendrá que hacer clic en **Reintentar** o en **Aceptar** para generar un nuevo código, según el teléfono.
    
  - Los usuarios con **Polycom VVX 5XX y 6XX** teléfonos verán:
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Los usuarios con teléfonos **Yealink T48G/T46G** verán:
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando un explorador, vaya a la dirección que se muestra en el teléfono e introduzca su nombre de usuario de Skype Empresarial.
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Introduzca el código que se muestra en el teléfono.
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Compruebe que el sitio muestra "[nombre del fabricante del teléfono] **Skype para teléfono del trabajo certificadas**," y haga clic en **continuar**.
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Haga clic en las credenciales de usuario o en **Usar otra cuenta**:
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Cuando aparezca la página siguiente, es seguro cerrar el explorador.
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Los teléfonos LPE para Skype Empresarial Online solo admiten el inicio de sesión mediante tethering USB. 
  
- **Implementaciones admitidas**: la siguiente tabla muestra los tipos de autenticación compatibles con los modelos de implementación que se admiten actualmente, incluidos la integración de Exchange, la autenticación moderna con Multi-factor Authentication (MFA) y Skype Empresarial Online y local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype Empresarial** <br/> |**Exchange** <br/> |**Método de inicio de sesión en el teléfono** <br/> |**Skype para el acceso de empresa** <br/> |**Acceso a Exchange con autenticación moderna y MFA desactivados** <br/> |**Acceso a Exchange con autenticación moderna y MFA activados** <br/> |
|En línea  <br/> |En línea  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|En línea  <br/> |En línea  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Inicio de sesión web  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|En línea  <br/> |Local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Autenticación de PIN  <br/> |Sí  <br/> |No  <br/> |No  <br/> |
|Local  <br/> |En línea/local  <br/> |Nombre de usuario y contraseña  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
|Local  <br/> |En línea/local  <br/> |Inicio de sesión vía equipo (BTOE)  <br/> |Sí  <br/> |Sí  <br/> |N/D  <br/> |
   
- **Características de teléfono** El conjunto de características puede variar ligeramente según el partner de teléfono IP. La característica completa establecido y para obtener más información sobre las características para cada fabricante del teléfono, vea[Obtener teléfonos con Skype Empresarial Online](getting-phones-for-skype-for-business-online.md).
    
- **Bloquear teléfono** es una característica recientemente introducida en Skype empresarial teléfonos de certificados que se utiliza para proteger un teléfono. Si está habilitado, los usuarios le pedirá que cree un PIN tras la autenticación. Una vez creada, teléfonos se bloquean cuando expira el tiempo agotado de inactividad que defina, un usuario bloquea manualmente su teléfono o sincronización su bloqueo de teléfono con un bloqueo de su PC utilizando emparejamiento de teléfono. Si el PIN de bloqueo de teléfono se escribe mal varias veces, el teléfono se cerrar la sesión del usuario o solicitar código del administrador para desbloquear el teléfono, pero esto variará dependiendo del socio de teléfono. El PIN del usuario debe estar entre 6 y 15 dígitos.
    
    Puede deshabilitar el bloqueo de teléfono de su organización (que está habilitado de forma predeterminada), cambiar el tiempo de espera de inactividad y elija si los usuarios pueden realizar llamadas telefónicas mientras están bloqueados o no utiliza configuración de banda. Para obtener más detalles acerca de la configuración, vea [Establecer CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) .
    
## Paso 7 (opcional): si se dispone de emparejamiento de dispositivos y Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE es un teléfono paining mecanismo de IP de Partner teléfonos que pares de teléfono de un usuario con sus Skype de Windows para la empresa App BToE permite a los usuarios:
  
- Iniciar sesión en su teléfono IP con su Skype para la aplicación de escritorio de la empresa (con un equipo)
    
- Sincronizar teléfono bloquear con bloqueo de PC
    
- Haga clic para llamar
    
BToE puede estar configurado para funcionar en dos modos:  *Manual*  y *automático*  (opción predeterminada). También puede ser habilitado (predeterminado) o deshabilitada para los usuarios con Skype para la configuración de banda de empresa. Cuando se trabaja en modo *Manual*  , los usuarios tendrán que realizar un paso adicional para emparejar el teléfono con su aplicación de Windows.
  
 **Para implementar BToE a los usuarios**
  
1. Conecte los equipos con los teléfonos usando el puerto de los equipos.
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Descargue el software BToE más reciente desde el sitio web del fabricante utilizando los vínculos que se ofrecen a continuación e instálelo. Para obtener una mejor experiencia de usuario, puede distribuir e instalar el software BToE usando una solución de distribución para administradores, como System Center Configuration Manager (SCCM). Para obtener ayuda sobre el uso de SCCM, consulte [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/es-es/sccm/apps/deploy-use/packages-and-programs).
    
  - [Sitio de descarga de Software de Polycom BToE](https://support.polycom.com/PolycomService/support/us/support/voice/polycom_uc/polycom_uc_software_for_lync.mdl)
    
  - [Descarga del software BToE de Yealink](http://www.yealink.com/solution_info.aspx?ProductsCateID=1471&amp;parentcateid=1471&amp;cateid=1471&amp;BaseInfoCateId=1328&amp;Cate_Id=1471)
    
  - [Descarga del software BToE de AudioCodes](ftp://VoP-C12:IPPLync@ftp.audiocodes.com/Release/3.0.0.Beta/BToE_1.1.8/)
    
3. La configuración de servidor de BToE se establece en **habilitado** y **modo automático** de forma predeterminada. Para cambiar esta configuración, vea[Establecer CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).
    
> [!NOTE]
> Actualmente BToE no es compatible con Mac ni plataformas VDI. 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

