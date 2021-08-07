---
title: Implementar y configurar la movilidad para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: En este artículo se le guían los pasos para configurar una instalación de Skype Empresarial Server existente para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de Skype Empresarial Server Mobility.
ms.openlocfilehash: 4e2cbb49d74347082bf3db02bba4a01de7f31ca187867b8e95474e88ec01fcbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306042"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implementar y configurar la movilidad para Skype Empresarial Server  
 
En este artículo se le guían los pasos para configurar una instalación de Skype Empresarial Server existente para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de Skype Empresarial Server Mobility.
  
Una vez revisado el artículo [Plan for Mobility for Skype Empresarial Server,](../plan-your-deployment/mobility.md) debe estar listo para continuar con los pasos siguientes para implementar Mobility en su entorno Skype Empresarial Server web. Los pasos son los siguientes (y estamos incluyendo en esta tabla una lista de permisos):
  
|**Fase**|**Permisos**|
|:-----|:-----|
|[Crear registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador local  <br/> |
|[Configurar el proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador local  <br/> |
|[Configurar detección automática para movilidad con implementaciones híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[Probar la implementación de movilidad](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar notificaciones de inserción](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar la directiva de movilidad](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas las secciones siguientes contienen pasos que suponen que ha leído el tema Planeación. If anything's confusing you, feel free to check out the information there.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
## <a name="create-dns-records"></a>Crear registros DNS
<a name="CreateDNSRec"> </a>

Es posible que ya las tenga como parte del entorno Skype Empresarial Server, pero debe crear los siguientes registros para que la detección automática funcione:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo (o público) para admitir usuarios móviles que se conectan desde fuera de la red de la organización.
    
Estos registros pueden ser nombres A (host) o registros CNAME (no es necesario realizar ambos, estamos incluyendo los pasos para todo aquí).
  
### <a name="create-an-internal-dns-cname-record"></a>Crear un registro CNAME dns interno

1. Inicie sesión en un servidor DNS de la red que sea miembro del grupo **Administradores** de dominio o del **grupo DnsAdmins.**
    
2. Haga **clic** en Inicio , Elija  Herramientas administrativas **(es** posible que deba buscarla si no es una opción de la menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo dns.
    
3. En el panel izquierdo de la ventana de la consola, tendrás que ir al dominio que es el hogar  de los servidores front-end de Skype Empresarial Server y expandir las zonas de búsqueda directa allí.
    
4. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (estándar o Enterprise) o grupo(s) front-end.
    
   - Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).
    
5. Una vez que haya observado esto, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **Nuevo alias (CNAME)** en el menú.
    
6. En el **cuadro de texto Nombre de** alias, escriba lyncdiscoverinternal para el nombre de host, para la dirección URL del servicio de detección automática interna.
    
7. En el nombre de dominio completo **(FQDN** para el host de destino), deberá escribir o examinar el FQDN interno de servicios web para el grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 4 anterior. Haga clic en Aceptar cuando se haya escrito esto.
    
8. Deberá crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en el entorno Skype Empresarial Server usuario.
    
### <a name="create-an-external-dns-cname-record"></a>Crear un registro CNAME DNS externo

1. Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público puede usar, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que podrá crear nuevos registros DNS allí.
    
2. En este momento, ya debe existir un dominio SIP para Skype Empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o, de lo contrario, ábrala.
    
3. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (estándar o Enterprise) o grupo(s) front-end.
    
   - Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).
    
4. Una vez que tenga esa información, debe poder seleccionar una opción para crear un **nuevo alias (CNAME).**
    
5. Ahora debería poder escribir un **nombre de alias,** debe escribir lyncdiscover aquí para la dirección URL del servicio de detección automática externa.
    
6. A continuación, debe haber un área para especificar un **FQDN** para el host de destino , este debe ser el FQDN del grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 3 anterior.
    
7. Puede que tenga que guardar aquí, o si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su entorno de Skype Empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.
    
### <a name="create-an-internal-dns-a-record"></a>Crear un registro A de DNS interno

1. Inicie sesión en un servidor DNS de la red que sea miembro del grupo **Administradores** de dominio o del **grupo DnsAdmins.**
    
2. Haga **clic** en Inicio , Elija  Herramientas administrativas **(es** posible que deba buscarla si no es una opción de la menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo dns.
    
3. En el panel izquierdo de la ventana de la consola, tendrás que ir al dominio que es el hogar  de los servidores front-end de Skype Empresarial Server y expandir las zonas de búsqueda directa allí.
    
4. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (estándar o Enterprise) o grupo(s) front-end.
    
   - Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).
    
5. Una vez que haya observado esto, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **Nuevo host (A o AAAA)** en el menú.
    
6. En el **cuadro de** texto Nombre, escriba lyncdiscoverinternal para el nombre de host, para la dirección URL del servicio de detección automática interna.
    
7. En el cuadro de texto Dirección **IP,** escriba la dirección IP interna de servicios web para el grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 4 anterior.
    
8. Cuando esto termine, haga clic **en Agregar host** y, a continuación, haga clic en **Aceptar**.
    
9. Deberá crear nuevos registros A o AAAA de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en el entorno Skype Empresarial Server usuario. Para ello, repita los pasos del 6 al 8 tantas veces como sea necesario.
    
10. Cuando haya terminado, haga clic en **Listo**.
    
### <a name="create-an-external-dns-a-record"></a>Crear un registro A de DNS externo

1. Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público puede usar, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que podrá crear nuevos registros DNS allí.
    
2. En este momento, ya debe existir un dominio SIP para Skype Empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o, de lo contrario, ábrala.
    
3. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (estándar o Enterprise) o grupo(s) front-end.
    
   - Cualquier host A o aaaa registros para un director o grupo de directores (una configuración opcional que puede tener en la implementación).
    
4. Una vez que tenga esa información, debe poder seleccionar una opción para crear un nuevo **host A o AAAA**.
    
5. Ahora debería poder escribir un **nombre,** debe escribir lyncdiscover aquí para la dirección URL del servicio de detección automática externa.
    
6. A continuación, debe haber un área para especificar una dirección **IP,** que tendrá que ser la DIRECCIÓN IP del grupo de servidores front-end (o un solo servidor front-end, o grupo de directores o director), identificado en el paso 3 anterior.
    
7. Puede que tenga que guardar aquí, o si necesita crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para su entorno de Skype Empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype Empresarial Server](../plan-your-deployment/mobility.md) article. Una vez que hayas revisado esto, te haremos un recorrido por lo siguiente:
  
- ¿Necesito certificados nuevos?
    
- Solicitar nuevos certificados de la entidad de certificación (CA).
    
- Actualizar los certificados locales con los reemplazos mediante PowerShell.
    
- Comprobación de los certificados mediante el complemento Certificados en Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>¿Necesito certificados nuevos?

1. En primer lugar, es posible que deba comprobar y ver qué certificados están en su lugar y si tienen o no las entradas que necesita. Para ello, deberá iniciar sesión en su cuenta Skype Empresarial Server una cuenta que sea un administrador local. Es posible que esta cuenta también necesite tener derechos sobre la entidad emisora de certificados (CA), para algunos de estos pasos.
    
2. Abra el Shell Skype Empresarial Server de administración (puede usar la búsqueda para encontrarlo si no lo tiene anclado a la barra de tareas o menú Inicio de tareas).
    
3. Será esencial que sepa qué certificados se han asignado antes de intentar agregar un certificado actualizado. Por lo tanto, en el comando, escriba:
    
   ```powershell
   Get-CsCertificate
   ```

4. La información del paso 3 será única para usted. Debe buscarlo para determinar si tiene un único certificado que se ha asignado para varias cosas o si tiene un certificado diferente asignado para los distintos componentes que los necesitan. El **parámetro Use** le dirá cómo se usa un certificado y el parámetro **Thumbprint** le dirá si es el mismo certificado o varios certificados.
    
5. Si tienes las entradas de SAN recomendadas en nuestra sección Planeación, estás bien. Si no es así, deberá solicitar un nuevo certificado o varios certificados (según la configuración) de la entidad de certificación.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar un nuevo certificado o certificados a la entidad de certificación (CA)

1. Después de comprobar qué entradas de SAN tiene, sabe que tiene un solo certificado **(después** de comprobar los pasos anteriores) y ha aprendido que no tiene todas las entradas que necesita. Es necesario realizar una nueva solicitud de certificado a la entidad de certificación. Abra el Skype Empresarial Server PowerShell:
    
   - Para un SAN de servicio de detección automática que falta (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. Deberá usar el parámetro DomainName en su lugar. Y al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (reemplazar el parámetro -Ca por su propia ruta de acceso de entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. O bien, después de comprobar qué entradas de SAN tiene, encontró que tiene varios certificados que no tienen todas las entradas que necesita.  Es necesario realizar una nueva solicitud de certificado a la entidad de certificación. Abra el Skype Empresarial Server PowerShell:
    
   - Para un SAN de servicio de detección automática que falta (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. Deberá usar el parámetro DomainName en su lugar. Y al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Algunos ejemplos serían (reemplazando el parámetro -Ca por su propia ruta de acceso de entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Una vez que la ca haya generado los nuevos certificados, tendrá que asignarlos.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Asignar certificados mediante Skype Empresarial Server Shell de administración

- En función de lo que encontró en la sección ¿Necesito nuevas certificaciones? anterior, debe ejecutar **una** de las siguientes opciones.
    
  - Si tiene un único certificado para todo (las huellas digitales son idénticas), debe ejecutar esto:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si tiene certificados diferentes para las cosas (las huellas digitales son todas diferentes), ejecute esto en su lugar:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Visualización de certificados en Microsoft Management Console (MMC)

1. Tiene una opción para ver los certificados mediante el complemento Certificados para MMC. Simplemente escriba MMC en la búsqueda y debería mostrarse como una opción de aplicación.
    
2. Para agregar el complemento Certificados, deberá hacer clic en Archivo y, a continuación, agregar o quitar **complemento...** (o el método abreviado **de teclado Ctrl+M** también funcionaría). **Los certificados** serán una opción en el panel izquierdo, selecciónelo y, a continuación, Cuenta de equipo en la ventana emergente y, a continuación, **Siguiente**. 
    
3. Todavía en la ventana emergente, con toda probabilidad lo está haciendo en el equipo que es el hogar de los certificados que necesita ver, así que deje la selección en Equipo **local** si es así. Si está trabajando en un equipo remoto,  cambie el botón de radio a Otro  equipo y, a continuación, escriba el FQDN del equipo o use el botón Examinar para buscar ese equipo a través de AD. Después de seleccionar el equipo, deberá  hacer clic en  Finalizar cuando esté listo y, a continuación, aceptar para agregar el complemento al MMC.
    
4. Expanda la **sección Certificados** en el panel izquierdo de MMC. Expanda también **la carpeta** Personal y, a continuación, **seleccione Certificados**. Esto te permite ver los certificados en este almacén.
    
5. Debe buscar el certificado que desea ver, hacer clic con el botón secundario en él y elegir **Abrir**.
    
    > [!NOTE]
    > ¿Cómo sabe qué certificado es? Debe ser el único certificado asignado a todo para la granja de servidores, o puede tener varios certificados para cosas diferentes, como Default, Internal Web Services, etc., en cuyo caso es posible que deba buscar varios certificados. Varios certificados tendrán la misma huella digital. 
  
6. Una vez que haya llegado a la **vista Certificado,** elija **Detalles**. Esto le permitirá ver el nombre del asunto del certificado al seleccionar **Asunto** y se muestran el nombre de sujeto asignado y las propiedades asociadas.
    
7. También tendrá que comprobar las entradas **de Nombre alternativo** del sujeto. Encontrará una o varias de las siguientes opciones:
    
   - El nombre del grupo de servidores de este grupo o el nombre de servidor único si no es un grupo de servidores.
    
   - Nombre del servidor al que está asignado el certificado.
    
   - Registros de dirección URL simples, normalmente se reúnen y marcan.
    
   - Nombres internos y externos de Servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el Generador de topologías y selecciones de servicios web sobrecargados.
    
   - Si ya está asignado, lyncdiscover.\<sipdomain\> y lyncdiscoverinternal.\<sipdomain\> registros.
    
     Deberá comprobar varios certificados si tiene más de un certificado asignado (compruebe la nota anterior).
    
8. Por lo tanto, si encuentra lyncdiscover.\<sipdomain\> y lyncdiscoverinternal.\<sipdomain\> registros, ya tiene esto configurado. Puede cerrar el MMC.
    
9. Si no están asignados, deberá realizar una nueva solicitud de certificado (descrita anteriormente) o deberá instalarlas después de la solicitud (se recomienda lo siguiente en PowerShell anterior para ello).
    
## <a name="configure-the-reverse-proxy"></a>Configurar el proxy inverso
<a name="ConfigRP"> </a>

Los pasos siguientes no están diseñados para seguirse exactamente. Esto se debe a que en versiones anteriores del producto, le habríamos recorrido, por ejemplo, la configuración de la puerta de enlace de administración de amenazas (TMG) y, si no lo estuviera usando, tendría que trabajar su propia versión desde allí.
  
Microsoft ya no ofrece TMG como producto y, si aún necesita configurarlo, puede ver los pasos de [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility). Pero la siguiente información está pensada para ser más útil en general, incluso si no hay ninguna forma de proporcionar pasos de tutorial específicos para cada proxy inverso que haya.
  
Tenemos que tener en cuenta dos aspectos principales:
  
- ¿Va a realizar la solicitud de detección automática inicial a través de HTTPS (que recomendamos)?
    
  - Si tiene una regla de publicación web, debe modificarla.
    
  - Si aún no tiene una regla de publicación web, debe crearla.
    
- Si está realizando la solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.
    
> [!NOTE]
> **Importante** Un valor de tiempo de espera de proxy es un número que variará de la implementación a la implementación. Debe supervisar la implementación y modificar el valor para la mejor experiencia para los clientes. Es posible que pueda establecer el valor como 200. Si admite clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción de Office 365, que tienen un valor de tiempo de espera de 900. Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar las desconexiones del cliente cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, pero se borran mucho después de que el cliente se haya desconectado. Supervisar y basar lo que es habitual para el entorno es la única forma precisa de determinar la configuración adecuada para este valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar la regla de publicación web existente para el SAN y la dirección URL de detección automática externos

1. Abra la interfaz de proxy inverso.
    
2. Tendrás que buscar la regla de publicación web y elegir la opción Editar (puede estar en un menú o pestaña, según la configuración de proxy inverso).
    
3. Debe haber un área que indica a qué se aplica esta regla de publicación web. Debe modificar esta regla para los sitios entrantes o las solicitudes de sitios. Agregará una **nueva** entrada.
    
4. Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o Guardar **,** según el formato del proxy inverso.
    
5. Es posible que tenga un nuevo certificado que tenga la entrada SAN de detección automática. Esto también debe instalarse y configurarse para su uso según la configuración del proxy inverso. Asegúrese de guardar todo cuando se complete la configuración.
    
6. Si el proxy inverso tiene una **funcionalidad de** prueba, haga uso de ella para asegurarse de que todo funciona correctamente.
    
7. Ahora, es posible que deba repetir estos pasos si tiene un director o un grupo de directores en su entorno (esto significaría que tiene una segunda regla).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Crear una regla de publicación web para la dirección URL de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Tendrás que buscar dónde en la interfaz creas las reglas  de  publicación web y elige la opción Nuevo o Crear (puede estar en un menú o pestaña, según la configuración de proxy inverso). Está buscando la opción para crear una nueva regla de publicación web.
    
3. Normalmente, deberá escribir la siguiente información:
    
   - **Nombre:** el nombre de la regla
    
   - **Acción de** regla: en este caso es una **regla Permitir,** está dejando que algo pase a través del proxy inverso.
    
   - La **regla u opción de** publicación que está eligiendo sería un solo sitio web o **equilibrador de carga.**
    
   - Debe ser **SSL** para el acceso externo, elija esa opción.
    
   - Deberá publicar una ruta de acceso para **la** publicación interna y escribir el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores si tiene uno), un ejemplo sería sfb_pool01.contoso.local.
    
   - Debe escribir _ como la ruta de acceso que se va a publicar, pero también debe reenviar el encabezado **/\\** de host original**.
    
   - Habrá una opción para información o **detalles de nombres** públicos o externos. Este es el lugar donde podrá escribir:
    
   - **Acepte solicitudes,** pero debe ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain> (esta es la dirección URL del servicio de detección automática externa). Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, deberá escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
   - Habrá una opción **Ruta** de acceso y tendrás que escribir **/\\** * aquí.
    
   - Deberá seleccionar una escucha **SSL** con su certificado público actualizado.
    
   - **La delegación de** autenticación debe establecerse **en Sin delegación,** pero se debe permitir la autenticación **directa** de cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta debe ser toda la información que necesita para crear esta regla y permitir que continúe.
    
4. Deberá asegurarse de que se reenvía el encabezado **host** original.
    
5. Los **puertos del** servidor web también tendrán que establecerse, deberá hacer lo siguiente:
    
   - **Redirigir solicitudes al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir solicitudes al puerto SSL** y el número de puerto debe ser **4443**.
    
6. Cuando todo esté configurado, tendrás que guardarlos o aplicarlos y, a continuación, querrás probar la regla.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Crear una regla de publicación web para el puerto 80 (opcional)

1. Abra la interfaz de proxy inverso.
    
2. Tendrás que buscar dónde en la interfaz creas las reglas  de  publicación web y elige la opción Nuevo o Crear (puede estar en un menú o pestaña, según la configuración de proxy inverso). Está buscando la opción para crear una nueva regla de publicación web.
    
3. Normalmente, deberá escribir la siguiente información:
    
   - **Nombre:** el nombre de la regla
    
   - **Acción de** regla: en este caso es una **regla Permitir,** está dejando que algo pase a través del proxy inverso.
    
   - La **regla u opción de** publicación que está eligiendo sería un solo sitio web o **equilibrador de carga.**
    
   - Debe ser una conexión no protegida para conectarse al servidor web o granja de servidores **publicados.**
    
   - Tendrá que publicar una ruta de acceso para **la** publicación interna y escribir el FQDN de la dirección **VIP** del equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01.contoso.local.
    
   - Debe escribir _ como la ruta de acceso que se va a publicar, pero también debe reenviar el encabezado **/\\** de host original**.
    
   - Habrá una opción para información o **detalles de nombres** públicos o externos. Este es el lugar donde podrá escribir:
    
   - **Acepte solicitudes,** pero debe ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain> (esta es la dirección URL del servicio de detección automática externa).
    
   - Habrá una opción **Ruta** de acceso y tendrás que escribir **/\\** * aquí.
    
   - Deberá seleccionar un agente de escucha web o permitir que el proxy inverso cree uno por usted.
    
   - **La delegación de** autenticación debe establecerse **en Sin delegación,** pero no se debe permitir la autenticación **directa** del cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta debe ser toda la información que necesita para crear esta regla y permitir que continúe.
    
4. Los **puertos del** servidor web tendrán que establecerse, deberá hacer lo siguiente:
    
   - **Redirigir solicitudes al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir solicitudes al puerto SSL** y el número de puerto debe ser **4443**.
    
5. Cuando todo esté configurado, tendrás que guardarlos o aplicarlos y, a continuación, querrás probar la regla.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar detección automática para movilidad con implementaciones híbridas
<a name="ConfigAutoD"> </a>

Los entornos híbridos Skype Empresarial Server son entornos que combinan un entorno local y O365. Cuando haya Skype Empresarial Server en un entorno híbrido, el servicio de detección automática debe poder localizar a un usuario de cualquiera de estos entornos.
  
Para que los clientes móviles descubran dónde se encuentra un usuario, el servicio de detección automática debe configurarse con un nuevo localizador uniforme de recursos (URL). Estos pasos son:
  
1. Abra Skype Empresarial Server Shell de administración.
    
2. Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para el entorno Skype Empresarial Server usuario:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. A continuación, aún en la ventana del shell, ejecute:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.
    
## <a name="test-your-mobility-deployment"></a>Probar la implementación de movilidad
<a name="TestMobility"> </a>

Una vez que haya implementado Skype Empresarial Server Mobility Service y Skype Empresarial Server Autodiscover Service, querrá ejecutar una transacción de prueba para asegurarse de que la implementación funciona correctamente. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear, unirse y comunicarse en una conferencia. Necesitará dos usuarios (reales o de prueba) y sus credenciales completa para realizar esta prueba. Este comando funcionará tanto para clientes Skype Empresarial como para clientes de Lync Server 2013.
  
Para los clientes de Lync Server 2010 en Skype Empresarial Server 2015, deberá ejecutar **Test-CsMcxP2PIM** para probar. Los usuarios de Lync Server 2010 seguirán teniendo que ser usuarios reales o usuarios de prueba predefinidos, y necesitará sus credenciales de contraseña.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Probar conferencias para Skype Empresarial y clientes móviles de Lync 2013

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde **Skype Empresarial Server Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Skype Empresarial Server de administración** (puede escribir el nombre en la búsqueda o ir a Todos los **programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   También es posible establecer credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de esto a continuación.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Probar conferencias para clientes móviles de Lync 2010

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde **Skype Empresarial Server Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Skype Empresarial Server de administración** (puede escribir el nombre en la búsqueda o ir a Todos los **programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   También es posible establecer credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de esto a continuación.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para revisar los procedimientos de comando más adelante, puede consultar [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar notificaciones de inserción
<a name="ConfigPush"> </a>

Las notificaciones push, en forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva. Pero, ¿qué son las notificaciones de inserción? Son alertas de eventos, como una invitación de mensajería instantánea nueva o perdida, o para un correo de voz recibido. El servicio de movilidad de Skype Empresarial Server envía estas notificaciones al servicio de notificaciones de inserción de Skype Empresarial Server basado en la nube, que envía las notificaciones al Servicio de notificaciones de inserción de Microsoft (MSNS) para Windows Phone usuarios.
  
Esta funcionalidad no cambia respecto a Lync Server 2013, pero si tiene un Skype Empresarial Server, querrá hacer lo siguiente:
  
- Para un servidor perimetral Skype Empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype Empresarial Online y, a continuación, configure la federación de proveedores de hospedaje entre su organización y Skype Empresarial Online.
    
- Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration.** De manera predeterminada, las notificaciones de inserción están desactivadas.
    
- Pruebe la configuración de federación y las notificaciones de inserción.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar el servidor perimetral Skype Empresarial para notificaciones de inserción

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Agregue un Skype Empresarial Server de hospedaje en línea.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por ejemplo:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > No puede tener más de una relación de federación con un único proveedor de hospedaje. Por lo tanto, si ya ha configurado un proveedor de hospedaje que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, incluso si la identidad del proveedor de hospedaje es otra que SkypeOnline. 
  
4. Configure la federación de proveedores de hospedaje entre su organización y el servicio de notificaciones de inserción en Skype Empresarial Online. En la línea de comandos, deberá escribir:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificaciones de inserción

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Habilitar notificaciones de inserción:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilitar federación:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Notificaciones de inserción y federación de pruebas

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Probar la configuración de federación:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Por ejemplo:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Pruebe las notificaciones de inserción:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Por ejemplo:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurar la directiva de movilidad
<a name="ConfigMob"> </a>

Tiene la capacidad de Skype Empresarial Server para determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, así como si se requiere WiFi para VoIP o vídeo. Llamar a través del trabajo permite a un usuario móvil usar su número de teléfono de trabajo, en lugar de su número de teléfono móvil, al realizar y recibir llamadas. La persona del otro extremo de la línea no verá el número de teléfono móvil de ese usuario móvil y le permite evitar los cargos por llamadas salientes. Cuando se configura VoIP y vídeo, los usuarios pueden realizar y realizar llamadas VoIP y vídeo. La configuración del uso de WiFi determina si el dispositivo móvil de un usuario tendrá que usar una red WiFi a través de una red de datos móviles.
  
La movilidad, la llamada a través del trabajo y las características VoIP y vídeo están habilitadas de forma predeterminada. La configuración para requerir WiFi para VoIP y vídeo está deshabilitada. Un administrador tiene la capacidad de cambiar esto, ya sea globalmente, por sitio o por usuario.
  
Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben ser:
  
- Habilitado para Skype Empresarial Server
    
- Habilitado para Telefonía IP empresarial.
    
- Se asignó una directiva de movilidad que tiene **la opción EnableMobility** establecida en **True**.
    
Para que los usuarios puedan usar La llamada a través del trabajo, también deben ser:
  
- Se asignó una directiva de voz que tiene seleccionada la opción Habilitar **llamadas simultáneas de** teléfonos.
    
- Se asignó una directiva de movilidad que **tiene el enableOutsideVoice** establecido en **True**.
    
> [!NOTE]
> Los usuarios que no están habilitados para Telefonía IP empresarial pueden usar sus dispositivos móviles para hacer Skype Skype llamadas VoIP o pueden unirse a conferencias mediante el vínculo Hacer clic para unirse mientras están en sus dispositivos móviles, si se establecen las opciones adecuadas para la directiva de voz a la que están asociados. Hay más detalles en el tema PLANNING. 
  
### <a name="modify-global-mobility-policy"></a>Modificar la directiva global de movilidad

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Desactiva el acceso a Movilidad y Llamar a través del trabajo globalmente escribiendo:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Puedes desactivar La llamada a través del trabajo sin desactivar el acceso a Movilidad. Pero no puedes desactivar Movilidad sin desactivar la llamada a través del trabajo. 
  
    Para obtener más información, [consulte Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar la directiva de movilidad por sitio

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP y Requerir WiFi para vídeo IP por sitio. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Obtenga más información [en New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar la directiva de movilidad por usuario

1. Inicie sesión, con una cuenta que sea miembro del rol **CsAdministrator,** en un equipo donde Skype Empresarial Server **Shell** de administración y **Ocscore** estén instalados.
    
2. Inicie el **Shell Skype Empresarial Server administración**.
    
3. Cree directivas de movilidad de nivel de usuario y desactive Movilidad y Llamar a través del trabajo por usuario. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Otro ejemplo con datos de ejemplo:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Puedes desactivar La llamada a través del trabajo sin desactivar el acceso a Movilidad. Pero no puedes desactivar Movilidad sin desactivar la llamada a través del trabajo. 
