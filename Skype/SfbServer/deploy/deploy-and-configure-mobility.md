---
title: Implementar y configurar la movilidad para Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará por los pasos para configurar un Skype existente para la instalación de Business Server 2015 para utilizar el servicio de movilidad, que permite a los dispositivos móviles poder aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a>Implementar y configurar la movilidad para Skype Empresarial Server 2015
 
Este artículo le guiará por los pasos para configurar un Skype existente para la instalación de Business Server 2015 para utilizar el servicio de movilidad, que permite a los dispositivos móviles poder aprovechar las ventajas de Skype para las características de movilidad de servidor empresarial.
  
Después de reconsiderar el artículo [Plan para la movilidad de Skype para Business Server 2015](../plan-your-deployment/mobility.md) , debería estar listo para continuar con los pasos siguientes para implementar la movilidad en su Skype para entorno Business Server 2015. Los pasos son los siguientes (e incluimos en esta tabla una lista de permisos):
  
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
  
## <a name="create-dns-records"></a>Crear registros DNS
<a name="CreateDNSRec"> </a>

Es posible que tenga como parte de su Skype para entorno Business Server, pero debe crear los siguientes registros de Autodiscovery funcione:
  
- Un registro DNS interno para dar soporte a los usuarios móviles que se conectan desde la red de su organización.
    
- Un registro DNS externo (o público) para dar soporte a los usuarios móviles que se conectan desde fuera de la red de su organización.
    
Estos registros pueden ser registros CNAME o nombres (de host) A (no tiene que crear ambos; únicamente estamos incluyendo los pasos necesarios para todo aquí).
  
### <a name="create-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que inicio a su Skype para servidores de Business Server frontales y expanda las **Zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Nuevo alias (CNAME)** en el menú.
    
6. En el cuadro de texto **Nombre de alias**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el **nombre de dominio completo (FQDN para host de destino**, debe escribir o buscar el FQDN interno de servicios Web Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificó en el paso 4 anterior. Haga clic en Aceptar cuando ya lo haya introducido.
    
8. Debe crear un nuevo registro de Autodiscover CNAME en la zona de búsqueda directa para cada dominio SIP de su Skype para entorno Business Server admite.
    
### <a name="create-an-external-dns-cname-record"></a>Crear un registro CNAME de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, un dominio SIP ya debe existir allí para Skype para Business Server 2015. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **alias nuevo (CNAME)**.
    
5. Ahora debería poder introducir un **nombre de alias**. Para ello, tiene que escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área para escribir en un **nombre de dominio completo para host de destino**, deberá ser el FQDN para el Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.
    
7. Puede que necesite guardar aquí, o si necesita crear más registros CNAME en la zona de búsqueda directa de cada dominio SIP en su Skype para entorno Business Server, debe hacerlo, pero una vez que esté listo, guarde su trabajo.
    
### <a name="create-an-internal-dns-a-record"></a>Crear un registro A de DNS interno

1. Inicie sesión en un servidor DNS de su red que sea miembro del grupo **Admins. del dominio** o el grupo **DnsAdmins**.
    
2. Haga clic en **Inicio**, elija **Herramientas administrativas** (es posible que tenga que **buscar** esta opción si no forma parte del menú Inicio) y haga clic en **DNS** para abrir el complemento administrativo de DNS.
    
3. En el panel izquierdo de la ventana de la consola, necesitará ir al dominio que inicio a su Skype para servidores de Business Server frontales y expanda las **Zonas de búsqueda directa** .
    
4. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).
    
5. Cuando lo haya comprobado, haga clic con el botón secundario en el nombre de dominio SIP y elija **Host nuevo (A o AAAA)** en el menú.
    
6. En el cuadro de texto **Nombre**, escriba lyncdiscoverinternal como nombre de host para la dirección URL interna del servicio Detección automática.
    
7. En el cuadro de texto **Dirección IP** , escriba la dirección IP de servicios Web interna para el Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 4 anterior.
    
8. Una vez hecho esto, haga clic en **Agregar host** y, a continuación, haga clic en **Aceptar**.
    
9. Debe crear nuevos registros de Autodiscover A o AAAA en la zona de búsqueda directa para cada dominio SIP de su Skype para entorno Business Server admite. Para ello, repita los pasos 6 a 8 tantas veces como sea necesario.
    
10. Cuando haya terminado, haga clic en **Listo**.
    
### <a name="create-an-external-dns-a-record"></a>Crear un registro A de DNS externo

