---
title: "Solución de problemas de inicio de sesión de Skype Empresarial Online para administradores"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Solución de problemas de inicio de sesión de Skype Empresarial Online para administradores

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Para solucionar errores de inicio de sesión de Skype Empresarial Online, empiece eliminando las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional.
  
## ¿Qué desea hacer?
<a name="__top"> </a>

> [Comprobar causas frecuentes de errores de inicio de sesión de Skype Empresarial Online](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [Seguir pasos de solución para un error específico (solo empresas)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [Agregue una entrada de firewall para msoidsvc.exe en su servidor proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [Actualizar la configuración DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [Instale un certificado SSL de un tercero en su servidor ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [Actualizar credenciales de seguridad](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [Modifique las claves de registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Actualice la configuración de usuario en Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Usar la guía de solución de problemas del soporte técnico de Microsoft](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [Recopilar más información y buscar ayuda adicional](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Comprobar causas frecuentes de errores de inicio de sesión de Skype Empresarial Online
<a name="__toc323194094"> </a>

Problemas de inicio de sesión mayoría pueden deberse a un pequeño número de causas y muchos de ellos son fáciles de corregir. La siguiente tabla enumera algunas causas comunes de errores de inicio de sesión y algunos pasos que usted o los usuarios pueden seguir para resolverlos.
  
|**Causa posible**|**Solución**|
|:-----|:-----|
|Durante el inicio de sesión, aparece un cuadro de diálogo que contiene la siguiente frase: **no puede verificar si el servidor es de confianza para la dirección de inicio de sesión. Conectar de todos modos?** <br/> |Verifique que el nombre de dominio del cuadro de diálogo pertenezca a un servidor de confianza de su organización, por ejemplo, **domainName.contoso.com**. Pídale al usuario que seleccione la casilla **Confiar siempre en este servidor** y, a continuación, haga clic en **Conectar**. <br/> Los clientes empresariales pueden evitar que aparezca este mensaje cuando un usuario inicia sesión por primera vez, modificando el registro de Windows en el equipo de cada usuario. Para obtener detalles, consulte [Modifique las claves de registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry).  <br/> |
|Error en la escritura de la dirección de inicio de sesión, nombre de usuario o contraseña  <br/> | Confirme que el nombre de inicio de sesión y la contraseña del usuario sean correctos. <br/>  Verifique que el nombre de inicio de sesión del usuario tenga el siguiente formato: **bobk@contoso.com**. Este puede ser diferente al formato que usó para iniciar sesión en la red de su organización.  <br/>  Pídale al usuario que intente iniciar sesión de nuevo. <br/> |
|Olvido de la contraseña  <br/> |Restablezca la contraseña del usuario y notifíquele la nueva contraseña provisoria.  <br/> |
|No tiene licencia para usar Skype Empresarial Online  <br/> |Confirme que el usuario está registrado como un usuario Skype Empresarial Online. Si no es así, registrar al usuario y, a continuación, pídale al volver a iniciar sesión.  <br/> |
|Versión incorrecta de Skype Empresarial Online instalado  <br/> |En general, este problema se asocia a un mensaje de error que contiene la siguiente frase: **es posible que el servicio de autenticación no sea compatible con esta versión del programa**.  <br/> Pídale al usuario que desinstale y vuelva a Skype Empresarial Online desde el Portal de Office 365.  <br/> |
|Problema para adquirir un certificado personal obligatorio para iniciar sesión  <br/> |Si recientemente ha cambiado la dirección de inicio de sesión del usuario, deberá eliminar datos de inicio de sesión en caché. Pida a los usuarios para cerrar la sesión, haga clic en eliminar mi información de inicio de sesión de vínculo en la pantalla de inicio de sesión y vuelva a intentarlo.  <br/> |
|Estableció un nombre de dominio personalizado y es posible que los cambios no hayan terminado de propagarse en el sistema.  <br/> |En primer lugar, asegúrese de que ha modificado los registros del servicio de nombres de dominio (DNS) para reflejar el cambio.  <br/> Si ya hizo los cambios necesarios en el DNS, recomiéndele al usuario que intente iniciar sesión más tarde. Los cambios en el DNS pueden demorar hasta 72 horas en verse reflejados en el sistema.  <br/> |
|Reloj del sistema no sincronizado con el reloj del servidor  <br/> |Asegúrese de que el controlador de dominio de su red se esté sincronizando con una fuente de tiempo externa confiable. Para obtener detalles, consulte el artículo 816042 de Microsoft Knowledge Base, [Cómo configurar un servidor de tiempo autoritativo en Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
[Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades. Para su referencia, puede encontrar la versión en inglés de este artículo aquíhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar errores de inicio de sesión de Skype Empresarial Online, empiece eliminando las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Seguir pasos de solución para un error específico (solo empresas)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> Estas instrucciones se crearon para los clientes de Microsoft Office 365, Plan E. Si usted es cliente de Office 365, Plan P, pase a la sección que sigue, [Recopilar más información y buscar ayuda adicional](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1). 
  
Si ya probó las sugerencias de la sección anterior y el usuario todavía no puede iniciar sesión, puede seguir intentando solucionar el problema, según el tipo de error. En la siguiente tabla, se enumeran los mensajes de error más frecuentes y las causas posibles. Después de la tabla se detallan los procedimientos para tratar cada problema.
  
|**Mensaje de error**|**Causa posible**|**Solución**|
|:-----|:-----|:-----|
|No se encontró la dirección de inicio de sesión  <br/> |Las solicitudes de inicio de sesión del Asistente de inicio de sesión de Microsoft Online Services (msoidsvc.exe) no están atravesando su firewall externo o servidor proxy.  <br/> |[Agregue una entrada de firewall para msoidsvc.exe en su servidor proxy](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|El servidor no está disponible temporalmente  <br/> |Si su organización tiene un dominio personalizado, es posible que estén faltando las configuraciones necesarias para el Sistema de nombre de dominio (DNS) o que sean incorrectas.  <br/> |[Actualizar la configuración DNS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|El servidor no está disponible temporalmente  <br/> |Si su organización está utilizando un único inicio de sesión con Servicios de federación de Active Directory (ADFS), es posible que haya usado un certificado de Capas de sockets seguros (SSL) con firma personal en lugar de un certificado de una entidad de certificación externa.  <br/> |[Instale un certificado SSL de un tercero en su servidor ADFS](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|Problema para adquirir un certificado personal obligatorio para iniciar sesión  <br/> |Si ya ha quitado los datos almacenados en caché de servidor que se usan para iniciar sesión y sigue apareciendo el error, credenciales de seguridad del usuario pueden estar dañadas o una carpeta RSA del equipo del usuario esté bloqueando la autenticación.  <br/> |[Actualizar credenciales de seguridad](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|Cuando un usuario inicia sesión por primera vez, aparece un cuadro de diálogo del certificado de confianza.  <br/> |Este cuadro de diálogo aparece si su servidor Skype Empresarial todavía no aparece en la clave de registro **TrustModelData**.  <br/> |[Modifique las claves de registro TrustModelData](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|El usuario no tiene habilitación para SIP  <br/> |Si se hizo una instalación previa de Microsoft Office Communications Server o Microsoft Lync Server 2010 en su organización, es posible que no haya eliminado a sus usuarios del servidor antes de desinstalar el software. Como consecuencia, el atributo **msRTCSIP-UserEnabled** todavía está establecido como **FALSO** en los servicios de dominio de Active Directory. <br/> |[Actualice la configuración de usuario en Active Directory](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### Agregue una entrada de firewall para msoidsvc.exe en su servidor proxy
<a name="__add_a_firewall"> </a>

Este procedimiento es una solución posible para el siguiente mensaje de error: **No se encontró la dirección de inicio de sesión**.
  
 **NOTA**: en los pasos que siguen se asume que está usando Microsoft Forefront Threat Management Gateway (TMG) 2010. Si tiene otra solución para puerta de enlace web, use las configuraciones que se describen en el paso 4, a continuación.
  
Para crear una entrada de aplicación para Msoidsvc.exe en Forefront TMG 2010, siga estos pasos:
  
1. En el panel izquierdo, en primer plano, haga clic en **Conexión de red**.
    
2. Haga clic en la pestaña **Red**. En la pestaña **Tareas** del panel derecho, haga clic en **Establecer la configuración de cliente de Forefront TMG**.
    
3. En el cuadro de diálogo **Configuración de cliente de Forefront TMG**, haga clic en **Nuevo**.
    
4. En el cuadro de diálogo **Configuración de entrada de la aplicación**, configure la siguientes reglas:
    
|****Aplicación****|****Clave****|****Valor****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deshabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2409256, [que no puede conectarse a Skype empresarial Online porque un firewall local bloquea la conexión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### Actualizar la configuración DNS
<a name="__update_dns_service"> </a>

Si su organización tiene un dominio personalizado, este procedimiento representa una solución posible para el siguiente mensaje de error: **El servidor no está disponible temporalmente**.
  
- Póngase en contacto con el registrador de su nombre de dominio para obtener información sobre cómo agregar el siguiente registro CNAME a su dominio:
    
  - **Tipo de registro DNS**: CNAME
    
  - **Nombre**: sip
    
  - **Valor/Destino**: sipdir.online.microsoft.com
    
Para obtener información detallada, vea el artículo 2566790 de Microsoft Knowledge Base, [Skype solucionar problemas de configuración de DNS en línea de negocio en Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)y el artículo Wiki de Office 365, [asegurarse de que su red funcione con Skype empresarial (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
### Instale un certificado SSL de un tercero en su servidor ADFS
<a name="__verify_upn_and"> </a>

Para instalar un certificado SSL de un tercero en su servidor de Servicios de Federación de Active Domain (ADFS), siga estos pasos:
  
1. Obtenga un certificado SSL de una entidad de certificación externa como VeriSign o Thawte.
    
2. Instalar el certificado en el servidor de ADFS mediante la consola de administración de ADFS.
    
### Actualizar credenciales de seguridad
<a name="__update_security_credentials_1"> </a>

Este procedimiento representa una solución posible para el mensaje de error **Problemas para adquirir un certificado personal obligatorio para iniciar sesión**.
  
Para eliminar los posibles problemas con los certificados o credenciales, primero debe renovar el certificado del usuario en Windows Certificate Manager. Para hacerlo, siga estos pasos:
  
1. Abra Windows Certificate Manager. Para hacerlo, haga clic en **Inicio**, **Correr**, escriba **certmgr.msc** y haga clic en **Aceptar**.
    
2. Haga doble clic en **personal** y, a continuación, en **Certificados**.
    
3. Ordene por la columna **Emitido por** y, a continuación, busque un certificado que haya emitido Communications Server.
    
4. Haga clic con el botón secundario sobre el certificado y luego, haga clic en **Eliminar**.
    
Luego, si el usuario está usando Windows 7, elimine las credenciales almacenadas en Windows Credential Manager. Para hacerlo, siga estos pasos:
  
1. Haga clic en **Inicio**, **Panel de control** y, a continuación, en **Administrador de credenciales**.
    
2. Busque el conjunto de credenciales que se usa para conectarse a Skype Empresarial en línea.
    
3. Expanda el conjunto de credenciales y, a continuación, haga clic en **Quitar de la cámara**.
    
4. Volver a iniciar sesión y vuelva a escribir las credenciales del usuario.
    
Por último, si ya actualizó las credenciales, pero el usuario todavía no puede iniciar sesión, intente eliminar la carpeta RSA del equipo del usuario, ya que podría estar bloqueando el proceso de autenticación:
  
1. Inicie sesión en el equipo del usuario mediante una cuenta de administrador.
    
2. Si es necesario, active la opción de vista de carpeta **Mostrar archivos ocultos**.
    
3. Escriba lo siguiente en la barra de direcciones del explorador de archivos: **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, **donde** ** *UserName* ** ** es su nombre de inicio de sesión de Windows**.
    
4. Elimine todas las carpetas que empiecen con el nombre **S-1-5-21-** seguido de una cadena de números.
    
### Modifique las claves de registro TrustModelData
<a name="__modify_trustmodeldata_registry"> </a>

Cuando un usuario inicia sesión por primera vez, pueden recibir un cuadro de diálogo que contiene algo parecido al siguiente: **no puede verificar si el servidor es de confianza para la dirección de inicio de sesión. Conectar de todos modos?** Esta es una característica de seguridad y no un error. Sin embargo, puede impedir que el cuadro de diálogo aparezca utilizando un objeto de directiva de grupo (GPO) para actualizar los equipos de los usuarios con el nombre de dominio antes de que inicie sesión por primera vez. Para ello, haga lo siguiente:
  
- Cree e implemente un GPO que se anexe a su nombre de dominio Skype Empresarial, por ejemplo, DomainName.contoso.com, en el valor actual de HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.
    
> [!IMPORTANT]
> Debe *anexar*  su nombre de dominio al valor existente, no solo sustituirlo.
  
Para obtener detalles, consulte el artículo 2531068 de Microsoft Knowledge Base, [Skype Empresarial no puede verificar si el servidor es de confianza para su dirección de inicio de sesión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### Actualice la configuración de usuario en Active Directory
<a name="__update_user_settings_1"> </a>

Si se hizo una instalación previa de Microsoft Office Communications Server o Microsoft Lync Server 2010 en su organización, es posible que no haya eliminado a sus usuarios del servidor antes de desinstalar el software. Como consecuencia, el atributo **msRTCSIP-UserEnabled** todavía está establecido como **FALSO** en los servicios de dominio de Active Directory.
  
Para solucionar este problema, siga estos pasos:
  
1. Actualice el atributo **msRTCSIP-UserEnabled** en todos los usuarios afectados como **VERDADERO**.
    
2. Vuelva a ejecutar la herramienta de sincronización de directorios (DirSync) de Microsoft Online Services. Para obtener más información, vea [directorios de AIntegrate su locales con Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).
    
[Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades. Para su referencia, puede encontrar la versión en inglés de este artículo aquíhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar errores de inicio de sesión de Skype Empresarial Online, empiece eliminando las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Usar la guía de solución de problemas del soporte técnico de Microsoft
<a name="__toc325626447"> </a>

Si está todavía no puede resolver los problemas de inicio de sesión del usuario, revise la sugerencias del artículo 2541980, de Microsoft Knowledge Base acerca de [cómo solucionar problemas de inicio de sesión en Skype empresarial Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## Recopilar más información y buscar ayuda adicional
<a name="__collect_more_information_1"> </a>

Si ha seguido las directrices anteriores y sigue sin poder resolver sus problemas de inicio de sesión, debe recopilar información adicional y póngase en contacto con soporte técnico. Para ello, siga estos pasos:
  
1. Obtener los archivos de registro y detalles de registro de eventos de Windows desde el equipo del usuario. Para obtener instrucciones detalladas, vea el tema de ayuda para el usuario final [Activar registros de errores en Skype Empresarial](http://technet.microsoft.com/library/eaf6602b-95e0-4c27-869f-36017475806c%28Office.14%29.aspx).
    
2. Envíe los archivos de registro y la información detallada sobre el error al equipo de soporte técnico de Microsoft.
    
Es posible que le pidan que envíe más información de diagnóstico, mediante la instalación del Kit de herramientas de soporte de registro y diagnóstico de Microsoft Online Services (MOSDAL) en el equipo del usuario afectado. Para obtener detalles, consulte [Cómo usar el Kit de herramientas de soporte MOSDAL](http://technet.microsoft.com/library/ddf1f52f-24a1-4675-abe0-141052c88b72%28Office.14%29.aspx).
  
[Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades. Para su referencia, puede encontrar la versión en inglés de este artículo aquíhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Para solucionar errores de inicio de sesión de Skype Empresarial Online, empiece eliminando las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

