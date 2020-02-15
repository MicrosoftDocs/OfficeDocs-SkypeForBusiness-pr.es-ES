---
title: Implementación y configuración de la movilidad para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artículo le guiará por los pasos necesarios para configurar una instalación existente de Skype empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029071"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implementación y configuración de la movilidad para Skype empresarial Server  
 
Este artículo le guiará por los pasos necesarios para configurar una instalación existente de Skype empresarial Server para usar el servicio de movilidad, lo que permite que los dispositivos móviles puedan aprovechar las características de movilidad de Skype empresarial Server.
  
Tras haber revisado el artículo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , debe estar listo para continuar con los pasos siguientes para implementar la movilidad en su entorno de Skype empresarial Server. Los pasos son los siguientes (y estamos incluyendo en esta tabla una lista de permisos):
  
|**Fase**|**Permisos**|
|:-----|:-----|
|[Crear registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> Administradores  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador local  <br/> |
|[Configurar el proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador local  <br/> |
|[Configurar la detección automática para movilidad con implementaciones híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[Probar la implementación de la movilidad](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar notificaciones de inserción](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar la Directiva de movilidad](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas las secciones siguientes contienen pasos que suponen que ha leído el tema de planeación. Si algo confuso, no dude en consultar la información allí.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
## <a name="create-dns-records"></a>Crear registros DNS
<a name="CreateDNSRec"> </a>

Puede que ya los tenga como parte de su entorno de Skype empresarial Server, pero debe crear los siguientes registros para que la detección automática funcione:
  
- Un registro DNS interno para admitir usuarios móviles que se conectan desde la red de la organización.
    
- Un registro DNS externo (o público) para admitir usuarios móviles que se conectan desde fuera de la red de la organización.
    
Estos registros pueden ser nombres de (host) o registros CNAME (no es necesario hacer ambas cosas, ya que estamos incluyendo los pasos para todo esto).
  
### <a name="create-an-internal-dns-cname-record"></a>Crear un registro CNAME de DNS interno

1. Inicie sesión en un servidor DNS de la red que sea miembro del grupo **administradores de dominio** o del grupo **DnsAdmins** .
    
2. Haga clic en **Inicio**, elija **herramientas administrativas** (es posible que deba **buscarla** si no se encuentra una opción en el menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo DNS.
    
3. En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio principal de los servidores front-end de Skype empresarial Server y, a continuación, ampliar las zonas de **búsqueda directa** .
    
4. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.
    
   - Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).
    
5. Una vez que lo haya anotado, haga clic con el botón derecho en el nombre de dominio SIP y, a continuación, elija **nuevo alias (CNAME)** en el menú.
    
6. En el cuadro de texto **nombre de alias** , escriba lyncdiscoverinternal para el nombre de host de la dirección URL interna del servicio Detección automática.
    
7. En el **nombre de dominio completo (FQDN para el host de destino**, debe escribir o buscar el FQDN de servicios Web internos del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 4 anterior. Haga clic en Aceptar cuando se especifique.
    
8. Tendrá que crear un nuevo registro CNAME de detección automática en la zona de búsqueda directa para cada dominio SIP que se admita en su entorno de Skype empresarial Server.
    
### <a name="create-an-external-dns-cname-record"></a>Crear un registro CNAME de DNS externo

1. Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público podría estar usando, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que pueda crear nuevos registros DNS allí.
    
2. En este momento, ya debe existir un dominio SIP en Skype empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala de otro modo.
    
3. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.
    
   - Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).
    
4. Una vez que tenga esa información, podrá seleccionar una opción para crear un **nuevo alias (CNAME)**.
    
5. Ahora debería poder escribir un **nombre de alias**, debe escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área que especificar en un **FQDN para el host de destino**, que tendrá que ser el FQDN del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 3 anterior.
    
7. Es posible que tenga que guardar aquí o, si necesita crear registros CNAME adicionales en la zona de búsqueda directa de cada dominio SIP en su entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.
    
### <a name="create-an-internal-dns-a-record"></a>Crear un registro A de DNS interno

1. Inicie sesión en un servidor DNS de la red que sea miembro del grupo **administradores de dominio** o del grupo **DnsAdmins** .
    
2. Haga clic en **Inicio**, elija **herramientas administrativas** (es posible que deba **buscarla** si no se encuentra una opción en el menú Inicio) y, a continuación, haga clic en **DNS** para abrir el complemento administrativo DNS.
    
3. En el panel izquierdo de la ventana de la consola, tendrá que ir al dominio principal de los servidores front-end de Skype empresarial Server y, a continuación, ampliar las zonas de **búsqueda directa** .
    
4. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.
    
   - Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).
    
5. Una vez que lo haya anotado, haga clic con el botón secundario en el nombre de dominio SIP y, a continuación, elija **nuevo host (a o aaaa)** en el menú.
    
6. En el cuadro de texto **nombre** , escriba lyncdiscoverinternal para el nombre de host de la dirección URL interna del servicio Detección automática.
    
7. En el cuadro de texto **dirección IP** , escriba la dirección IP de servicios Web internos del grupo de servidores front-end (o el servidor front-end único, o el grupo o director de Director) que se identificó en el paso 4 anterior.
    
8. Cuando termine, haga clic en **Agregar host**y, a continuación, haga clic en **Aceptar**.
    
9. Tendrá que crear un nuevo registro de A o AAAA de detección automática en la zona de búsqueda directa para cada dominio SIP que se admita en su entorno de Skype empresarial Server. Para ello, repita los pasos del 6-8 al tantas veces como sea necesario.
    
10. Cuando haya terminado, haga clic en **listo**.
    
### <a name="create-an-external-dns-a-record"></a>Crear un registro A de DNS externo

1. Estos pasos son genéricos, ya que no podemos saber qué proveedor de DNS público podría estar usando, pero aún queremos ayudarle. Inicie sesión en su proveedor de DNS público con una cuenta que pueda crear nuevos registros DNS allí.
    
2. En este momento, ya debe existir un dominio SIP en Skype empresarial Server. Expanda la **zona de búsqueda directa** para este dominio SIP o ábrala de otro modo.
    
3. Tómese un momento para ver cuál de las siguientes opciones tiene:
    
   - Cualquier registro A o AAAA de host para el servidor front-end (Standard o Enterprise) o los grupos de servidores front-end.
    
   - Cualquier registro A o AAAA de host para un director o un grupo de directores (una configuración opcional que puede tener en la implementación).
    
4. Una vez que tenga esa información, podrá seleccionar una opción para crear un **nuevo host a o AAAA**.
    
5. Ahora debería poder escribir un **nombre**, debe escribir lyncdiscover aquí para la dirección URL externa del servicio Detección automática.
    
6. A continuación, debe haber un área que especificar en las **direcciones IP**, que tendrá que ser la IP del grupo de servidores front-end (o el servidor front-end único o el grupo o director de Director) identificado en el paso 3 anterior.
    
7. Es posible que tenga que guardar aquí o, si tiene que crear registros A o AAAA adicionales en la zona de búsqueda directa de cada dominio SIP para su entorno de Skype empresarial Server, debe hacerlo, pero una vez que esté listo, guarde el trabajo.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Si tiene preguntas sobre la planeación de los certificados, nos hemos documentado en nuestro artículo sobre [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) . Una vez que lo haya revisado, le guiaremos a través de lo siguiente:
  
- ¿Necesito certificados nuevos?
    
- Solicitar certificados nuevos a la entidad de certificación (CA).
    
- Actualizar los certificados locales con los reemplazos mediante PowerShell.
    
- Comprobar los certificados con el complemento certificados en Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>¿Necesito certificados nuevos?

1. En primer lugar, es posible que necesite comprobar qué certificados están en el lugar y si tienen las entradas que necesita. Para ello, debe iniciar sesión en su Skype empresarial Server con una cuenta que sea un administrador local. Es posible que esta cuenta también necesite tener derechos sobre la entidad emisora de certificados (CA) para algunos de estos pasos.
    
2. Abra el shell de administración de Skype empresarial Server (puede usar la búsqueda para encontrarla si no la tiene anclada al menú Inicio o la barra de tareas).
    
3. Será esencial que sepa qué certificados se han asignado antes de intentar agregar un certificado actualizado. Por lo tanto, en el comando, escriba:
    
   ```powershell
   Get-CsCertificate
   ```

4. La información del paso 3 será exclusiva para usted. Necesita buscarla para determinar si tiene un único certificado que se ha asignado para varios elementos o si tiene asignado un certificado diferente para los distintos componentes que los necesiten. El parámetro **use** le dirá cómo se está usando un certificado y el parámetro **Thumbprint** le dirá si es todo el mismo certificado o varios certificados.
    
5. Si tiene las entradas de SAN recomendadas en nuestra sección de planeación, está bien. Si no es así, deberá solicitar un nuevo certificado o varios certificados (según la configuración) de la entidad de certificación.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar un nuevo certificado o certificados de la entidad de certificación (CA)

1. Una vez que haya comprobado qué entradas de SAN tiene, sabrá que tiene un **único certificado** (después de comprobar los pasos anteriores) y que ha aprendido que no tiene todas las entradas que necesita. Se debe realizar una nueva solicitud de certificado a la entidad de certificación. Abra el PowerShell de Skype empresarial Server:
    
   - Para que falte un servicio de detección automática de SAN (reemplazando el parámetro-CA por su propia ruta de acceso de la entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. Deberá usar el parámetro DomainName en su lugar. Y, cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Un ejemplo sería (reemplazar el parámetro-CA por su propia ruta de acceso de la entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. O bien, una vez que haya comprobado qué entradas de SAN tiene, verá que tiene **varios certificados** que no tienen todas las entradas que necesita. Se debe realizar una nueva solicitud de certificado a la entidad de certificación. Abra el PowerShell de Skype empresarial Server:
    
   - Para que falte un servicio de detección automática de SAN (reemplazando el parámetro-CA por su propia ruta de acceso de la entidad de certificación):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ahora, si tiene varios dominios SIP, no puede usar el parámetro AllSipDomain como en el ejemplo anterior. Deberá usar el parámetro DomainName en su lugar. Y, cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover. Algunos ejemplos serían reemplazar el parámetro-CA por su propia ruta de acceso de la entidad de certificación:
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Una vez que la entidad de certificación haya generado los nuevos certificados, tendrá que asignarlos.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Asignar certificados mediante el shell de administración de Skype empresarial Server

- Según lo que haya encontrado en la sección ¿necesito nuevas certificaciones? anterior, debe ejecutar **una** de las siguientes opciones.
    
  - Si tiene un único certificado para todo (las huellas digitales son idénticas), debe ejecutar lo siguiente:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si tiene diferentes certificados para cosas (las huellas digitales son todas diferentes), ejecute esto en su lugar:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Ver certificados en Microsoft Management Console (MMC)

1. Tiene una opción para ver los certificados con el complemento certificados para MMC. Simplemente escriba MMC en la búsqueda y debería aparecer como una opción de aplicación.
    
2. Para agregar el complemento certificados, tendrá que hacer clic en **archivo**y, a continuación, **Agregar o quitar complemento...** (o método abreviado de teclado **Ctrl + M** también funcionará). Los **certificados** serán una opción en el panel izquierdo, selecciónelo y, a continuación, **cuenta de equipo** en la ventana emergente y, a continuación, **siguiente**.
    
3. Todavía en la ventana emergente, en todas las probabilidades tiene que hacerlo en el equipo principal para los certificados que necesita ver, así que deje la selección en **equipo local** si es así. Si está trabajando en un equipo remoto, cambie el botón de opción a **otro equipo** y, a continuación, escriba el FQDN de ese equipo o use el botón **examinar** para buscar el equipo a través de ad. Después de seleccionar el equipo, deberá hacer clic en **Finalizar** cuando esté listo y, después, en **Aceptar** para agregar el complemento a MMC.
    
4. Expanda la sección **certificados** en el panel izquierdo de MMC. Expanda también la carpeta **personal** y, a continuación, seleccione **certificados**. Esto le permite ver los certificados en este almacén.
    
5. Debe buscar el certificado que desea ver, hacer clic con el botón derecho en él y elegir **abrir**.
    
    > [!NOTE]
    > ¿Cómo saber qué certificado es? Debe ser el único certificado asignado a todo el conjunto o la granja de servidores, o bien puede tener varios certificados para cosas diferentes, como la predeterminada, los servicios Web internos, etc., en cuyo caso es posible que necesite mirar varios certificados. Varios certificados tendrán la misma huella digital. 
  
6. Una vez que haya llegado a la vista del **certificado** , elija **detalles**. Esto le permitirá ver el nombre del firmante del certificado cuando seleccione **asunto**, y se mostrará el nombre del sujeto asignado y las propiedades asociadas.
    
7. También necesitará comprobar las entradas de **nombre alternativo de sujeto** . Encontrará uno o varios de los siguientes elementos:
    
   - El nombre del grupo para este grupo o el nombre de servidor único si no se trata de un grupo.
    
   - El nombre del servidor al que está asignado el certificado.
    
   - Registros de direcciones URL simples, que suelen reunirse y marcar.
    
   - Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.
    
   - Si ya está asignado, el lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.
    
     Tendrá que comprobar varios certificados si tiene más de uno asignado (consulte la nota anterior).
    
8. Por lo tanto, si encuentra lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros, ya tiene configurada. Puede cerrar MMC.
    
9. Si no están asignados, necesitará crear una nueva solicitud de certificado (que se indica más arriba) o debe instalarla después de la solicitud (se recomienda realizar el siguiente PowerShell para ello).
    
## <a name="configure-the-reverse-proxy"></a>Configurar el proxy inverso
<a name="ConfigRP"> </a>

Los pasos siguientes no están pensados para seguirlos exactamente. Esto se debe a que en las versiones anteriores del producto, nos hemos pasado por el paso de, por ejemplo, la configuración de Threat Management Gateway (TMG) y, si no lo estuviera usando, tendría que crear su propia versión desde allí.
  
Microsoft ya no ofrece TMG como producto y, si todavía necesita configurarlo, puede consultar los [pasos de 2013 de Lync Server](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx). Pero la siguiente información suele ser más útil, incluso si no hay forma de proporcionar pasos de tutoriales específicos para cada proxy inverso.
  
Tenemos dos cosas importantes que debe tener en cuenta:
  
- ¿Va a realizar la solicitud de detección automática inicial a través de HTTPS (recomendado)?
    
  - Si tiene una regla de publicación Web, debe modificarla.
    
  - Si aún no tiene una regla de publicación Web, debe crearla.
    
- Si va a realizar la solicitud de detección automática inicial a través de HTTP, tendrá que crear o modificar también esa regla.
    
> [!NOTE]
> **Importante** Un valor de tiempo de espera de proxy es un número que variará de una implementación a una implementación. Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes. Es posible que pueda establecer el valor como mínimo como 200. Si va a admitir clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir tiempos de espera de notificaciones de inserción de Office 365, que tienen un valor de tiempo de espera de 900. Es muy probable que tenga que aumentar el valor de tiempo de espera para evitar desconexiones de clientes cuando el valor es demasiado bajo, o disminuir el número si las conexiones a través del proxy no se desconectan, sino más lentas después de que el cliente se haya desconectado. La supervisión y la definición de una estructura en su entorno es la única forma precisa de determinar la configuración adecuada para este valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar la regla de publicación web existente para la dirección URL y el SAN de detección automática externa

1. Abra la interfaz de proxy inverso.
    
2. Deberá buscar la regla de publicación web y elegir la opción Editar (puede estar en un menú o una pestaña, según la configuración del proxy inverso).
    
3. Debe haber un área que indique a qué se aplica esta regla de publicación Web. Debe modificar esta regla para los sitios o solicitudes entrantes de los sitios. Va a **Agregar** una nueva entrada.
    
4. Escriba el nombre del sitio de detección automática (el ejemplo que usaremos es lyncdiscover.contoso.com) y haga clic en **Aceptar** o **Guardar**, según el formato de su proxy inverso.
    
5. Es posible que tenga un nuevo certificado que contenga la entrada SAN de detección automática. También debe instalarse y configurarse para usarlo de acuerdo con la configuración del proxy inverso. Asegúrese de guardar todo cuando se complete la configuración.
    
6. Si el proxy inverso tiene una funcionalidad de **prueba** , úselo para asegurarse de que todo funciona correctamente.
    
7. Ahora, es posible que tenga que repetir estos pasos si tiene un director o un grupo de servidores de Director en su entorno (esto significa que tendrá una segunda regla).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Crear una regla de publicación web para la dirección URL externa de detección automática

1. Abra la interfaz de proxy inverso.
    
2. Deberá buscar en el lugar de la interfaz en el que cree las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una ficha, según la configuración del proxy inverso). Busca la opción de crear una nueva regla de publicación Web.
    
3. Normalmente, tendrá que escribir la siguiente información:
    
   - **Name**: el nombre de la regla.
    
   - **Acción de regla**: en este caso, se trata de una regla de **permiso** , que permite que un servidor proxy inverso pase algo.
    
   - La regla de **publicación** o la opción que elija será **un único sitio web o equilibrador de carga**.
    
   - Debe ser **SSL** para el acceso externo; elija esa opción.
    
   - Tendrá que publicar una ruta de acceso para la **publicación interna**y especificar el FQDN de los servicios web externos en el equilibrador de carga del grupo de servidores front-end (o el FQDN del equilibrador de carga del grupo de directores, si tiene uno), un ejemplo sería sfb_pool01. contoso. local.
    
   - Debe escribir ** / *** como la ruta de acceso que se va a publicar, pero también debe **reenviar el encabezado de host original**.
    
   - Habrá una opción para obtener información o información detallada sobre los **nombres públicos o externos** . Este es el lugar en el que podrá escribir:
    
   - **Aceptar solicitudes**, pero debe ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(esta es la dirección URL externa del servicio Detección automática). Ahora, si va a crear una regla para la dirección URL de servicios web externos en el grupo de servidores front-end, tendrá que escribir el FQDN de los servicios web externos en el grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
   - Habrá una opción de **ruta de acceso** y deberá escribir ** / *** aquí.
    
   - Deberá seleccionar un **agente de escucha de SSL** con el certificado público actualizado.
    
   - La **delegación de autenticación** debe establecerse en **sin delegación**, pero **debe** permitirse la autenticación directa de clientes.
    
   - La regla debe establecerse en **todos los usuarios**.
    
   - Esta es la información que necesita para crear esta regla y permitirle continuar.
    
4. Necesitará asegurarse de que el **encabezado de host original** se reenvía.
    
5. Los puertos del **servidor Web** también deben establecerse, tendrá que hacer lo siguiente:
    
   - **Las solicitudes de redireccionamiento al puerto http** y el número de Puerto deberían ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
6. Cuando todo está configurado, necesitará guardar o aplicar estos y, después, querrá probar la regla.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Crear una regla de publicación web para el puerto 80 (opcional)

1. Abra la interfaz de proxy inverso.
    
2. Deberá buscar en el lugar de la interfaz en el que cree las reglas de publicación web y elegir la opción **nuevo** o **crear** (puede estar en un menú o una ficha, según la configuración del proxy inverso). Busca la opción de crear una nueva regla de publicación Web.
    
3. Normalmente, tendrá que escribir la siguiente información:
    
   - **Name**: el nombre de la regla.
    
   - **Acción de regla**: en este caso, se trata de una regla de **permiso** , que permite que un servidor proxy inverso pase algo.
    
   - La regla de **publicación** o la opción que elija será **un único sitio web o equilibrador de carga**.
    
   - Debe ser una **conexión no segura para conectarse al servidor web o la granja de servidores publicada**.
    
   - Tendrá que publicar una ruta de acceso para la **publicación interna**y escribir el FQDN de la **Dirección VIP** del equilibrador de carga del grupo de servidores front-end, un ejemplo sería sfb_pool01. contoso. local.
    
   - Debe escribir ** / *** como la ruta de acceso que se va a publicar, pero también debe **reenviar el encabezado de host original**.
    
   - Habrá una opción para obtener información o información detallada sobre los **nombres públicos o externos** . Este es el lugar en el que podrá escribir:
    
   - **Aceptar solicitudes**, pero debe ser para el nombre de dominio.
    
   - Para el **nombre**, debe escribir **lyncdiscover.** <sipdomain>(esta es la dirección URL externa del servicio Detección automática).
    
   - Habrá una opción de **ruta de acceso** y deberá escribir ** / *** aquí.
    
   - Deberá seleccionar una escucha de web o permitir que el proxy inverso cree una.
    
   - La **delegación de autenticación** debe establecerse en **sin delegación**, pero **no debe** permitirse la autenticación directa de clientes.
    
   - La regla debe establecerse en **todos los usuarios**.
    
   - Esta es la información que necesita para crear esta regla y permitirle continuar.
    
4. Se deben establecer los puertos del **servidor Web** , deberá hacer lo siguiente:
    
   - **Las solicitudes de redireccionamiento al puerto http** y el número de Puerto deberían ser **8080**.
    
   - **Redirigir peticiones al puerto SSL** y el número de puerto debe ser **4443**.
    
5. Cuando todo está configurado, necesitará guardar o aplicar estos y, después, querrá probar la regla.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar la detección automática para movilidad con implementaciones híbridas
<a name="ConfigAutoD"> </a>

Los entornos híbridos de Skype empresarial Server son entornos que combinan un entorno local y de O365. Cuando se trabaja en un entorno híbrido de Skype empresarial Server, el servicio de detección automática necesita poder encontrar a un usuario de cualquiera de estos entornos.
  
Para permitir que los clientes móviles detecten dónde se encuentra un usuario, el servicio de detección automática debe configurarse con un nuevo localizador de recursos uniforme (URL). Estos pasos son:
  
1. Abra el shell de administración de Skype empresarial Server.
    
2. Ejecute lo siguiente para obtener el valor del atributo **ProxyFQDN** para su entorno de Skype empresarial Server:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. A continuación, en la ventana del shell, ejecute:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Donde [identity] se sustituye por el nombre de dominio del espacio de direcciones SIP compartido.
    
## <a name="test-your-mobility-deployment"></a>Probar la implementación de la movilidad
<a name="TestMobility"> </a>

Una vez que haya implementado el servicio de movilidad de Skype empresarial Server y el servicio Detección automática de Skype empresarial Server, querrá ejecutar una transacción de prueba para asegurarse de que la implementación funciona correctamente. Puede ejecutar **Test-CsUcwaConference** para probar la capacidad de dos usuarios para crear, unirse y comunicarse en una conferencia. Necesitará dos usuarios (reales o de prueba) y sus credenciales completas para realizar esta prueba. Este comando funcionará para clientes de Skype empresarial, así como para clientes de Lync Server 2013.
  
Para los clientes de Lync Server 2010 en Skype empresarial Server 2015, deberá ejecutar **Test-CsMcxP2PIM** para probar. Los usuarios de Lync Server 2010 todavía tendrán que ser usuarios reales o usuarios de prueba predefinidos, y necesitará sus credenciales de contraseña.

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Conferencias de prueba para clientes móviles de Skype empresarial y Lync 2013

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   También es posible establecer credenciales en un script y pasarlas al cmdlet test. Se incluye un ejemplo a continuación.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Conferencia de prueba para clientes móviles de Lync 2010

> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.

1. Inicie sesión como miembro del rol **CsAdministrator** en cualquier equipo donde estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server** (puede escribir el nombre en buscar o ir a **todos los programas** y elegirlo).
    
3. En la línea de comandos, escriba:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   También es posible establecer credenciales en un script y pasarlas al cmdlet test. Se incluye un ejemplo a continuación.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para revisar los procedimientos de comando, puede consultar [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) y [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar notificaciones de inserción
<a name="ConfigPush"> </a>

Las notificaciones de inserción, en forma de identificadores, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación de Skype o Lync está inactiva. Pero ¿qué son las notificaciones de inserción? Se trata de alertas de eventos, como una invitación de mi nueva o perdida, o de un correo de voz recibido. El servicio de movilidad de Skype empresarial Server envía estas notificaciones al servicio de notificación de inserción basado en la nube de Skype empresarial Server, que a su vez envía las notificaciones al servicio de notificación de inserción de Microsoft (MSNS) para los usuarios de Windows Phone.
  
Esta funcionalidad no ha cambiado en Lync Server 2013, pero si tiene un servidor de Skype empresarial, querrá hacer lo siguiente:
  
- Para un servidor perimetral de Skype empresarial Server, agregue un nuevo proveedor de hospedaje, Microsoft Skype empresarial online y, a continuación, configure la Federación del proveedor de hospedaje entre su organización y Skype empresarial online.
    
- Habilite las notificaciones de inserción mediante la ejecución del cmdlet **set-CsPushNotificationConfiguration** . De manera predeterminada, las notificaciones de inserción están desactivadas.
    
- Pruebe la configuración de Federación y las notificaciones de inserción.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar el servidor perimetral de Skype empresarial para las notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Agregue un proveedor de hospedaje de Skype empresarial Server online.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Por ejemplo:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > No puede tener más de una relación de Federación con un solo proveedor de hospedaje. Por lo tanto, si ya ha configurado un proveedor de hospedaje que tiene una relación de Federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, incluso si la identidad del proveedor de hospedaje no es SkypeOnline. 
  
4. Configure la Federación del proveedor de hospedaje entre su organización y el servicio de notificaciones de inserción en Skype empresarial online. En la línea de comandos, tendrá que escribir:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar las notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Habilitar notificaciones de inserción:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilitar Federación:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Probar la Federación y las notificaciones de inserción

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Pruebe la configuración de Federación:
    
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

## <a name="configure-mobility-policy"></a>Configurar la Directiva de movilidad
<a name="ConfigMob"> </a>

Tiene la capacidad de Skype empresarial Server para determinar quién puede usar el servicio de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, así como si se necesitará Wi-Fi para VoIP o vídeo. Llamar a través del trabajo permite a un usuario móvil usar su número de teléfono del trabajo, en lugar de su número de teléfono móvil, al colocar y recibir llamadas. La persona que se encuentra en el otro extremo de la línea no verá el número de teléfono móvil del usuario y le permitirá evitar gastos de llamadas salientes. Cuando se configuran VoIP y vídeo, los usuarios pueden realizar llamadas y vídeos de VoIP. La configuración del uso de WiFi determina si el dispositivo móvil de un usuario será necesario para usar una red WiFi a través de una red de datos móviles.
  
La movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas de forma predeterminada. La configuración para requerir WiFi para VoIP y vídeo está deshabilitada. Un administrador tiene la capacidad de cambiar esto, ya sea de forma global, por sitio o por usuario.
  
Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben:
  
- Habilitado para Skype empresarial Server
    
- Habilitado para telefonía IP empresarial.
    
- Se le asigna una directiva de movilidad que tiene la opción **enablemobility configurada** establecida en **true**.
    
Para que los usuarios puedan usar la llamada a través del trabajo, también deben:
  
- Se le asigna una directiva de voz que tiene seleccionada la opción **Habilitar llamadas simultáneas en teléfonos** .
    
- Se le ha asignado una directiva de movilidad que tiene la **EnableOutsideVoice** establecida en **true**.
    
> [!NOTE]
> Los usuarios que no están habilitados para telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas VoIP de Skype a Skype o pueden unirse a conferencias mediante el vínculo haga clic para unirse mientras están en sus dispositivos móviles, si las opciones adecuadas están definidas para la Directiva de voz a la que están asociadas con. Hay más detalles en el tema de PLANEAción. 
  
### <a name="modify-global-mobility-policy"></a>Modificar la Directiva de movilidad global

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Desactive el acceso a la movilidad y llame a través del trabajo de forma global; para ello, escriba lo siguiente:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad. Pero no se puede desactivar la movilidad sin desactivar también la llamada a través del trabajo. 
  
    Para obtener más información, consulte [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar la Directiva de movilidad por sitio

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Puede crear una directiva de nivel de sitio, desactivar VoIP y vídeo, habilitar la opción de requerir Wi-Fi para audio IP y requerir WiFi para vídeo IP por sitio. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Para obtener más información [, vea New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar la Directiva de movilidad por usuario

1. Inicie sesión con una cuenta que sea miembro del rol **CsAdministrator** , en un equipo en el que estén instalados el **Shell de administración de Skype empresarial Server** y **Ocscore** .
    
2. Inicie el **Shell de administración de Skype empresarial Server**.
    
3. Cree directivas de movilidad de nivel de usuario y desactive la movilidad y llame a través del trabajo por parte del usuario. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Otro ejemplo con datos de muestra:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Puede desactivar la llamada a través del trabajo sin desactivar el acceso a la movilidad. Pero no se puede desactivar la movilidad sin desactivar también la llamada a través del trabajo. 
  

