---
title: Implementación y configuración de movilidad de Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: En este artículo le guiará a través de los pasos para configurar un Skype existente para la instalación de Business Server para usar el servicio de movilidad, lo que permite a los dispositivos móviles que puedan aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
ms.openlocfilehash: c9203bb90f4d4659819a4336c21f08e58785dfde
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884269"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implementación y configuración de movilidad de Skype para Business Server  
 
En este artículo le guiará a través de los pasos para configurar un Skype existente para la instalación de Business Server para usar el servicio de movilidad, lo que permite a los dispositivos móviles que puedan aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
  
Después de reconsiderar el artículo [planeación de movilidad de Skype para Business Server](../plan-your-deployment/mobility.md) , deberá estar preparado para continuar con los pasos siguientes para implementar la movilidad en su Skype para el entorno de servidor empresarial. Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):
  
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
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
## <a name="create-dns-records"></a>Crear registros de DNS
<a name="CreateDNSRec"> </a>

Es posible que ya tiene estos como parte de su Skype para el entorno de servidor empresarial, pero es necesario crear los siguientes registros para la detección automática para que funcione:
  
- Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.
    
Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).
  
### <a name="create-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que principal a su Skype para servidores de Front-End del servidor empresarial y expanda las **Zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.
    
6. En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el **nombre de dominio completo (FQDN para el host de destino**, que necesitará para escriba o busque el FQDN de servicios Web internos para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior. Haga clic en Aceptar cuando ya lo haya introducido.
    
8. Debe crear un nuevo registro CNAME de Autodiscover en la zona de búsqueda directa para cada dominio SIP compatibles con su Skype para el entorno de servidor empresarial.
    
### <a name="create-an-external-dns-cname-record"></a>Crear un registro CNAME de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, un dominio SIP ya debe existir existe para Skype para Business Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.
    
5. Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debería haber un área para escribir en un **nombre de dominio completo para el host de destino**, deberá ser el FQDN para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.
    
7. Es posible que necesite guardar aquí, o si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su Skype para entorno Business Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.
    
### <a name="create-an-internal-dns-a-record"></a>Crear un registro A de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que principal a su Skype para servidores de Front-End del servidor empresarial y expanda las **Zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.
    
6. En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el cuadro de texto **Dirección IP** , escriba la dirección IP de servicios Web interna para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior.
    
8. Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.
    
9. Debe crear un nuevo registros de Autodiscover A o AAAA en la zona de búsqueda directa para cada dominio SIP compatibles con su Skype para el entorno de servidor empresarial. Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.
    
10. Cuando haya terminado, haga clic en **Listo**.
    
### <a name="create-an-external-dns-a-record"></a>Crear un registro A de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, un dominio SIP ya debe existir existe para Skype para Business Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o grupos de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director del grupo de servidores (una configuración opcional es posible que tenga en su implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.
    
5. Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debería haber un área para escribir en una **Dirección IP**, esto deberá ser la dirección IP para el Front-End del grupo (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.
    
7. Es posible que necesite guardar aquí, o si necesita crear más registros A o AAAA en la zona de búsqueda directa de cada dominio SIP para su Skype para el entorno de servidor empresarial, debe hacer, pero una vez esté listo, guarde el trabajo.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Si tiene alguna pregunta sobre la planeación alrededor de certificados, nos hemos documentado en nuestro artículo de [planeación de movilidad de Skype para Business Server](../plan-your-deployment/mobility.md) . Cuando lo revise, le guiaremos por los siguientes temas:
  
- ¿Necesito certificados nuevos?
    
- Solicitud de nuevos certificados de su entidad de certificación (CA).
    
- Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.
    
- Comprobación de los certificados mediante el complemento de certificados en Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>¿Necesito certificados nuevos?

1. Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita. Para ello, debe iniciar sesión en su Skype para Business Server con una cuenta que sea un administrador local. Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).
    
2. Abra el Skype para Shell de administración de servidor empresarial (puede usar búsqueda buscarla si no lo tiene anclados a la barra de tareas o el menú de inicio).
    
3. Te va a resultar esencial saber qué certificados se han asignado antes de intentar agregar uno actualizado. Por ello, en el comando, escriba:
    
   ```
   Get-CsCertificate
   ```

4. La información del paso 3 será exclusiva para usted. Tiene que analizarla para determinar si cuenta con un certificado único asignado a varias cosas o si tiene un certificado distinto asignado a cada uno de los diferentes componentes que lo necesitan. El parámetro **Use** le indicará cómo se ha estado usando un certificado, mientras que el parámetro **Thumbprint** le indicará si se trata del mismo certificado o de varios.
    
5. Si tiene las entradas SAN recomendadas en nuestra sección Planificación, está en el camino correcto. En caso contrario, tendrá que solicitar un certificado nuevo o varios certificados (según su configuración) a la entidad de certificación.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar uno o varios certificados nuevos a una entidad de certificación (CA)

1. Después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene un **único certificado** (mediante los pasos anteriores) y sabrá que no tiene todas las entradas que necesita. En ese caso, se debe solicitar a la CA un nuevo certificado. Abra su Skype para Business Server PowerShell:
    
   - En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como se muestra en el ejemplo anterior. Debe usar el parámetro DomainName en su lugar. Y cuando se utiliza el parámetro DomainName, tiene que definir el FQDN de los registros de lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (reemplazando el parámetro -Ca con su propia ruta de acceso de la entidad emisora de certificados):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita. Si es así, se debe solicitar a la CA un nuevo certificado. Abra su Skype para Business Server PowerShell:
    
   - En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como se muestra en el ejemplo anterior. Debe usar el parámetro DomainName en su lugar. Y cuando se utiliza el parámetro DomainName, tiene que definir el FQDN de los registros de lyncdiscoverinternal y lyncdiscover. Algunos ejemplos serían (reemplazando el parámetro -Ca con su propia ruta de acceso de la entidad emisora de certificados):
    
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
    
3. En la ventana emergente, en probabilidad todos los que hace esto en el equipo que se encarga a los certificados que necesita para mirar, deje es así la selección en el **equipo Local** si lo. Si está trabajando en un equipo remoto, cambie el botón de radio a **Otro equipo** y escriba el FQDN de ese equipo o utilice el botón **Examinar** para buscar dicho equipo a través de AD. Después de seleccionar el equipo, debe hacer clic en **Finalizar** cuando esté listo y, a continuación, **Aceptar** para agregar el complemento a la consola MMC.
    
4. Expanda la sección de **certificados** en el panel izquierdo de MMC. Expanda la carpeta **Personal** también y seleccione **Certificados**. Esto le permitirá ver los certificados de esta tienda.
    
5. Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.
    
    > [!NOTE]
    > ¿Cómo puede saber qué certificado es? Debe ser puede ser el único certificado asignado a todo el contenido de la granja de servidores, o puede tener varios certificados para cosas diferentes, al igual que de forma predeterminada, los servicios Web internos, etc., en cuyo caso es posible que deba ver varios certificados. Varios certificados tendrán la misma huella digital. 
  
6. Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.
    
7. También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:
    
   - El nombre del grupo para este grupo de servidores o el nombre del servidor si este no es un grupo de servidores.
    
   - Nombre del servidor al que está asignado el certificado.
    
   - Registros de direcciones URL simples, normalmente de reunión y marcación.
    
   - Servicios Web internos y los servicios Web externos los nombres (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones elegidas en el generador de topología y reemplazadas selecciones de servicios Web.
    
   - Si ya está asignado, el lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
     Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).
    
8. Por lo tanto, si se encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ha elegido ya configurado. Puede cerrar MMC.
    
9. Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).
    