1. Estos pasos son genéricos porque, a pesar de que no podemos saber qué proveedor de DNS público está usando, queremos seguir ayudándole. Inicie sesión en el proveedor de DNS público con una cuenta que le permita realizar nuevos registros DNS en él.
    
2. En este momento, un dominio SIP ya debe existir allí para Skype para Business Server 2015. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala.
    
3. Dedique un momento a ver cuáles de los siguientes registros tiene:
    
   - Cualquier A o AAAA registros de host para el servidor de Front-End (Standard o Enterprise) o pools de Front-End.
    
   - Cualquier host A o registros AAAA para un Director o el Director de la piscina (una configuración opcional que se puede tener en la implementación).
    
4. Cuando ya tenga esa información, podrá seleccionar una opción para crear un **nuevo host A o AAAA**.
    
5. Ahora debería poder introducir un **nombre**. Para ello, tiene que escribir lyncdiscover para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área para escribir en una **Dirección IP**, esto deberá ser la IP Front-End pool (o único servidor Front-End, o grupo de directores o Director), identificado en el paso 3 anterior.
    
7. Puede que necesite guardar aquí, o si necesita crear más registros A o AAAA en la zona de búsqueda directa de cada dominio SIP para su Skype para entorno Business Server, debe hacer eso, pero una vez esté listo, guarde el trabajo.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Si tiene preguntas acerca de la planificación alrededor de certificados, nos hemos documentado en nuestro artículo de [Plan para la movilidad de Skype para Business Server 2015](../plan-your-deployment/mobility.md) . Cuando lo revise, le guiaremos por los siguientes temas:
  
- ¿Necesito certificados nuevos?
    
- Solicitud de nuevos certificados de su entidad de certificación (CA).
    
- Actualización de certificados locales con los reemplazos mediante el uso de PowerShell.
    
- Comprobación de los certificados mediante el complemento certificados en Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>¿Necesito certificados nuevos?

1. Primero, es probable que necesite comprobar qué certificados tiene en local y si tienen las entradas que necesita. Para ello, debe iniciar sesión en tu Skype para Business Server 2015 server con una cuenta que sea un administrador local. Para algunos de estos pasos, es posible que esta cuenta necesite tener derechos para la entidad emisora de certificados (CA).
    
2. Abra el Skype para el Shell de administración de servidor empresarial (puede utilizar Buscar para encontrarlo si no lo tiene anclado a la barra de tarea o del menú Inicio).
    
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

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En cambio, tendrá que usar el parámetro DomainName y, en tal caso, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. O bien, después de haber comprobado qué entradas SAN tiene, ya sabrá si tiene **varios certificados** que no tienen todas las entradas que necesita. Si es así, se debe solicitar a la CA un nuevo certificado. Abra su Skype para Business Server PowerShell:
    
   - En el caso de que falte un SAN del servicio Detección automática (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. En cambio, tendrá que usar el parámetro DomainName y, en tal caso, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Algunos ejemplos serían (mediante el reemplazo del parámetro -Ca con la ruta de acceso de nuestra propia entidad de certificación):
    
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
    
3. En la ventana emergente, con toda probabilidad que hace esto en el equipo que ha el hogar de los certificados debe mirar, así que deje la selección en el **equipo Local** si es así. Si está trabajando en un equipo remoto, cambie el botón de radio a **Otro equipo** y escriba el FQDN del equipo o utilizar el botón **Examinar** para buscar dicho equipo a través de AD. Después de seleccionar el equipo, debe hacer clic en **Finalizar** cuando esté listo y en **Aceptar** para agregar el complemento a la consola MMC.
    
4. Expanda la sección **certificados** en el panel izquierdo de MMC. Expanda la carpeta **Personal** también y seleccione **Certificados**. Esto le permitirá ver los certificados de esta tienda.
    
5. Tiene que ubicar el certificado que quiere ver, hacer clic con el botón derecho en él y elegir **Abrir**.
    
    > [!NOTE]
    > ¿Cómo puede saber qué certificado es? Debe ser el certificado de único asignado a todos los elementos de su granja, o puede tener varios certificados para cosas diferentes, al igual que de forma predeterminada, los servicios Web internos, etc., en cuyo caso debe mirar varios certificados. Varios certificados tendrán la misma huella digital. 
  
6. Cuando haya llegado a la vista **Certificado**, elija **Detalles**. Esto le permitirá ver el nombre del firmante del certificado al seleccionar **Sujeto** y se mostrará el nombre del sujeto asignado y sus propiedades asociadas.
    
7. También necesitará comprobar las entradas de **Nombres alternativos de firmante**. Encontrará uno o varios de lo siguiente:
    
   - El nombre del grupo para este grupo, o el nombre de servidor único si este no es un grupo.
    
   - Nombre del servidor al que está asignado el certificado.
    
   - Registros de direcciones URL simples, normalmente de reunión y marcación.
    
   - Servicios Web internos y los servicios Web externos los nombres (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), basados en las elecciones realizadas en el generador de topología y las selecciones de servicios Web reemplazadas.
    
   - Si ya ha asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
    Necesitará comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).
    
