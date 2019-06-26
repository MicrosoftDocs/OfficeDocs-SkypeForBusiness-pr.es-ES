---
title: Solucionar problemas de inicio de sesión en Skype Empresarial Online para administradores
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Setup
description: 'Obtenga información sobre causas comunes de error en el inicio de sesión en Skype Empresarial Online y la forma de solucionar estos problemas. '
ms.openlocfilehash: 397e899796184274ca357e40e070e7c92cf23b66
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221495"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Solucionar problemas de inicio de sesión en Skype Empresarial Online para administradores

Para solucionar errores durante el inicio de sesión en Skype Empresarial Online, empiece por eliminar las causas más frecuentes de dificultades durante el inicio de sesión. Si es necesario, puede seguir pasos específicos de solución, según el tipo de error. Si, aún así, el usuario no puede iniciar sesión, recopile más información y busque más ayuda.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?
<a name="top"> </a>

> [Buscar las causas comunes de errores de inicio de sesión de Skype Empresarial Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Seguir pasos de solución para un error específico (solo empresas)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Agregar una entrada de firewall para msoidsvc.exe en su servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Actualizar la configuración DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Instalar un certificado SSL de un tercero en su servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Actualizar credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Modificar las claves de registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Actualizar la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Usar la guía de solución de problemas del Soporte técnico de Microsoft](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Recopilar más información y buscar ayuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Buscar las causas comunes de errores de inicio de sesión de Skype Empresarial Online
<a name="toc323194094"> </a>

La mayoría de los problemas de inicio de sesión pueden resumirse en unas pocas causas, y muchas de estas son fáciles de corregir. En la siguiente tabla, se enumeran algunas causas comunes de los errores que se producen durante el inicio de sesión y algunos pasos que usted o los usuarios pueden seguir para resolverlas.


| **Causa posible**                                                                                                                                                    | **Resolución**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Durante el inicio de sesión, aparece un cuadro de diálogo con la siguiente frase: **no se puede verificar si el servidor es de confianza para su dirección de inicio de sesión. ¿Quiere conectarse de todas formas?** <br/> | Compruebe que el nombre de dominio en el cuadro de diálogo es un servidor de confianza de la organización, por ejemplo, **domainName.contoso.com**. Pida al usuario que seleccione la casilla **Confiar siempre en este servidor** y haga clic en **Conectar**. <br/> Los clientes empresariales pueden evitar que aparezca este mensaje cuando un usuario inicia sesión por primera vez modificando el registro de Windows en el equipo de cada usuario. Para obtener detalles, consulte [Modificar las claves de registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Error en la escritura de la dirección de inicio de sesión, nombre de usuario o contraseña  <br/>                                                                                                               | Confirme que el nombre de inicio de sesión y la contraseña del usuario sean correctos. <br/>  Compruebe que el nombre de inicio de sesión del usuario tenga el siguiente formato: <strong>bobk@contoso.com</strong>. Este puede ser diferente al formato que usó para iniciar sesión en la red de su organización.  <br/>  Pídale al usuario que vuelva a intentar iniciar sesión. <br/>                                                                                                                                                                                                                             |
| Olvido de la contraseña  <br/>                                                                                                                                             | Restablezca la contraseña del usuario e infórmele de la nueva contraseña temporal.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| No tiene licencia para usar Skype Empresarial Online  <br/>                                                                                                                  | Confirme que el usuario está registrado en Skype Empresarial Online. Si no lo está, registre al usuario y pídale que vuelva a intentar iniciar sesión.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Versión instalada de Skype Empresarial Online incorrecta  <br/>                                                                                                           | En general, este problema se asocia a un mensaje de error que contiene la siguiente frase: **es posible que el servicio de autenticación no sea compatible con esta versión del programa**.  <br/> Pídale al usuario que desinstale y vuelva a instalar Skype Empresarial Online desde el portal de Office 365.  <br/>                                                                                                                                                                                                                                                    |
| Problema para adquirir un certificado personal obligatorio para iniciar sesión  <br/>                                                                                           | Si la dirección de inicio de sesión del usuario se ha modificado recientemente, puede que sea necesario eliminar los datos de inicio de sesión almacenados en caché. Pida a los usuarios que cierren sesión y hagan clic en el vínculo Borrar mi información de inicio de sesión que aparece en la pantalla y que vuelvan a intentarlo.  <br/>                                                                                                                                                                                                                                                                                                                                |
| Estableció un nombre de dominio personalizado y es posible que los cambios no hayan terminado de propagarse en el sistema.  <br/>                                                         | Primero, asegúrese de haber modificado los registros del Servicio de nombre de dominio (DNS) para reflejar el cambio.  <br/> Si ya hizo los cambios necesarios en el DNS, recomiende al usuario que intente iniciar sesión más tarde. Los cambios en el DNS pueden tardar hasta 72 horas en verse reflejados en el sistema.  <br/>                                                                                                                                                                                                                                                        |
| Reloj del sistema no sincronizado con el reloj del servidor  <br/>                                                                                                                     | Asegúrese de que el controlador de dominio de su red se esté sincronizando con un origen de hora externo confiable. Para obtener detalles, consulte el artículo 816042 de Microsoft Knowledge Base, [Cómo configurar un servidor de tiempo autoritativo en Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Para solucionar errores durante el inicio de sesión en Skype Empresarial Online, empiece por eliminar las causas más frecuentes de dificultades durante el inicio de sesión. Si es necesario, puede seguir pasos específicos de solución, según el tipo de error. Si, aún así, el usuario no puede iniciar sesión, recopile más información y busque más ayuda.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Seguir pasos de solución para un error específico (solo empresas)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Estas instrucciones se crearon para los clientes de Microsoft Office 365 Plan E. Si es cliente de Office 365 Plan P, pase a la sección siguiente, [Recopilar más información y buscar ayuda adicional](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Si ya probó las sugerencias de la sección anterior y el usuario todavía no puede iniciar sesión, puede seguir intentando solucionar el problema, según el tipo de error. En la siguiente tabla se enumeran los mensajes de error más frecuentes y las causas posibles. Después de la tabla se detallan los procedimientos para tratar cada problema.

|**Mensaje de error**|**Causa posible**|**Resolución**|
|:-----|:-----|:-----|
|No se encontró la dirección de inicio de sesión  <br/> |Las solicitudes de inicio de sesión del Asistente de inicio de sesión de Microsoft Online Services (msoidsvc.exe) no están atravesando su firewall externo o servidor proxy.  <br/> |[Agregar una entrada de firewall para msoidsvc.exe en su servidor proxy](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|El servidor no está disponible temporalmente  <br/> |Si su organización tiene un dominio personalizado, es posible que falten las configuraciones necesarias para el Sistema de nombre de dominio (DNS) o que sean incorrectas.   <br/> |[Actualizar la configuración DNS](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|El servidor no está disponible temporalmente  <br/> |Si su organización está utilizando inicio de sesión único con Servicios de federación de Active Directory (AD FS), es posible que haya usado un certificado de Capa de sockets seguros (SSL) autofirmado en lugar de un certificado de una entidad de certificación externa.   <br/> |[Instalar un certificado SSL de un tercero en su servidor ADFS](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problema para adquirir un certificado personal obligatorio para iniciar sesión  <br/> |Si ya eliminó los datos del servidor almacenados en caché usados para iniciar sesión, pero el error sigue apareciendo, es posible que las credenciales de seguridad del usuario estén dañadas o que una carpeta RSA del equipo del usuario esté bloqueando la autenticación.  <br/> |[Actualizar credenciales de seguridad](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Cuando un usuario inicia sesión por primera vez, aparece un cuadro de diálogo del certificado de confianza.  <br/> |Este cuadro de diálogo aparece si su servidor de Skype Empresarial todavía no aparece en la lista de la clave de registro **TrustModelData**. <br/> |[Modificar las claves de registro TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|El usuario no tiene habilitación para SIP  <br/> |Si se hizo una instalación previa de Microsoft Office Communications Server o Microsoft Lync Server 2010 en su organización, es posible que no haya eliminado a sus usuarios del servidor antes de desinstalar el software. Como consecuencia, el atributo **msRTCSIP-UserEnabled** todavía está establecido como **FALSE** en los servicios de dominio de Active Directory. <br/> |[Actualizar la configuración de usuario en Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Agregue una entrada de firewall para msoidsvc.exe en su servidor proxy
<a name="add-a-firewall"> </a>

Este procedimiento es una solución posible para el siguiente mensaje de error: **No se encontró la dirección de inicio de sesión**.

> [!NOTE]
> En los pasos que siguen se asume que está usando Microsoft Forefront Threat Management Gateway (TMG) 2010. Si tiene otra solución para puerta de enlace web, use las configuraciones que se describen en el paso 4, a continuación.


Para crear una entrada de aplicación para Msoidsvc.exe en Forefront TMG 2010, siga estos pasos:

1. En el panel izquierdo de Forefront, haga clic en **Conexión de red**.

2. Haga clic en la pestaña **Red**. En la pestaña **Tareas** del panel derecho, haga clic en **Establecer la configuración de cliente de Forefront TMG**.

3. En el cuadro de diálogo **Configuración de cliente de Forefront TMG**, haga clic en **Nuevo**.

4. En el cuadro de diálogo **Configuración de entrada de la aplicación**, configure las siguientes reglas:

|**Aplicación**|**Clave**|**Valor**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Para obtener detalles, consulte el artículo 2409256 de Microsoft Knowledge Base, [No puede conectarse a Skype Empresarial Online porque un firewall local bloquea la conexión](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Actualizar la configuración DNS
<a name="update-dns-service"> </a>

Si su organización tiene un dominio personalizado, este procedimiento es una solución posible para el siguiente mensaje de error: **El servidor no está disponible temporalmente**.

- Póngase en contacto con el registrador de su nombre de dominio para obtener información sobre cómo agregar el siguiente registro CNAME a su dominio:

  - **Tipo de registro DNS**: CNAME

  - **Nombre**: sip

  - **Valor/Destino**: sipdir.online.lync.com

Para obtener detalles, consulte el artículo 2566790 de Microsoft Knowledge Base, [Solucionar problemas de configuración DNS de Skype Empresarial Online en Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Instale un certificado SSL de un tercero en su servidor ADFS
<a name="verify-upn-and"> </a>

Para instalar un certificado SSL de un tercero en su servidor de Servicios de Federación de Active Domain (ADFS), siga estos pasos:

1. Obtenga un certificado SSL de una entidad de certificación externa como VeriSign o Thawte.

2. Instale el certificado en su servidor ADFS con la consola de administración de ADFS.

### <a name="update-security-credentials"></a>Actualizar credenciales de seguridad
<a name="update-security-credentials"> </a>

Este procedimiento representa una solución posible para el mensaje de error **Problemas para adquirir un certificado personal obligatorio para iniciar sesión**.

Para eliminar los posibles problemas con los certificados o credenciales, primero debe renovar el certificado del usuario en Windows Certificate Manager. Para ello, siga estos pasos:

1. Abra Windows Certificate Manager. Para hacerlo, haga clic en **Inicio**, **Ejecutar**, escriba **certmgr.msc** y haga clic en **Aceptar**. 

2. Haga doble clic en **Personal** y en **Certificados**.

3. Ordene por la columna **Emitido por** y busque un certificado que haya emitido Communications Server.

4. Haga clic con el botón secundario sobre el certificado y luego haga clic en **Eliminar**. 

Después, si el usuario está usando Windows 7, elimine las credenciales almacenadas en al administrador de credenciales de Windows. Para ello, siga estos pasos:

1. Haga clic en **Inicio**, **Panel de control** y en **Administrador de credenciales**.

2. Busque el conjunto de credenciales que se usa para conectarse a Skype Empresarial Online.

3. Expanda el conjunto de credenciales y haga clic en **Quitar del almacén**.

4. Vuelva a iniciar sesión e introduzca de nuevo las credenciales del usuario.

Por último, si ya actualizó las credenciales, pero el usuario todavía no puede iniciar sesión, intente eliminar la carpeta RSA del equipo del usuario, ya que podría estar bloqueando el proceso de autenticación:

1. Inicie sesión en el equipo del usuario mediante una cuenta de administrador.

2. Si es necesario, active la opción de vista de carpeta **Mostrar archivos ocultos**.

3. Escriba lo siguiente en la barra de direcciones del explorador de archivos: **C:\\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**, donde ***UserName*** es su nombre de inicio de sesión de Windows.

4. Elimine todas las carpetas que empiecen con el nombre **S-1-5-21-** seguido de una cadena de números.

### <a name="modify-trustmodeldata-registry-keys"></a>Modifique las claves de registro TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Cuando un usuario inicia sesión por primera vez, es posible que le aparezca un cuadro de diálogo que contenga algo como lo siguiente: **No se puede verificar si el servidor es de confianza para su dirección de inicio de sesión. ¿Quiere conectarse de todas formas?** Esta es una función de seguridad y no un error. Sin embargo, puede evitar que aparezca el cuadro de diálogo usando un Objeto de directiva de grupo (GPO) para actualizar los equipos de los usuarios con su nombre de dominio antes de que inicien sesión por primera vez. Para esto, haga lo siguiente:

- Cree e implemente un GPO que se anexe a su nombre de dominio de Skype Empresarial Online, por ejemplo, domainName.contoso.com, en el valor actual de HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData.

> [!IMPORTANT]
>  Debe *anexar* el nombre de su dominio al valor existente, no solo sustituirlo.

Para obtener detalles, consulte el artículo 2531068 de Microsoft Knowledge Base, [Skype Empresarial (Lync) no puede verificar si el servidor es de confianza para su dirección de inicio de sesión](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Actualizar la configuración de usuario en Active Directory
<a name="update-user-settings"> </a>

Si se hizo una instalación previa de Microsoft Office Communications Server o Microsoft Lync Server 2010 en su organización, es posible que no haya eliminado a sus usuarios del servidor antes de desinstalar el software. Como consecuencia, el atributo **msRTCSIP-UserEnabled** todavía está establecido como **FALSE** en los servicios de dominio de Active Directory.

Para solucionar este problema, siga estos pasos:

1. Establezca el atributo **msRTCSIP-UserEnabled** en todos los usuarios afectados como **TRUE**. 

2. Vuelva a ejecutar la Herramienta de sincronización de directorios (DirSync) de Microsoft Online Services. Para más información, vea [Integración de los directorios locales con Azure Active Directory](https://technet.microsoft.com/es-ES/library/hh967642.aspx) 

Para solucionar errores durante el inicio de sesión en Skype Empresarial Online, empiece por eliminar las causas más frecuentes de dificultades durante el inicio de sesión. Si es necesario, puede seguir pasos específicos de solución, según el tipo de error. Si, aún así, el usuario no puede iniciar sesión, recopile más información y busque más ayuda.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Usar la guía de solución de problemas del Soporte técnico de Microsoft
<a name="toc325626447"> </a>

Si todavía no puede resolver los problemas de inicio de sesión del usuario, revise las sugerencias del artículo 2541980 de Microsoft Knowledge Base, [Cómo solucionar problemas de inicio de sesión en Skype Empresarial Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Recopilar más información y buscar ayuda adicional
<a name="collect-more-information"> </a>

Si siguió las instrucciones anteriores y, aún así, no puede resolver los problemas de inicio de sesión, debe recopilar más información y ponerse en contacto con el soporte técnico. Para ello, siga estos pasos:

1. Obtenga los archivos de registro y los detalles de registros de eventos de Windows del equipo del usuario. Para obtener instrucciones paso a paso, consulte el tema de ayuda para el usuario final [Activar los registros de errores en Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Envíe los archivos de registro y la información detallada sobre el error al equipo de soporte técnico de Microsoft.

Es posible que le pidan que envíe más información de diagnóstico, mediante la instalación del Kit de herramientas de soporte de registro y diagnóstico de Microsoft Online Services (MOSDAL) en el equipo del usuario afectado. Para obtener detalles, consulte [Cómo usar el Kit de herramientas de soporte MOSDAL](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Para solucionar errores durante el inicio de sesión en Skype Empresarial Online, empiece por eliminar las causas más frecuentes de dificultades durante el inicio de sesión. Si es necesario, puede seguir pasos específicos de solución, según el tipo de error. Si, aún así, el usuario no puede iniciar sesión, recopile más información y busque más ayuda.

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md)