## <a name="configure-the-reverse-proxy"></a>Configurar el proxy inverso
<a name="ConfigRP"> </a>

No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.
  
Microsoft como un producto ya no ofrece TMG y, si aún necesita configurarlo, puede consultar los [pasos de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Pero la siguiente información de pretende ser útiles de forma más general, incluso si no hay ninguna forma podemos proporcionar pasos del tutorial específico para cada proxy inverso ahí.
  
Debemos considerar dos aspectos:
  
- ¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?
    
  - Si tiene una regla de publicación web, debe modificarla.
    
  - Si no tiene una regla de publicación web todavía, debe crearla.
    
- Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.
    
> [!NOTE]
> **Importante** Un valor de tiempo de espera de servidor Proxy es un número que puede variar de una implementación a otra. Debe supervisar la implementación y modifique el valor de la mejor experiencia para los clientes. Es posible que pueda establecer el valor tan bajo como 200. Si admite a clientes móviles de Lync en su entorno, debe establecer el valor a 960 para permitir tiempos de espera de notificación de inserción de Office 365, que tiene un valor de tiempo de espera de 900. Es muy probable que tendrá que aumentar el valor de tiempo de espera para evitar el cliente se desconecta cuando el valor es demasiado bajo o reduzca el número si las conexiones a través del proxy no desconecten pero desactive mucho después de que el cliente ha desconectado. Supervisión y líneas de base lo habitual para su entorno es la única forma precisa para determinar la configuración adecuada para este valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Necesitará para localizar la regla de publicación de web y elija la opción de Editar (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).
    
3. Debe haber un área que indica lo que se aplica esta regla de publicación de web a. Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios. Deberá **agregar** una nueva entrada.
    
4. Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del servidor de proxy inverso.
    
5. Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática. Que debe también ha instalado y configurado para su uso de acuerdo con la configuración del servidor de proxy inverso. Asegúrese de guardar todo cuando haya completado la configuración.
    
6. Si el proxy inverso tiene una funcionalidad de **prueba** , a continuación, asegúrese de uso del mismo, para garantizar que todo funciona correctamente.
    
7. Ahora, es posible que necesite Repita estos pasos si tiene un Director o el Director de grupo de servidores en su entorno (Esto significa que tiene una segunda regla).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Crear una regla de publicación de web para la dirección URL de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Debe buscar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **La acción de regla**: en este caso se trata de una regla de **permiso** , algo que permite que pase a través de proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser **SSL** para acceso interno. Elija esa opción.
    
   - Va a necesitar publicar una ruta de acceso para **Publicación interna**y escriba el FQDN para los servicios Web externos en el equilibrador de carga de su Front-End del grupo de servidores (o el FQDN del equilibrador de carga del grupo de servidores del Director si tiene uno), un ejemplo sería sfb_ pool01.contoso.local.
    
   - Debe escribir ** / *** como la ruta de acceso para su publicación, pero también debe **Reenviar el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(Esto es la dirección URL del servicio Detección automática externo). Ahora, si está creando una regla para la URL de servicios Web externos en el grupo de servidores Front-End, debe escribir el FQDN para los servicios Web externos en el grupo de servidores Front-End (por ejemplo, lyncwebextpool01.contoso.com).
    
   - Habrá una opción de **ruta de acceso** y necesita escribir ** / *** aquí.
    
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
    
2. Debe buscar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **La acción de regla**: en este caso se trata de una regla de **permiso** , algo que permite que pase a través de proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.
    
   - Va a necesitar publicar una ruta de acceso para **Publicación interna**y escriba el FQDN de la **dirección VIP** del equilibrador de carga de su Front-End del grupo de servidores, un ejemplo sería sfb_pool01.contoso.local.
    
   - Debe escribir ** / *** como la ruta de acceso para su publicación, pero también debe **Reenviar el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(Esto es la dirección URL del servicio Detección automática externo).
    
   - Habrá una opción de **ruta de acceso** y necesita escribir ** / *** aquí.
    
   - Debe seleccionar una escucha de web, o permitir que el proxy inverso crear uno.
    
   - **Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta es toda la información que puede necesitar para crear esta regla y poder continuar.
    
4. Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:
    
   - **Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
5. Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar la detección automática para movilidad con implementaciones híbridas
<a name="ConfigAutoD"> </a>

Entornos híbridos de Skype para Business Server son entornos que combinan un local y el entorno de Office 365. Cuando tenga Skype para trabajar en un entorno híbrido de Business Server, el servicio Detección automática debe ser capaz de encontrar a un usuario de cualquiera de estos entornos.
  
Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:
  
1. Abra Skype para Shell de administración de servidor empresarial.
    
2. Ejecute el siguiente procedimiento para obtener el valor del atributo **ProxyFQDN** para su Skype para entorno Business Server:
    
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

Una vez haya implementado Skype para el servicio de movilidad de Business Server y Skype para servicio de detección automática de servidor empresarial, desea ejecutar una transacción de prueba, para asegurarse de trabajo de la implementación adecuada. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro. Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba. Este comando funcionará para ambos Skype para clientes empresariales, así como los clientes de Lync Server 2013.
  
Para los clientes de Lync Server 2010 en Skype para Business Server 2015, debe ejecutar **Test-CsMcxP2PIM** para probar. Los usuarios de Lync Server 2010 aún se tienen que ser usuarios reales o usuarios de prueba predefinidos y necesitará sus credenciales de contraseña.

> [!NOTE]
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar **Skype para Shell de administración de negocio Server** (que es posible que escriba el nombre de la búsqueda o vaya a **Todos los programas** y lo elija).
    
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
> Compatibilidad con MCX (servicio de movilidad) para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Todos los Skype actual para los clientes móviles de negocio ya usa la API de Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (IM), presencia y contactos. Los usuarios con los clientes heredados con MCX necesitará actualizar a un cliente actual.

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar **Skype para Shell de administración de negocio Server** (que es posible que escriba el nombre de la búsqueda o vaya a **Todos los programas** y lo elija).
    
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

Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva. Pero ¿qué son las notificaciones de inserción? Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido. El Skype para servicio de movilidad de Business Server envía estas notificaciones a la Skype basados en la nube para servidor de inserción notificación servicio empresarial, que, a continuación, envía las notificaciones para el servicio de notificación de inserción de Microsoft (MSNS) para los usuarios de Windows Phone.
  
Esta funcionalidad se ha modificado desde Lync Server 2013, pero si tiene un Skype para Business Server, querrá hacer lo siguiente:
  
- Para un Skype para servidor perimetral de Business Server, agregar un nuevo proveedor de hospedaje, Microsoft Skype para profesionales en línea y, a continuación, configurar la federación de hospedaje entre su organización y Skype para profesionales en línea.
    
- Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.
    
- Pruebe la configuración de federación y las notificaciones de inserción.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
3. Agregar un Skype para el proveedor de hospedaje en línea Business Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por ejemplo:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline. 
  
4. Configurar la federación del proveedor de hospedaje entre su organización y el servicio de notificación de inserción en Skype para profesionales en línea. En la línea de comando, deberá escribir:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
3. Habilite las notificaciones de inserción:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilite la federación:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Probar la federación y las notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
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

Tiene la posibilidad de con Skype para Business Server determinar quién puede usar el servicio de movilidad, llamar vía trabajo, voz sobre IP (VoIP), o de vídeo, así como si va a ser necesario para VoIP o vídeo WiFi. Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil. La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes. Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo. La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.
  
Movilidad, llamada vía trabajo y VoIP y las características de vídeo están habilitadas de forma predeterminada. Esta opción de requerir WiFi para VoIP y vídeo están deshabilitadas. Un administrador tiene la capacidad para cambiar esto, globalmente, por sitio, o por usuario.
  
Para poder usar las características de movilidad y llamada vía trabajo, los usuarios deben ser:
  
- Habilitado para Skype para Business Server
    
- estar habilitados para telefonía IP empresarial;
    
- Asigna una directiva de movilidad que tiene la opción **enablemobility configurada** en **True**.
    
Para que los usuarios puedan usar Vía trabajo, también deben:
  
- tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;
    
- Asigna una directiva de movilidad que tiene la **enableoutsidevoice configurada** establecida en **True**.
    
> [!NOTE]
> Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles. 
  
### <a name="modify-global-mobility-policy"></a>Modificar la directiva de movilidad global

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
3. Desactivar el acceso a la movilidad y vía trabajo globalmente escribiendo:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Puede desactivar llamada vía trabajo sin desactivar el acceso a la movilidad. Pero no se puede desactivar la movilidad sin desactivar también llamada vía trabajo. 
  
    Para obtener más información, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar la directiva de movilidad por sitio

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
3. Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Más información en [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar la directiva de movilidad por usuario

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo que tenga instalado **Skype para Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Inicie el **Skype para Shell de administración de servidor empresarial**.
    
3. Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y llamada vía trabajo por usuario. Escriba:
    
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
    > Puede desactivar llamada vía trabajo sin desactivar el acceso a la movilidad. Pero no se puede desactivar la movilidad sin desactivar también llamada vía trabajo. 
  