8. Por lo tanto, si se encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ha elegido ya configurado. Puede cerrar MMC.
    
9. Si no están asignados, tendrá que realizar una nueva solicitud de certificado (como se detalla anteriormente) o deberá instalarlos después de la solicitud (para ello recomendamos seguir los pasos para Powershell detallados anteriormente).
    
## <a name="configure-the-reverse-proxy"></a>Configurar el proxy inverso
<a name="ConfigRP"> </a>

No es necesario seguir al pie de la letra los pasos que se explican a continuación. En las versiones anteriores del producto, le hemos guiado, por ejemplo, en el proceso de configuración de Threat Management Gateway (TMG) y, si no lo estaba utilizando, tenía que encontrar la forma de adaptarlo a su propia versión a partir de la información con la que contaba.
  
TMG ya no se ofrece por Microsoft como un producto y, si aún necesita configurarlo, puede mirar los [pasos de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Pero la siguiente información ha sido diseñada ser generalmente más útil, incluso si no hay ninguna manera podemos proporcionar los pasos del tutorial específico para cada proxy inverso por ahí.
  
Debemos considerar dos aspectos:
  
- ¿Hará su solicitud de detección automática inicial a través de HTTPS (recomendado)?
    
  - Si tiene una regla de publicación web, debe modificarla.
    
  - Si no tiene una regla de publicación web todavía, debe crearla.
    
- Si está realizando una solicitud de detección automática inicial a través de HTTP, también tendrá que crear o modificar esa regla.
    
> [!NOTE]
> **Importante** Un valor de tiempo de espera de servidor Proxy es un número que puede variar de una implementación a otra. Debe supervisar la implementación y modifique el valor de la mejor experiencia para los clientes. Puede establecer un valor tan bajo como 200. Si admite a clientes móviles Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificación de inserción de Office 365, que tienen un valor de tiempo de espera de 900. Es muy probable que tendrá que aumentar el valor de tiempo de espera para evitar el cliente se desconecta cuando el valor es demasiado bajo, o reducir el número, si las conexiones a través del proxy no desconecten pero desactive mucho después de que el cliente se desconectó. Supervisión y nivel de referencia lo habitual en su entorno es la única forma precisa para determinar la configuración adecuada para este valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Debe encontrar la regla de publicación web y elegir la opción Editar (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso).
    
3. Debe haber un área que indica lo que se aplica esta regla de publicación de web para. Tendrá que modificar la regla para los sitios de entrada o las solicitudes de sitios. Deberá **agregar** una nueva entrada.
    
4. Escriba el nombre de su sitio de detección automática (en el ejemplo que utilizaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato del servidor de proxy inverso.
    
5. Es probable que cuente con un certificado nuevo que contenga la entrada SAN de detección automática. Que debe ser también instalado y configurado para su uso según la configuración del servidor de proxy inverso. Asegúrese de guardar todo cuando haya completado la configuración.
    
6. Si el proxy inverso tiene una funcionalidad de **prueba** , por favor haga uso de él, para garantizar que todo funciona correctamente.
    
7. Ahora, puede que necesite repetir estos pasos si tiene un Director o Director de grupo en su entorno (Esto significaría tener una segunda regla).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Crear una regla de publicación de web para la dirección URL de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Debe localizar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **La acción de regla**: en este caso es una regla de **permiso** , algo permite que pase a través de proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser **SSL** para acceso interno. Elija esa opción.
    
   - Va a necesitar una ruta de publicación para **Publicación en interno**y escriba el FQDN para los servicios Web externos de equilibrador de carga de la agrupación de Front-End (o el FQDN del equilibrador de carga del grupo Director si tiene uno), un ejemplo sería sfb_ pool01.contoso.local.
    
   - Debe escribir ** / ** como la ruta de acceso que se publiquen, pero también debe **enviar el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(ésta es la dirección URL del servicio Detección automática externos). Ahora, si está creando una regla para la URL de servicios Web externos en el grupo de servidores Front-End, debe escribir el nombre completo de los servicios Web externos en el grupo de servidores Front-End (por ejemplo, lyncwebextpool01.contoso.com).
    
   - Habrá una opción de **ruta de acceso** y tendrá que escribir ** / ** aquí.
    
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
    
2. Debe localizar donde en la interfaz de crear las reglas de publicación de web y elija la opción **nuevo** o **crear** (puede estar en un menú o ficha, dependiendo de la configuración de proxy inverso). Debe buscar la opción que le permita crear una nueva regla de publicación web.
    
3. Generalmente necesitará especificar la información siguiente:
    
   - **Nombre**: el nombre para la regla.
    
   - **La acción de regla**: en este caso es una regla de **permiso** , algo permite que pase a través de proxy inverso.
    
   - La opción o regla de **publicación** que elija será un **único sitio web o equilibrador de carga**.
    
   - Tiene que ser una **conexión no segura para conectarse con la granja o el servidor web publicado**.
    
   - Va a necesitar una ruta de publicación para **Publicación en interno**y escriba el FQDN de la **dirección VIP** del equilibrador de carga de la agrupación de Front-End, un ejemplo sería sfb_pool01.contoso.local.
    
   - Debe escribir ** / ** como la ruta de acceso que se publiquen, pero también debe **enviar el encabezado de host original**.
    
   - Habrá una opción para la información o los detalles del **nombre externo o público**. Aquí es donde podrá introducir lo siguiente:
    
   - **Solicitudes de aceptación**, pero debería ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(ésta es la dirección URL del servicio Detección automática externos).
    
   - Habrá una opción de **ruta de acceso** y tendrá que escribir ** / ** aquí.
    
   - Debe seleccionar un agente de escucha de web, o permitir que el proxy inverso crear uno.
    
   - **Delegación de autenticación** debe establecerse en **Sin delegación**, pero **no debe** permitirse la autenticación directa de cliente.
    
   - La regla debe establecerse en **Todos los usuarios**.
    
   - Esta es toda la información que puede necesitar para crear esta regla y poder continuar.
    
4. Será necesario configurar los puertos del **servidor web**. Para ello, tendrá que hacer lo siguiente:
    
   - **Redirigir peticiones al puerto HTTP** y el número de puerto debe ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
5. Cuando todo esté configurado, debe guardar o aplicar esta configuración y, a continuación, debería probar la regla.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar la detección automática para movilidad con implementaciones híbridas
<a name="ConfigAutoD"> </a>

Entornos híbridos en Skype para Business Server 2015 son entornos que combinen una local y entorno de O365. Cuando tenga Skype para trabajar en un entorno híbrido de Business Server, el servicio Detección automática debe poder localizar a un usuario de cualquiera de estos entornos.
  
Para permitir que los clientes móviles descubran dónde se encuentra un usuario, el servicio Detección automática tiene que configurarse con un nuevo localizador uniforme de recursos (URL). Los pasos son los siguientes:
  
1. Abre Skype para el Shell de administración de servidor empresarial.
    
2. Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** de su Skype para entorno Business Server:
    
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

Una vez que haya implementado Skype para servicio de movilidad Business Server y Skype para el servicio de detección automática del servidor de negocios, desea ejecutar una transacción de prueba, para asegurarse de que trabajo de la implementación es correcta. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear una conferencia, unirse a ella y comunicarse dentro. Necesitará dos usuarios (real o de prueba) y sus credenciales completas para realizar esta prueba. Este comando funcionará para ambos Skype para clientes empresariales, así como los clientes de Lync Server 2013.
  
Para los clientes de Lync Server 2010, debe ejecutar **CsMcxP2PIM de prueba** para probar. Los usuarios de Lync Server 2010 todavía tendrá que ser usuarios reales, o los usuarios de prueba predefinidas y tendrá sus credenciales de contraseña.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Probar las conferencias para clientes móviles de Lync 2013 y Skype Empresarial

1. Inicie sesión como un miembro de la función **CsAdministrator** en cualquier equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar **Skype para el Shell de administración de servidor de negocio** (que podría escribir el nombre en la búsqueda o vaya a **Todos los programas** y elige).
    
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

1. Inicie sesión como un miembro de la función **CsAdministrator** en cualquier equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar **Skype para el Shell de administración de servidor de negocio** (que podría escribir el nombre en la búsqueda o vaya a **Todos los programas** y elige).
    
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

Para revisar los procedimientos de comando aún más, puede desproteger [Prueba CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [CsMcxP2PIM de prueba](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar notificaciones de inserción
<a name="ConfigPush"> </a>

Las notificaciones de inserción, que tienen la forma de notificaciones, iconos o alertas, pueden enviarse a un dispositivo móvil incluso cuando la aplicación Skype o Lync está inactiva. ¿En qué consisten las notificaciones de inserción? Son alertas de eventos, como una invitación de mensajería instantánea perdida o nueva, o un correo de voz recibido. El Skype para servicio Business Server 2015 movilidad envía esas notificaciones al Skype en la nube para Business Server Push servicio de notificación, que envía las notificaciones a Microsoft Push Notification Service (MSNS) para los usuarios de Windows Phone.
  
Esta funcionalidad se ha modificado desde Lync Server 2013, pero si tienes un Skype para Business Server, deberá hacer lo siguiente:
  
- Para un Skype para Business Server 2015 Edge Server, agregar un nuevo proveedor de hospedaje, Microsoft Skype para los negocios en línea y configure la federación de proveedor entre la organización y Skype para los negocios en línea de hospedaje.
    
- Habilite las notificaciones de inserción ejecutando el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.
    
- Pruebe la configuración de federación y las notificaciones de inserción.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar el servidor perimetral de Skype Empresarial para notificaciones de inserción

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
3. Agregue un Skype para el proveedor de hospedaje en línea Business Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por ejemplo:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > No puede tener más de una relación de federación con un solo proveedor de host. Es decir, si ya ha configurado un proveedor de host que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de host para él, aunque la identidad del proveedor de host no sea SkypeOnline. 
  
4. Configurar la federación proveedor hospedaje entre la organización y el servicio de notificación Push en Skype para los negocios en línea. En la línea de comando, deberá escribir:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificaciones de inserción

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
3. Habilite las notificaciones de inserción:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilite la federación:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Probar la federación y las notificaciones de inserción

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
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

Tiene la posibilidad de con Skype para Business Server 2015 determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o de vídeo, así como si va a ser necesario para VoIP o vídeo WiFi. Vía trabajo permite a un usuario móvil realizar y recibir llamadas con el número de teléfono de su trabajo en lugar de su número de teléfono móvil. La persona en el otro extremo de la línea no verá el número del teléfono móvil de ese usuario móvil y se evitarán los cargos por llamadas salientes. Cuando se configuran VoIP y vídeo, los usuarios pueden recibir y realizar llamadas de VoIP y vídeo. La configuración del uso de WiFi define si será necesario que el dispositivo móvil de un usuario use una red WiFi además de una red de datos de telefonía móvil.
  
Movilidad, llamada a través del trabajo y el VoIP y funciones de vídeo están habilitados de forma predeterminada. La opción de requerir WiFi para VoIP y vídeo están deshabilitadas. Un administrador tiene la capacidad para cambiar esto, globalmente, por sitio, o por el usuario.
  
Para poder utilizar las características de movilidad y llamada a través del trabajo, los usuarios deben:
  
- Habilitado para Skype para Business Server 2015
    
- estar habilitados para telefonía IP empresarial;
    
- Asignar una directiva de movilidad que tiene la opción de **EnableMobility** establecida en **True**.
    
Para que los usuarios puedan usar Vía trabajo, también deben:
  
- tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada;
    
- Asignar una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **True**.
    
> [!NOTE]
> Los usuarios que no están habilitados para la telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP entre usuarios de Skype o pueden unirse a conferencias mediante el uso del vínculo Hacer clic para unirse mientras estén en sus dispositivos móviles, siempre y cuando estén configuradas las opciones apropiadas para la directiva de voz con la que están asociados. En el tema PLANIFICACIÓN encontrará más detalles. 
  
### <a name="modify-global-mobility-policy"></a>Modificar la directiva de movilidad global

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
3. Desactivar el acceso a la movilidad y la llamada a través de trabajo globalmente escribiendo:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad. Pero no puede desactivar movilidad sin desactivar también la llamada a través del trabajo. 
  
    Para obtener más información, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar la directiva de movilidad por sitio

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
3. Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar Requerir WiFi para audio IP, y Requerir WiFi para vídeo IP por sitio. Escriba:
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Obtenga más información en [CsMobilityPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar la directiva de movilidad por usuario

1. Inicie sesión, con una cuenta que sea miembro de la función **CsAdministrator** , a un equipo donde están instalado **Skype para el Shell de administración de servidor empresarial** y **Ocscore** .
    
2. Iniciar el **Skype para el Shell de administración de servidor de empresa**.
    
3. Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través de trabajo por usuario. Escriba:
    
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
    > Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad. Pero no puede desactivar movilidad sin desactivar también la llamada a través del trabajo. 
  

