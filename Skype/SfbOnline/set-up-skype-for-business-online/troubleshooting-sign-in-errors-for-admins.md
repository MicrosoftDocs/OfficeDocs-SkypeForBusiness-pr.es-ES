---
title: Solución de problemas de Skype para errores de inicio de sesión empresarial en línea para administradores
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
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
description: 'Aprender las causas comunes de Skype para errores de inicio de sesión empresarial en línea y el trabajo a través de solucionar estos problemas. '
ms.openlocfilehash: 5c3204304d44729be2e2f382ed213507832536b1
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Solución de problemas de Skype para errores de inicio de sesión empresarial en línea para administradores

Para solucionar los errores de inicio de sesión de negocios en línea Skype, iniciar mediante la eliminación de las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir los pasos en función del tipo de error de resolución específica. Si el usuario todavía no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional. 
  
## <a name="what-do-you-want-to-do"></a>¿Qué acción desea realizar?
<a name="top"> </a>

> [Verificación de las causas comunes de Skype para errores de inicio de sesión de negocios en línea](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [Siga los pasos de resolución de un error específico (sólo empresas)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [Agregar una entrada de servidor de seguridad para msoidsvc.exe en su servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [Actualizar la configuración de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [Instalar un certificado SSL de terceros en el servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [Actualizar las credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [Modificar las claves del registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [Actualizar la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [Utilice el Support Microsoft Guía de solución de problemas](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [Recopilar más información y buscar ayuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Verificación de las causas comunes de Skype para errores de inicio de sesión de negocios en línea
<a name="toc323194094"> </a>

Problemas de inicio de sesión más pueden atribuirse a un pequeño número de causas y muchas de ellas son fáciles de corregir. La tabla siguiente enumera algunas causas comunes de errores de inicio de sesión y algunos pasos que usted o los usuarios pueden realizar para resolverlas.
  
|**Causa posible**|**Resolución**|
|:-----|:-----|
|Al iniciar la sesión, aparece un cuadro de diálogo que contiene la frase siguiente: **no se puede comprobar que el servidor es de confianza en la dirección de inicio de sesión. Conectarse de todas formas?** <br/> |Compruebe que el nombre de dominio en el cuadro de diálogo es un servidor de confianza en su organización, por ejemplo, **domainName.contoso.com**. Pedir al usuario que Active la casilla de verificación **Confiar siempre en este servidor** y, a continuación, haga clic en **Conectar**. <br/> Los clientes empresariales pueden impedir que este mensaje aparezca cuando un usuario inicia sesión por primera vez modificando el registro de Windows en el equipo de cada usuario. Para obtener más información, consulte [TrustModelData modificar las claves del registro](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Cuya dirección de inicio de sesión, nombre de usuario o contraseña  <br/> | Confirme que el nombre de inicio de sesión del usuario y la contraseña son correctos. <br/>  Compruebe que el nombre de usuario inicio de sesión tiene el formato siguiente: **bobk@contoso.com**. Esto puede ser diferente del formato que se utiliza para iniciar sesión en la red de su organización.  <br/>  Pedir al usuario que intente iniciar sesión de nuevo. <br/> |
|Contraseña olvidada  <br/> |Restablecer la contraseña del usuario y notificar a él o ella de la nueva contraseña temporal.  <br/> |
|No tiene licencia para utilizar Skype para los negocios en línea  <br/> |Confirme que el usuario se registra como un Skype para usuarios de negocios en línea. Si no es así, registrar al usuario y, a continuación, pídale al iniciar sesión de nuevo.  <br/> |
|Versión incorrecta de Skype para los negocios en línea instalado  <br/> |Este problema se suele estar asociado a un mensaje de error que contenga la frase siguiente: **el servicio de autenticación puede ser incompatible con esta versión del programa**.  <br/> Pedir al usuario que desinstalar y volver a instalar Skype para los negocios en línea desde el Portal de Office 365.  <br/> |
|Problema al adquirir un certificado personal necesario para iniciar sesión en  <br/> |Si recientemente ha cambiado la dirección de inicio de sesión del usuario, deberá eliminar los datos de inicio de sesión en caché. Pedir a los usuarios cerrar la sesión, haga clic en eliminar mi información de inicio de sesión de enlace en la pantalla de inicio de sesión y vuelva a intentarlo.  <br/> |
|Configurar un nombre de dominio personalizado, y los cambios que no hayan terminado de propagarse a través del sistema.  <br/> |En primer lugar, asegúrese de que ha modificado los registros del servicio de nombres de dominio (DNS) para reflejar el cambio.  <br/> Si ya ha realizado los cambios necesarios de DNS, aconsejar al usuario que vuelva a conectarse más tarde. Cambios de DNS pueden tardar hasta 72 horas para que se reflejen en todo el sistema.  <br/> |
|Sistema de reloj sincronizados con el reloj del servidor  <br/> |Asegúrese de que el controlador de dominio de la red se sincroniza con un origen de hora externo confiable. Para obtener más información, consulte el artículo 816042 de Microsoft Knowledge Base [cómo configurar un servidor horario con autoridad en Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |
   
Para solucionar los errores de inicio de sesión de negocios en línea Skype, iniciar mediante la eliminación de las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir los pasos en función del tipo de error de resolución específica. Si el usuario todavía no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional. 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Siga los pasos de resolución de un error específico (sólo empresas)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Estas instrucciones están pensadas principalmente para clientes de Microsoft Office 365 Plan E. Si es un cliente de Office 365 Plan P, continúe con la siguiente sección,[recopilar más información y buscar ayuda adicional ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information). 
  
Si el usuario no puede iniciar sesión después de haber intentado las sugerencias en la sección anterior, puede hacer resolución de problemas adicional según el tipo de error. La tabla siguiente enumera los mensajes de error más comunes y las causas posibles. La tabla siguiente es procedimientos detallados para resolver cada problema.
  
|**Mensaje de error**|**Causa posible**|**Resolución**|
|:-----|:-----|:-----|
|Dirección de inicio de sesión que no se encuentra  <br/> |Solicitudes de inicio de sesión desde el Asistente Microsoft Online Services Sign-On (msoidsvc.exe) no se van a través del servidor de seguridad externo o servidor proxy.  <br/> |[Agregar una entrada de servidor de seguridad para msoidsvc.exe en su servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Servidor no está disponible temporalmente  <br/> |Si su organización tiene un dominio personalizado, puede ser la configuración necesaria del sistema de nombres de dominio (DNS) falta o es incorrecto.  <br/> |[Actualizar la configuración de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Servidor no está disponible temporalmente  <br/> |Si su organización utiliza el inicio de sesión único con Active Directory Federation Services (ADFS), es posible que haya utilizado un certificado autofirmado de Secure Socket Layer (SSL) en lugar de uno de una entidad de certificación de terceros.  <br/> |[Instalar un certificado SSL de terceros en el servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problema al adquirir un certificado personal necesario para iniciar sesión en  <br/> |Si ya ha eliminado los datos del servidor en caché se utilizaron para iniciar sesión en y sigue apareciendo el error, las credenciales de seguridad del usuario pueden estar dañadas o puede estar bloqueando la autenticación a una carpeta RSA en el equipo del usuario.  <br/> |[Actualizar las credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Un cuadro de diálogo de confianza de certificado aparece cuando un usuario inicia sesión por primera vez.  <br/> |Este cuadro de diálogo aparece si su Skype para Business server aún no aparece en la clave del registro **TrustModelData** . <br/> |[Modificar las claves del registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Usuario no está habilitado para SIP  <br/> |Si su organización tiene una instalación anterior de Microsoft Lync Server 2010 o Microsoft Office Communications Server, que no ha eliminado los usuarios desde el servidor antes de desactivarlo. Como resultado, el atributo **msRTCSIP-UserEnabled** todavía se establece en **FALSE** en servicios de dominio de Active Directory. <br/> |[Actualizar la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Agregar una entrada de servidor de seguridad para msoidsvc.exe en su servidor proxy
<a name="add-a-firewall"> </a>

Este procedimiento es una solución posible para el mensaje de error siguiente: **dirección de inicio de sesión no se encuentra**.
  
 **Nota**: los pasos siguientes asumen que está utilizando Microsoft Forefront Threat Management Gateway (TMG) 2010. Si usted posee una solución de puerta de enlace de la web diferente, utilice la configuración descrita en el paso 4 más abajo.
  
Para crear una entrada de la aplicación para Msoidsvc.exe en Forefront TMG 2010, siga estos pasos:
  
1. En el panel izquierdo de Forefront, haga clic en **redes**.
    
2. Haga clic en la ficha **red** . En la ficha **tareas** en el panel derecho, haga clic en **Configurar opciones de cliente de Forefront TMG**.
    
3. En el cuadro de diálogo **Configuración de cliente de Forefront TMG** , haga clic en **nuevo**.
    
4. En el cuadro de diálogo **Configuración de entrada de la aplicación** , configure las siguientes reglas:
    
|**Aplicación**|**Clave**|**Valor**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deshabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2409256, [que no se puede conectar a Skype para los negocios en línea porque un servidor de seguridad en instalaciones bloquea la conexión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### <a name="update-dns-settings"></a>Actualizar la configuración de DNS
<a name="update-dns-service"> </a>

Si su organización tiene un dominio personalizado, este procedimiento es una solución posible para el siguiente mensaje de error: **servidor no está disponible temporalmente**.
  
- Para obtener información sobre cómo agregar el registro CNAME siguiente a su dominio, póngase en contacto con el registrador de nombres de dominio:
    
  - **Tipo de registro DNS**: CNAME 
    
  - **Nombre**: sip
    
  - **Valor/destino**: sipdir.online.microsoft.com
    
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2566790, [Skype solucionar problemas de configuración de DNS en línea de negocio de Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Instalar un certificado SSL de terceros en el servidor ADFS
<a name="verify-upn-and"> </a>

Para instalar un certificado SSL de terceros en su servidor Active dominio Federation Services (ADFS), siga estos pasos:
  
1. Obtener un certificado SSL de una entidad de certificación de terceros como VeriSign o Thawte.
    
2. Instalar el certificado en el servidor ADFS mediante la consola de administración de ADFS. 
    
### <a name="update-security-credentials"></a>Actualizar las credenciales de seguridad
<a name="update-security-credentials"> </a>

Este procedimiento es una solución posible para el **problema de adquirir un certificado personal necesario para iniciar sesión en**el mensaje de error.
  
Para eliminar posibles problemas de certificado o credencial, primero hay que renovar el certificado del usuario en el Administrador de certificados de Windows. Para ello, siga estos pasos:
  
1. Abra el Administrador de certificados de Windows. Para ello, haga clic en **Inicio**, haga clic en **Ejecutar**, escriba **certmgr.msc**y, a continuación, haga clic en **Aceptar**. 
    
2. Haga doble clic en **Personal**y, a continuación, haga doble clic en **certificados**. 
    
3. Ordenar por la columna **Emitido por** y, a continuación, busque un certificado emitido por el servidor.
    
4. Haga clic en el certificado y, a continuación, haga clic en **Eliminar**. 
    
A continuación, si el usuario está ejecutando Windows 7, quitar las credenciales almacenadas en el Administrador de credenciales de Windows. Para ello, siga estos pasos:
  
1. Haga clic en **Inicio**, haga clic en **Panel de Control**y, a continuación, haga clic en **Administrador de credenciales**. 
    
2. Busque el conjunto de credenciales que se utiliza para conectar con Skype para los negocios en línea. 
    
3. Expanda el conjunto de credenciales y, a continuación, haga clic en **quitar de la caja fuerte**. 
    
4. Iniciar sesión de nuevo y vuelva a escribir las credenciales del usuario.
    
Por último, si el usuario todavía no puede iniciar sesión después de actualizar sus credenciales, intente eliminar la carpeta RSA en el equipo del usuario, ya que podría estar bloqueando la finalización del proceso de autenticación de usuario:
  
1. Iniciar sesión en el equipo del usuario con una cuenta de administrador.
    
2. Si es necesario, active la opción de vista de carpeta **Mostrar archivos ocultos**. 
    
3. Escriba lo siguiente en la barra de direcciones de archivo Explorer: **C:\\Documents and Settings\\nombre de usuario\\datos de la aplicación\\Microsoft\\Crypto\\RSA**, donde ***nombreDeUsuario*** es el nombre de inicio de sesión de Windows.
    
4. Elimine cualquier carpeta que comienza con el nombre **S-1-5-21 -** seguido de una cadena de números.
    
### <a name="modify-trustmodeldata-registry-keys"></a>Modificar las claves del registro TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Cuando un usuario inicia sesión por primera vez, pueden recibir un cuadro de diálogo que contiene algo como lo siguiente: **no se puede comprobar que el servidor es de confianza en la dirección de inicio de sesión. Conectarse de todas formas?** Se trata de una característica de seguridad y no un error. Sin embargo, puede impedir que el cuadro de diálogo aparezca utilizando un objeto de directiva de grupo (GPO) para actualizar los equipos de los usuarios con su nombre de dominio antes de que inicie sesión por primera vez. Para ello, haga lo siguiente:
  
- Crear e implementar un GPO que anexa su Skype para nombre de dominio de negocio — por ejemplo, domainName.contoso.com—to el valor actual de HKEY_LOCAL_MACHINE\\Software\\directivas\\Microsoft\\Communicator\\ TrustModelData.
    
> [!IMPORTANT]
>  Debe *Anexar* el nombre del dominio al valor existente, no tiene que sustituirla.
  
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2531068, [que Skype para el negocio (Lync) no puede comprobar que el servidor es de confianza en la dirección de inicio de sesión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### <a name="update-user-settings-in-active-directory"></a>Actualizar la configuración de usuario en Active Directory
<a name="update-user-settings"> </a>

Si su organización tiene una instalación anterior de Microsoft Lync Server 2010 o Microsoft Office Communications Server, que no ha eliminado los usuarios desde el servidor antes de desactivarlo. Como resultado, el atributo **msRTCSIP-UserEnabled** todavía se establece en **FALSE** en servicios de dominio de Active Directory.
  
Para corregir este problema, siga estos pasos:
  
1. Actualizar el atributo **msRTCSIP-UserEnabled** para todos los usuarios afectados en **TRUE**.
    
2. Vuelva a ejecutar el de Microsoft Online Services-Herramienta de sincronización de directorios (DirSync). Para obtener más información, vea [AIntegrate en sus instalaciones de directorios con Active Directory de Azure](https://technet.microsoft.com/en-us/library/hh967642.aspx). 
    
Para solucionar los errores de inicio de sesión de negocios en línea Skype, iniciar mediante la eliminación de las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir los pasos en función del tipo de error de resolución específica. Si el usuario todavía no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional. 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Utilice el Support Microsoft Guía de solución de problemas
<a name="toc325626447"> </a>

Si le sigue sin poder resolver los problemas de inicio de sesión del usuario, revise las sugerencias de Microsoft Knowledge Base el artículo 2541980, [cómo solucionar problemas de inicio de sesión en Skype para los negocios en línea](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## <a name="collect-more-information-and-seek-additional-help"></a>Recopilar más información y buscar ayuda adicional
<a name="collect-more-information"> </a>

Si ha seguido las instrucciones anteriores y todavía no puede resolver los problemas de inicio de sesión, debe recopilar información adicional y póngase en contacto con soporte técnico. Para ello, siga estos pasos: 
  
1. Obtener los archivos de registro y los detalles del registro de sucesos de Windows en el equipo del usuario. Para obtener instrucciones detalladas, consulte el tema de ayuda para el usuario final [activar los registros de errores en Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Enviar los archivos de registro y la información detallada sobre el error a soporte técnico de Microsoft.
    
Le pedirá que proporcione información de diagnóstico adicional mediante la instalación de Microsoft Online Services diagnóstico y Kit de herramientas de soporte de registro (MOSDAL) en la máquina del usuario afectado. Para obtener más información, vea [utilizar el Kit de herramientas de soporte de MOSDAL](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
Para solucionar los errores de inicio de sesión de negocios en línea Skype, iniciar mediante la eliminación de las causas más comunes de problemas de inicio de sesión. Si es necesario, puede seguir los pasos en función del tipo de error de resolución específica. Si el usuario todavía no puede iniciar sesión, recopilar información adicional y, a continuación, buscar ayuda adicional. 
  
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 