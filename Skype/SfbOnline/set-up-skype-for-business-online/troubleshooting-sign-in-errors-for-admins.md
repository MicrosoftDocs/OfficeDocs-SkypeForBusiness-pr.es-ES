---
title: Solución de problemas de Skype para errores de inicio de sesión empresarial en línea para los administradores
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
description: 'Obtenga información sobre las causas habituales de Skype para errores de inicio de sesión en línea de negocio y de trabajo a través de solucionar estos problemas. '
ms.openlocfilehash: 560b8244cae99d0af2603181d3cf0c2a02c491d5
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501248"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Solución de problemas de Skype para errores de inicio de sesión empresarial en línea para los administradores

Para solucionar problemas de Skype para errores de inicio de sesión de negocio en línea, inicie mediante la eliminación de las causas más comunes de inicio de sesión de dificultad. Si es necesario, a continuación, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no se puede iniciar sesión, recopilar información adicional y, a continuación, busca ayuda adicional. 
  
## <a name="what-do-you-want-to-do"></a>¿Qué acción desea realizar?
<a name="top"> </a>

> [Verificación de las causas habituales de Skype para errores de inicio de sesión de negocio en línea](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [Siga los pasos de la solución para un error específico (solo Enterprise)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [Agregar una entrada de firewall para msoidsvc.exe el servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [Actualización de la configuración de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [Instalar un certificado SSL de terceros en el servidor de ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [Actualizar las credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [Modificar las claves del registro de TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [Actualización de la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [Use el Support Microsoft Guía de solución de problemas](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [Recopilar más información y busca ayuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Verificación de las causas habituales de Skype para errores de inicio de sesión de negocio en línea
<a name="toc323194094"> </a>

Problemas de inicio de sesión de mayoría pueden realizarse a un número reducido de las causas y muchas de ellas son fáciles de corregir. En la tabla siguiente se enumera algunas de las causas comunes de errores de inicio de sesión y algunos pasos que usted o los usuarios pueden realizar para resolverlos conflictos.
  
|**Causa posible**|**Resolución**|
|:-----|:-----|
|Durante el inicio de sesión, aparece un cuadro de diálogo que contiene la frase siguiente: **no se puede comprobar que el servidor es de confianza para la dirección de inicio de sesión. Conectar de todos modos?** <br/> |Compruebe que el nombre de dominio en el cuadro de diálogo es un servidor de confianza en su organización, por ejemplo, **domainName.contoso.com**. Pida al usuario que Active la casilla de verificación **Confiar siempre en este servidor** y, a continuación, haga clic en **Conectar**. <br/> Los clientes de empresa pueden impedir que este mensaje aparezca cuando un usuario inicia sesión por primera vez mediante la modificación del registro de Windows en el equipo de cada usuario. Para obtener información detallada, vea [Modificar TrustModelData registry keys](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Dirección de inicio de sesión escrita incorrectamente, nombre de usuario o contraseña  <br/> | Confirme que el nombre de inicio de sesión del usuario y la contraseña son correctos. <br/>  Compruebe que el nombre del usuario de inicio de sesión tiene el formato siguiente: **bobk@contoso.com**. Esto puede ser diferente del formato que use para iniciar sesión red de su organización.  <br/>  Pida al usuario que intente iniciar sesión de nuevo. <br/> |
|Contraseña olvidado  <br/> |Restablecer la contraseña del usuario y notificar a él o ella de la nueva contraseña temporal.  <br/> |
|No tiene licencia para usar Skype para profesionales en línea  <br/> |Confirme que el usuario está registrado como un Skype para usuarios profesionales en línea. En caso contrario, registre el usuario y, a continuación, pídale al iniciar sesión de nuevo.  <br/> |
|Versión incorrecta de Skype para profesionales Online instalado  <br/> |Este problema se suele estar asociado a un mensaje de error que contenga la frase siguiente: **el servicio de autenticación puede ser incompatible con esta versión del programa**.  <br/> Pida al usuario que la desinstalación y reinstalación de Skype para profesionales en línea desde el Portal de Office 365.  <br/> |
|Cómo adquirir un certificado personal que es necesario para iniciar sesión en el problema  <br/> |Si ha cambiado recientemente la dirección de inicio de sesión del usuario, que es posible que necesitan eliminar datos de inicio de sesión en caché. Pida a los usuarios a cerrar la sesión, haga clic en eliminar mi información de inicio de sesión de vínculo en la pantalla de inicio de sesión y, a continuación, vuelva a intentarlo.  <br/> |
|Configurar un nombre de dominio personalizado, y es posible que los cambios no hayan terminado de propagarse a través del sistema.  <br/> |En primer lugar, asegúrese de que se modificaron los registros del servicio de nombres de dominio (DNS) para reflejar el cambio.  <br/> Si ya ha realizado los cambios DNS necesarios, de aviso al usuario que intente iniciar la sesión más adelante. Los cambios DNS pueden tardar hasta 72 horas para que se reflejen en todo el sistema.  <br/> |
|Sistema de reloj sincronizados con el reloj del servidor  <br/> |Asegúrese de que el controlador de dominio de red está sincronizando con un origen de hora externo confiable. Para obtener información detallada, vea el artículo 816042 de Microsoft Knowledge Base [cómo configurar un servidor horario autorizado en Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |
   
Para solucionar problemas de Skype para errores de inicio de sesión de negocio en línea, inicie mediante la eliminación de las causas más comunes de inicio de sesión de dificultad. Si es necesario, a continuación, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no se puede iniciar sesión, recopilar información adicional y, a continuación, busca ayuda adicional. 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Siga los pasos de la solución para un error específico (solo Enterprise)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Estas instrucciones se destinan principalmente a los clientes de Microsoft Office 365 planear E. Si usted es un cliente de Office 365 planear P, continúe con la sección siguiente,[recopilar más información y busca ayuda adicional ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information). 
  
Si el usuario no puede iniciar sesión después de haber intentado las sugerencias en la sección anterior, a continuación, se puede hacer solución de problemas adicionales en función del tipo de error. En la tabla siguiente se enumera los mensajes de error más comunes y las posibles causas. La tabla siguiente es los procedimientos detallados para solucionar cada problema.
  
|**Mensaje de error**|**Causa posible**|**Resolución**|
|:-----|:-----|:-----|
|Dirección de inicio de sesión que no se ha encontrado  <br/> |Las solicitudes de inicio de sesión desde el Asistente Microsoft Online Services Sign-On (msoidsvc.exe) no se van a través del firewall externo, o el servidor proxy.  <br/> |[Agregar una entrada de firewall para msoidsvc.exe el servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Servidor no está disponible temporalmente  <br/> |Si su organización tiene un dominio personalizado, la configuración del sistema de nombres de dominio (DNS) es necesario puede ser incorrectos o que faltan.  <br/> |[Actualización de la configuración de DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Servidor no está disponible temporalmente  <br/> |Si su organización usa el inicio de sesión único con Active Directory Federation Services (ADFS), es posible que ha usado un certificado autofirmado de capa de sockets seguros (SSL) en lugar de uno de una entidad de certificación de terceros.  <br/> |[Instalar un certificado SSL de terceros en el servidor de ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Cómo adquirir un certificado personal que es necesario para iniciar sesión en el problema  <br/> |Si ya ha quitado los datos del servidor en caché se usan para iniciar sesión en y sigue apareciendo el error, credenciales de seguridad del usuario pueden estar dañadas o es posible que esté bloqueando la autenticación a una carpeta de RSA en el equipo del usuario.  <br/> |[Actualizar las credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Un cuadro de diálogo de confianza de certificado aparece cuando un usuario inicia sesión por primera vez.  <br/> |Este cuadro de diálogo aparece si aún no aparece en la clave del registro de **TrustModelData** su Skype para Business server. <br/> |[Modificar las claves del registro de TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Usuario no está habilitado para SIP  <br/> |Si su organización tiene una instalación anterior de Microsoft Office Communications Server o Microsoft Lync Server 2010, es posible que no ha eliminado los usuarios desde el servidor antes de retirarlo. Como resultado, el atributo **msRTCSIP-UserEnabled** aún se establece en **FALSE** en servicios de dominio de Active Directory. <br/> |[Actualización de la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Agregar una entrada de firewall para msoidsvc.exe el servidor proxy
<a name="add-a-firewall"> </a>

Este procedimiento es una solución posible para el siguiente mensaje de error: **dirección de inicio de sesión no se ha encontrado**.

> [!NOTE]
> Los siguientes pasos se suponen que está usando Microsoft Forefront Threat Management Gateway (TMG) 2010. Si tiene una solución de puerta de enlace web diferente, use las opciones que se describen en el paso 4 por debajo.
  
  
Para crear una entrada de la aplicación para Msoidsvc.exe en Forefront TMG 2010, siga estos pasos:
  
1. En el panel izquierdo de Forefront, haga clic en **la red**.
    
2. Haga clic en la ficha **red** . En la ficha **tareas** en el panel derecho, haga clic en **Configurar opciones de cliente de Forefront TMG**.
    
3. En el cuadro de diálogo **Configuración de cliente de Forefront TMG** , haga clic en **nuevo**.
    
4. En el cuadro de diálogo **Configuración de entrada de la aplicación** , configure las siguientes reglas:
    
|**Aplicación**|**Clave**|**Valor**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deshabilitar  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2409256, [que no se puede conectar a Skype para profesionales en línea porque un firewall local bloquea la conexión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### <a name="update-dns-settings"></a>Actualización de la configuración de DNS
<a name="update-dns-service"> </a>

Si su organización tiene un dominio personalizado, este procedimiento es una solución posible para el siguiente mensaje de error: **servidor no está disponible temporalmente**.
  
- Para obtener información sobre cómo agregar el siguiente registro CNAME a su dominio, póngase en contacto con el registrador de nombres de dominio:
    
  - **Tipo de registro DNS**: CNAME 
    
  - **Nombre**: sip
    
  - **Valor/destino**: sipdir.online.microsoft.com
    
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2566790, [Solución de problemas de Skype para problemas de configuración de DNS en línea de negocio en Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Instalar un certificado SSL de terceros en el servidor de ADFS
<a name="verify-upn-and"> </a>

Para instalar un certificado SSL de terceros en el servidor de servicios de federación de dominio Active (ADFS), siga estos pasos:
  
1. Obtención de un certificado SSL de una entidad de certificación de terceros, como VeriSign o Thawte.
    
2. Instalar el certificado en el servidor de ADFS mediante el uso de la consola de administración de ADFS. 
    
### <a name="update-security-credentials"></a>Actualizar las credenciales de seguridad
<a name="update-security-credentials"> </a>

Este procedimiento es una solución posible para el mensaje de error **problema adquirir un certificado personal, debe iniciar sesión**.
  
Para eliminar posibles problemas de certificado o credenciales, en primer lugar renovar el certificado de usuario en el Administrador de certificados de Windows. Para ello, siga estos pasos:
  
1. Abra el Administrador de certificados de Windows. Para ello, haga clic en **Inicio**, haga clic en **Ejecutar**, escriba **certmgr.msc**y, a continuación, haga clic en **Aceptar**. 
    
2. Haga doble clic en **Personal**y, a continuación, haga doble clic en **certificados**. 
    
3. Ordenar por la columna **Emitido por** y, a continuación, busque un certificado emitido por Communications Server.
    
4. Haga clic en el certificado y, a continuación, haga clic en **Eliminar**. 
    
A continuación, si el usuario ejecuta Windows 7, quitar sus credenciales almacenadas en el Administrador de credenciales de Windows. Para ello, siga estos pasos:
  
1. Haga clic en **Inicio**, haga clic en **Panel de Control**y, a continuación, haga clic en **Administrador de credenciales**. 
    
2. Busque el conjunto de credenciales que se usa para conectarse a Skype para profesionales en línea. 
    
3. Expanda el conjunto de credenciales y, a continuación, haga clic en **quitar de la cámara**. 
    
4. Iniciar sesión de nuevo y vuelva a escribir las credenciales del usuario.
    
Por último, si el usuario aún no se puede iniciar sesión después de actualizar sus credenciales, intente eliminar la carpeta RSA en el equipo del usuario, debido a que podría estar bloqueando la finalización del proceso de autenticación de usuario:
  
1. Inicie sesión en el equipo del usuario con una cuenta de administrador.
    
2. Si es necesario, active la opción de vista de la carpeta **Mostrar archivos ocultos**. 
    
3. Escriba lo siguiente en la barra de direcciones de archivo Explorer: **C:\\Documents and Settings\\nombre de usuario\\datos de la aplicación\\Microsoft\\criptográfico de\\RSA**, donde el ***nombre de usuario*** es el nombre de inicio de sesión de Windows.
    
4. Eliminar cualquier carpeta que comienza con el nombre **S-1-5-21 -** seguido de una cadena de números.
    
### <a name="modify-trustmodeldata-registry-keys"></a>Modificar las claves del registro de TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Cuando un usuario inicia sesión por primera vez, es posible que reciben un cuadro de diálogo que contiene algo parecido a lo siguiente: **no se puede comprobar que el servidor es de confianza para la dirección de inicio de sesión. Conectar de todos modos?** Esto es una característica de seguridad y no un error. Sin embargo, puede impedir que el cuadro de diálogo aparezca mediante el uso de un objeto de directiva de grupo (GPO) para actualizar los equipos de los usuarios con el nombre de dominio antes de iniciar sesión por primera vez. Para ello, haga lo siguiente:
  
- Crear e implementar un GPO que se anexa el Skype para el nombre de dominio de negocio — por ejemplo, domainName.contoso.com—to el valor actual de HKEY_LOCAL_MACHINE\\Software\\directivas\\Microsoft\\Communicator\\ TrustModelData.
    
> [!IMPORTANT]
>  Debe *Anexar* su nombre de dominio para el valor existente, no simplemente reemplazarlo.
  
Para obtener información detallada, vea el artículo de Microsoft Knowledge Base 2531068, [que Skype para la empresa (Lync) no se puede comprobar que el servidor es de confianza para la dirección de inicio de sesión](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### <a name="update-user-settings-in-active-directory"></a>Actualizar la configuración de usuario en Active Directory
<a name="update-user-settings"> </a>

Si su organización tiene una instalación anterior de Microsoft Office Communications Server o Microsoft Lync Server 2010, es posible que no ha eliminado los usuarios desde el servidor antes de retirarlo. Como resultado, el atributo **msRTCSIP-UserEnabled** aún se establece en **FALSE** en servicios de dominio de Active Directory.
  
Para corregir este problema, siga estos pasos:
  
1. Actualizar el atributo **msRTCSIP-UserEnabled** para todos los usuarios afectados en **TRUE**.
    
2. Vuelva a ejecutar la herramienta de sincronización de directorios de Microsoft Online Services (DirSync). Para obtener información detallada, vea [directorios de AIntegrate su local con Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx). 
    
Para solucionar problemas de Skype para errores de inicio de sesión de negocio en línea, inicie mediante la eliminación de las causas más comunes de inicio de sesión de dificultad. Si es necesario, a continuación, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no se puede iniciar sesión, recopilar información adicional y, a continuación, busca ayuda adicional. 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Use el Support Microsoft Guía de solución de problemas
<a name="toc325626447"> </a>

Si está todavía no puede resolver los problemas de inicio de sesión del usuario, revise las sugerencias de Microsoft Knowledge Base el artículo 2541980, [cómo solucionar problemas de inicio de sesión en Skype para profesionales en línea](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## <a name="collect-more-information-and-seek-additional-help"></a>Recopilar más información y busca ayuda adicional
<a name="collect-more-information"> </a>

Si ha seguido las instrucciones anteriores y aún no se puede resolver los problemas de inicio de sesión, debe recopilar información adicional y póngase en contacto con soporte técnico. Para ello, siga estos pasos: 
  
1. Obtener los archivos de registro y los detalles del registro de eventos de Windows desde el equipo del usuario. Para obtener instrucciones detalladas, vea el tema de ayuda para el usuario final [activar los registros de error en Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Enviar los archivos de registro y obtener información detallada sobre el error a soporte técnico de Microsoft.
    
Es posible que se le pida para proporcionar información de diagnóstico adicional mediante la instalación de Microsoft Online Services diagnóstico y herramientas de soporte técnico de registro (MOSDAL) en el equipo del usuario afectado. Para obtener información detallada, vea [con el Kit de herramientas de soporte técnico MOSDAL](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
Para solucionar problemas de Skype para errores de inicio de sesión de negocio en línea, inicie mediante la eliminación de las causas más comunes de inicio de sesión de dificultad. Si es necesario, a continuación, puede seguir pasos en función del tipo de error de resolución específica. Si el usuario aún no se puede iniciar sesión, recopilar información adicional y, a continuación, busca ayuda adicional. 
  
## <a name="related-topics"></a>See also
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 