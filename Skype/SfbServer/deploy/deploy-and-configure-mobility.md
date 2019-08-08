---
title: Implementar y configurar la movilidad en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará a través de los pasos para configurar una instalación existente de Skype empresarial Server con el fin de usar el servicio de movilidad, de modo que sus dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234579"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implementar y configurar la movilidad en Skype empresarial Server  
 
Este artículo le guiará a través de los pasos para configurar una instalación existente de Skype empresarial Server con el fin de usar el servicio de movilidad, de modo que sus dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
  
Una vez que haya revisado el [plan de movilidad de Skype empresarial Server](../plan-your-deployment/mobility.md) , debe estar listo para continuar con los pasos siguientes para implementar la movilidad en su entorno de Skype empresarial Server. Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):
  
|**Fase**|**Permisos**|
|:-----|:-----|
|[Crear registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Administradores de dominio  <br/> DnsAdmins  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador local  <br/> |
|[Configurar el proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador local  <br/> |
|[Configurar la detección automática para movilidad con implementaciones híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Administradores de dominio  <br/> |
|[Probar la implementación de la movilidad](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar notificaciones de inserción](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar la directiva de movilidad](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas las secciones siguientes contienen pasos que dan por sentado que ha leído el tema sobre planificación. Si algo le resulta confuso, consulte la información contenida en dicho tema.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
## <a name="create-dns-records"></a>Crear registros de DNS
<a name="CreateDNSRec"> </a>

Es posible que ya tenga estas como parte de su entorno de Skype empresarial Server, pero es necesario crear los siguientes registros para que funcione AutoDiscovery:
  
- Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.
    
Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).
  
### <a name="create-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que está en el hogar de los servidores front-end de Skype empresarial Server y expandir allí las **zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.
    
   - Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.
    
6. En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el **nombre de dominio completo (FQDN para el host de destino**, tendrá que escribir o examinar el FQDN de los servicios Web internos de su grupo de servidores front-end (o un único servidor front-end, o director o director), identificado en el paso 4 anterior. Haga clic en Aceptar cuando ya lo haya introducido.
    
8. Tendrá que crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP admitido en su entorno de Skype empresarial Server.
    
### <a name="create-an-external-dns-cname-record"></a>Crear un registro CNAME de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, ya debería existir un dominio SIP en Skype empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.
    
   - Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.
    
5. Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área para especificar en un **FQDN para el host de destino**, lo cual deberá ser el FQDN para el grupo de servidores front-end (o un único servidor frontal o director o director), identificado en el paso 3 anterior.
    
7. Es posible que tenga que guardarlos aquí o, si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en el entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.
    
### <a name="create-an-internal-dns-a-record"></a>Crear un registro A de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio que está en el hogar de los servidores front-end de Skype empresarial Server y expandir allí las **zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.
    
   - Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.
    
6. En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el cuadro de texto **dirección IP** , escriba la dirección IP de los servicios Web internos para el grupo de servidores front-end (o un solo servidor front-end o un grupo de directores o director) identificada en el paso 4 anterior.
    
8. Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.
    
9. Tendrá que crear nuevos registros A o AAAA de Autodiscover en la zona de búsqueda directa de cada dominio SIP que se admita en su entorno de Skype empresarial Server. Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.
    
10. Cuando haya terminado, haga clic en **Listo**.
    
### <a name="create-an-external-dns-a-record"></a>Crear un registro A de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, ya debería existir un dominio SIP en Skype empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier registro de host A o AAAA para el servidor front-end (Standard o Enterprise) o grupos front-end.
    
   - Cualquier registro A o AAAA de un director o un grupo de directores (una configuración opcional que puede tener en su implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.
    
5. Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área para escribir en una **dirección IP**, lo cual tendrá que ser la dirección IP del grupo de servidores front-end (o un único servidor front-end o un director o director) identificada en el paso 3 anterior.
    
7. Es posible que tenga que guardarla aquí o, si necesita crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para el entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Si tiene preguntas sobre cómo planear los certificados, nos hemos documentado en el artículo sobre el [plan de movilidad para Skype empresarial Server](../plan-your-deployment/mobility.md) . Cuando lo revise, le guiaremos por los siguientes temas:
  
- ¿Necesito certificados nuevos?
    
- Solicitud de nuevos certificados de su entidad de certificación (CA).
    
- Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.
    
- Comprobar los certificados con el complemento certificados en Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>¿Necesito certificados nuevos?

1. Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita. Para ello, tendrá que iniciar sesión en su servidor de Skype empresarial con una cuenta que sea un administrador local. Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).
    
2. Abra el shell de administración de Skype empresarial Server (puede usar buscar para encontrarlo si no está anclado al menú Inicio o a la barra de tareas).
    
3. Te va a resultar esencial saber qué certificados se han asignado antes de intentar agregar uno actualizado. Por ello, en el comando, escriba:
    
   ```
   Get-CsCertificate
   ```

4. La información del paso 3 será exclusiva para usted. Tiene que analizarla para determinar si cuenta con un certificado único asignado a varias cosas o si tiene un certificado distinto asignado a cada uno de los diferentes componentes que lo necesitan. El parámetro **Use** le indicará cómo se ha estado usando un certificado, mientras que el parámetro **Thumbprint** le indicará si se trata del mismo certificado o de varios.
    
5. Si tiene las entradas SAN recomendadas en nuestra sección Planificación, está en el camino correcto. En caso contrario, tendrá que solicitar un certificado nuevo o varios certificados (según su configuración) a la entidad de certificación.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar uno o varios certificados nuevos a una entidad de certificación (CA)

1. Después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene un **único certificado** (mediante los pasos anteriores) y sabrá que no tiene todas las entradas que necesita. En ese caso, se debe solicitar a la CA un nuevo certificado. Abra el PowerShell de Skype empresarial Server:
    
   - En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En su lugar, tendrá que usar el parámetro DomainName. Y cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (reemplazar el parámetro-CA por su propia ruta de acceso de la entidad emisora de certificados):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita. Si es así, se debe solicitar a la CA un nuevo certificado. Abra el PowerShell de Skype empresarial Server:
    
   - En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En su lugar, tendrá que usar el parámetro DomainName. Y cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Los ejemplos serían reemplazar el parámetro-CA por su propia ruta de acceso de la entidad emisora de certificados:
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Cuando la CA haya generado los nuevos certificados, tendrá que asignarlos.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Asignar certificados usando el Shell de administración de Skype Empresarial Server

- Según qué haya encontrado en la sección anterior relativa a si necesita certificados nuevos, tendrá que ejecutar **uno** de los siguientes comandos.
    
  - Si tiene un solo certificado para todo (las huellas digitales son idénticas), tiene que ejecutar lo siguiente:
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si tiene diferentes certificados (las huellas digitales son todas diferentes), ejecute lo siguiente:
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Ver certificados en Microsoft Management Console (MMC)

1. Tiene la opción de mirar los certificados con el complemento Certificados para MMC. Solo tiene que escribir MMC en el cuadro de búsqueda y aparecerá como una opción de aplicación.
    
2. Para agregar el complemento Certificados, debe hacer clic en **Archivo** y después en **Agregar o quitar complemento...** (o el método abreviado de teclado **Ctrl+M** también funcionará). **Certificados** será una de las opciones en el panel izquierdo. Selecciónela y, a continuación, seleccione **Cuenta de equipo** en la ventana emergente y **Siguiente**.
    
3. Aún en la ventana emergente, en todas las probabilidades está haciendo esto en el equipo que está en el hogar con los certificados que necesita consultar, así que deje la selección en el **equipo local** si es así. Si está trabajando en un equipo remoto, cambie el botón de radio a **otro equipo** y, a continuación, escriba el FQDN de ese equipo o use el botón **examinar** para buscar ese equipo a través de ad. Después de seleccionar el equipo, tendrá que hacer clic en **Finalizar** cuando esté listo y, después, en **Aceptar** para agregar el complemento a MMC.
    
4. Expanda la sección **certificados** en el panel izquierdo de MMC. Expanda la carpeta **Personal** también y seleccione **Certificados**. Esto le permitirá ver los certificados de esta tienda.
    
5. Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.
    
    > [!NOTE]
    > ¿Cómo puede saber qué certificado es? Debe ser el único certificado asignado a cada una de las granjas de servidores o puede tener varios certificados para diferentes aspectos, como predeterminado, servicios Web internos, etc., en cuyo caso es posible que tenga que consultar varios certificados. Varios certificados tendrán la misma huella digital. 
  
6. Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.
    
7. También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:
    
   - El nombre del grupo para este grupo o el nombre de servidor único si no se trata de un grupo.
    
   - Nombre del servidor al que está asignado el certificado.
    
   - Registros de direcciones URL simples, normalmente de reunión y marcación.
    
   - Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.
    
   - Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
     Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).
    
8. Por lo tanto, si encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ya tienes configurado. Puede cerrar MMC.
    
9. Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).
    
## <a name="configure-the-reverse-proxy"></a>Configurar el proxy inverso
<a name="ConfigRP"> </a>

No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.
  
Ya no ofrece Microsoft TMG como producto y, si aún necesita configurarlo, puede consultar los [pasos de 2013 de Lync Server](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Sin embargo, la siguiente información es más útil, incluso si no hay forma de que podamos proporcionar pasos de tutoriales específicos para cada proxy inverso.
  
Debemos considerar dos aspectos:
  
- ¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?
    
  - Si tiene una regla de publicación web, debe modificarla.
    
  - Si no tiene una regla de publicación web todavía, debe crearla.
    
- Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.
    
> [!NOTE]
> **Importante** Un valor de tiempo de espera de proxy es un número que variará de una implementación a la de implementación. Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes. Es posible que pueda configurar el valor como mínimo como 200. Si admite clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción en Office 365, que tienen un valor de tiempo de espera de 900. Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar desconexiones de cliente cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, pero no más tiempo después de que el cliente se haya desconectado. La supervisión y la determinación de las características habituales de su entorno es la única forma precisa de determinar la configuración adecuada para este valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Tendrá que ubicar su regla de publicación web y elegir la opción de edición (puede estar en un menú o pestaña, según la configuración del proxy inverso).
    
3. Debe haber un área que indique a qué se aplica esta regla de publicación Web. Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios. Deberá **agregar** una nueva entrada.
    
4. Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del proxy inverso.
    
5. Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática. Además, debe instalarse y configurarse para su uso según la configuración de su proxy inverso. Asegúrese de guardar todo cuando haya completado la configuración.
    
6. Si su proxy inverso tiene una funcionalidad de **prueba** , hágalo para asegurarse de que todo funciona correctamente.
    
7. Ahora, es posible que tenga que repetir estos pasos si tiene un grupo de directores o directores en su entorno (esto significa que tiene una segunda regla).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Crear una regla de publicación web para la dirección URL externa de detección automática

1. Abra la interfaz de proxy inverso.
    
2. Tendrá que localizar en qué lugar de la interfaz crea las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una pestaña, según la configuración del proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **Acción de regla**: en este caso, se trata de una regla de **permiso** que permite que un objeto pase por el proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser **SSL** para acceso interno. Elija esa opción.
    
   - Tendrá que publicar una ruta de acceso para la **publicación interna**e introducir el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores, si tiene uno), un ejemplo sería sfb_ pool01. contoso. local.
    
   - Debe escribir ** / *** como la ruta de acceso que se va a publicar, pero también debe reenviar **el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(esta es la dirección URL externa del servicio de detección automática). Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, tendrá que escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
   - Habrá una opción de **ruta de acceso** y tendrá que escribir ** / *** aquí.
    
   - Tendrá que seleccionar un **agente de escucha SSL** con el certificado público actualizado.
    
   - **Delegación de autenticación** debe establecerse en **Sin delegación**, pero **debe** permitirse la autenticación directa de cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta es toda la información que puede necesitar para crear esta regla y poder continuar.
    
4. Necesitará asegurarse de que se transfiera el **encabezado host original**.
    
5. También será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:
    
   - **Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
6. Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Crear una regla de publicación web para el puerto 80 (opcional)

1. Abra la interfaz de proxy inverso.
    
2. Tendrá que localizar en qué lugar de la interfaz crea las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una pestaña, según la configuración del proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **Acción de regla**: en este caso, se trata de una regla de **permiso** que permite que un objeto pase por el proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.
    
   - Tendrá que publicar una ruta de acceso para la **publicación interna**y especificar el FQDN de la **Dirección VIP** de su equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01. contoso. local.
    
   - Debe escribir ** / *** como la ruta de acceso que se va a publicar, pero también debe reenviar **el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(esta es la dirección URL externa del servicio de detección automática).
    
   - Habrá una opción de **ruta de acceso** y tendrá que escribir ** / *** aquí.
    
   - Tendrá que seleccionar una escucha de web o permitir que su proxy inverso cree una.
    
   - **Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta es toda la información que puede necesitar para crear esta regla y poder continuar.
    
4. Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:
    
   - **Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
5. Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar la detección automática para movilidad con implementaciones híbridas
<a name="ConfigAutoD"> </a>

Los entornos híbridos de Skype empresarial Server son entornos que combinan un entorno local y de O365. Cuando tiene Skype empresarial Server funcionando en un entorno híbrido, el servicio de detección automática debe poder localizar a un usuario de cualquiera de estos entornos.
  
Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:
  
1. Abra el shell de administración de Skype empresarial Server.
    
2. Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para su entorno de Skype empresarial Server:
    
   ```
   Get-CsHostingProvider
   ```

3. A continuación, todavía desde la ventana del shell, ejecute:
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.
    
## <a name="test-your-mobility-deployment"></a>Probar la implementación de la movilidad
<a name="TestMobility"> </a>

Una vez que haya implementado el servicio de movilidad de Skype empresarial Server y el servicio Detección automática de Skype empresarial Server, querrá ejecutar una transacción de prueba para asegurarse de que el funcionamiento de su implementación es correcto. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro. Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba. Este comando funciona tanto para los clientes de Skype empresarial como para los clientes de Lync Server 2013.
  
Para los clientes de Lync Server 2010 en Skype empresarial Server 2015, tendrá que ejecutar **Test-CsMcxP2PIM** para realizar la prueba. Sus usuarios de Lync Server 2010 seguirán teniendo que ser usuarios reales o usuarios de prueba predefinidos y necesitarán sus credenciales de contraseña.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial

1. Inicie sesión como miembro del rol de **CsAdministrator** en cualquier equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Probar las conferencias para clientes móviles de Lync 2010

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.

1. Inicie sesión como miembro del rol de **CsAdministrator** en cualquier equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   También es posible establecer las credenciales en un script y pasarlas al cmdlet de prueba. Tenemos un ejemplo de ello a continuación.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para revisar en detalle los procedimientos de comando, puede consultar [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar notificaciones de inserción
<a name="ConfigPush"> </a>

Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva. Pero, ¿qué son las notificaciones push? Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido. El servicio de movilidad de Skype empresarial Server envía estas notificaciones al servicio de notificaciones de inserción basado en la nube de Skype empresarial Server, que después envía las notificaciones al servicio de notificaciones push de Microsoft (MSNS) para los usuarios de Windows Phone.
  
Esta funcionalidad no ha sido modificada en Lync Server 2013, pero si tiene un servidor de Skype empresarial, querrá hacer lo siguiente:
  
- Para un servidor perimetral de Skype empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype empresarial online y, a continuación, configure la Federación de proveedores de hospedaje entre su organización y Skype empresarial online.
    
- Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.
    
- Pruebe la configuración de federación y las notificaciones de inserción.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Agregue un proveedor de hospedaje en línea de Skype empresarial Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por ejemplo:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline. 
  
4. Configure la Federación de proveedores de hospedaje entre su organización y el servicio de notificaciones de inserción en Skype empresarial online. En la línea de comando, deberá escribir:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Habilite las notificaciones de inserción:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilite la federación:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Probar la federación y las notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Pruebe la configuración de la federación:
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Por ejemplo:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Pruebe las notificaciones de inserción:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Por ejemplo:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurar la directiva de movilidad
<a name="ConfigMob"> </a>

Tiene la capacidad de usar Skype empresarial Server para determinar quién puede usar su servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o video, así como si se necesitará WiFi para VoIP o video. Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil. La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes. Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo. La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.
  
La movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas de forma predeterminada. La configuración para requerir WiFi para VoIP y vídeo está deshabilitada. Un administrador tiene la capacidad de cambiar esto, ya sea de forma global, por sitio o por usuario.
  
Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben:
  
- Habilitado para Skype empresarial Server
    
- estar habilitados para telefonía IP empresarial;
    
- Se le asignó una directiva de movilidad que tiene la opción **EnableMobility** establecida en **true**.
    
Para que los usuarios puedan usar Vía trabajo, también deben:
  
- tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;
    
- Se le asignó una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **true**.
    
> [!NOTE]
> Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles. 
  
### <a name="modify-global-mobility-policy"></a>Modificar la directiva de movilidad global

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Para desactivar el acceso a la movilidad y las llamadas a través del trabajo, escribe:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad. Pero no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo. 
  
    Para obtener más información, consulta [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar Directiva de movilidad por sitio

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Más información en [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar Directiva de movilidad por usuario

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el Shell y la **Ocscore** de **Administración de Skype empresarial Server** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través del trabajo por usuario. Escriba:
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Otro ejemplo con datos de muestra:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad. Pero no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo. 
  

